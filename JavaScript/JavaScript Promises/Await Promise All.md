Await Promise.all()<br>
Another way to take advantage of concurrency when we have multiple promises which can be executed simultaneously is to await a Promise.all().

We can pass an array of promises as the argument to Promise.all(), and it will return a single promise. This promise will resolve when all of the promises in the argument array have resolved. This promise's resolve value will be an array containing the resolved values of each promise from the argument array.
```javascript
async function asyncPromAll() {
  const resultArray = await Promise.all([asyncTask1(), asyncTask2(), asyncTask3(), asyncTask4()]);
  for (let i = 0; i<resultArray.length; i++){
    console.log(resultArray[i]); 
  }
}
```
In our above example, we await the resolution of a Promise.all(). This Promise.all() was invoked with an argument array containing four promises (returned from required-in functions). Next, we loop through our resultArray, and log each item to the console. The first element in resultArray is the resolved value of the asyncTask1() promise, the second is the value of the asyncTask2() promise, and so on.

Promise.all() allows us to take advantage of asynchronicity— each of the four asynchronous tasks can process concurrently. Promise.all() also has the benefit of failing fast, meaning it won't wait for the rest of the asynchronous actions to complete once any one has rejected. As soon as the first promise in the array rejects, the promise returned from Promise.all() will reject with that reason. As it was when working with native promises, Promise.all() is a good choice if multiple asynchronous tasks are all required, but none must wait for any other before executing.

**Instructions:**
In this exercise, we require in the same four functions as in the last exercise: cookBeans(), steamBroccoli(), cookRice(), and bakeChicken().

These functions each return a promise which will resolve to a string representing a part of a meal. You can check them out in the library.js file. Press "Check Work" to move on to the next step.

* You're going to create a very similar function to the serveDinner() function you created in the last exercise. This time, you'll use Promise.all()!

Create an async function serveDinnerAgain(). Inside your function, declare a variable foodArray and assign it the resolved value of returned from Promise.all().

Remember that Promise.all() takes in an array of promises. Pass in an array containing the steamBroccoli(), cookRice(), bakeChicken(), and cookBeans() functions in that order.

* Next console.log() a string in the following format: Dinner is served. We're having [first item in foodArray ], [second item in foodArray ], [third item in foodArray], and [fourth item in foodArray ]. eg. 'Dinner is served. We're having broccoli, rice, chicken, and beans.'

There are a few different ways you can accomplish the desired functionality. Check out the hint if you want some guidance.

* Ok great! Now let's see your function in action. Beneath your function declaration, invoke serveDinnerAgain().

In the terminal type node app.js and press enter to run the code.

**My Code:**
```javascript
let {cookBeans, steamBroccoli, cookRice, bakeChicken} = require('./library.js')

// Write your code below:
async function serveDinnerAgain() {
  let foodArray = await Promise.all([steamBroccoli(),cookRice(),bakeChicken(),cookBeans()]);
  
  let vegetable = foodArray[0];
  let starch = foodArray[1];
  let protein = foodArray[2];
  let side = foodArray[3];
console.log(`Dinner is served. We're having ${vegetable}, ${starch}, ${protein}, and ${side}.`);
}
 serveDinnerAgain()
```
