Handling Independent Promises<br>
Remember that await halts the execution of our async function. This allows us to conveniently write synchronous-style code to handle dependent promises. But what if our async function contains multiple promises which are not dependent on the results of one another to execute?
```javascript
async function waiting() {
 const firstValue = await firstAsyncThing();
 const secondValue = await secondAsyncThing();
 console.log(firstValue, secondValue);
}

async function concurrent {
 const firstPromise = firstAsyncThing();
 const secondPromise = secondAsyncThing();
console.log(await firstPromise, await secondPromise);
}
```
In the waiting() function, we pause our function until the first promise resolves, then we construct the second promise. Once that resolves, we print both resolved values to the console.

In our concurrent() function, both promises are constructed without using await. We then await each of their resolutions to print them to the console.

With our concurrent() function both promises' asynchronous operations can be run simultaneously. If possible, we want to get started on each asynchronous operation as soon as possible! Within our async functions we should still take advantage of concurrancy, the ability to perform asynchronous actions at the same time.

Note: if we have multiple truly independent promises that we would like to execute fully in parallel, we must use individual .then() functions and avoid halting our execution with await.

**Instructions:**
* Take a look at the provided code. We require in four functions: cookBeans(), steamBroccoli(), cookRice(), and bakeChicken(). These functions each return a promise which will resolve to a string representing a part of a meal.

* Declare an async function, serveDinner(). Create four variables:

vegetablePromise which should be assigned the return value of steamBroccoli()
starchPromise which should be assigned the return value of cookRice()
proteinPromise which should be assigned the return value of bakeChicken()
and sidePromise which should be assigned the return value of cookBeans()
These variables should be assigned the promise objects themselves not their resolved values.

* Next console.log() a string in the following format: Dinner is served. We're having [resolved value of the vegetablePromise], [resolved value of the starchPromise], [resolved value of the proteinPromise], and [resolved value of the sidePromise]. ie. 'Dinner is served. We're having broccoli, rice, chicken, and beans.'

You'll need to await each promise, but there are a few different ways you can accomplish the desired functionality. Check out the hint if you want some guidance.

* Awesome! Let's see your function in action. Beneath your function declaration, invoke serveDinner().

* In the terminal type node app.js and press enter to run the code.

**My Code:**
```javascript
let {cookBeans, steamBroccoli, cookRice, bakeChicken} = require('./library.js')

// Write your code below:

async function serveDinner() {
  let vegetablePromise =  steamBroccoli();
  let starchPromise =  cookRice();
  let proteinPromise = bakeChicken();
  let sidePromise = cookBeans();
  console.log(`Dinner is served. We're having ${await vegetablePromise}, ${await starchPromise}, ${await proteinPromise}, and ${await sidePromise}.`)
}

serveDinner()
```
