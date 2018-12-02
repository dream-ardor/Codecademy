Handling Errors<br>
When .catch() is used with a long promise chain, there is no indication of where in the chain the error was thrown. This can make debugging challenging.

With async...await, we use try...catch statements for error handling. By using this syntax, not only are we able to handle errors in the same way we do with synchronous code, but we can also catch both synchronous and asynchronous errors. This makes for easier debugging!
```javascript
async function usingTryCatch() {
 try {
   let resolveValue = await asyncFunction('thing that will fail');
   let secondValue = await secondAsyncFunction(resolveValue);
 } catch (err) {
   // Catches any errors in the try block
   console.log(err);
 }
}
```
Remember, since async functions return promises we can still use native promise's .catch() with an async function
```javascript
async function usingPromiseCatch() {
   let resolveValue = await asyncFunction('thing that will fail');
}

let rejectedPromise = usingPromiseCatch();
rejectedPromise.catch((rejectValue) => {
console.log(rejectValue);
})
```
This sometimes used in the global scope to catch final errors in complex code.

**Instructions**
* For convenience, we've been working with a lot of promises that never reject, but this isn't very realistic!

This time we've required in a function, cookBeanSouffle() which returns a promise that resolves or rejects randomly. When it resolves, the promise resolves with a value of 'Bean Souffle' and, when it rejects, it rejects with a value of 'Dinner is ruined!'. If you're interested, you can see how the function works by looking in the library.js file.

Press "Check Work" when you're ready to move on to the next step.

* Declare an async function, hostDinnerParty(). Inside your function, create a try...catch statement. The catch statement should specify an identifier, error. You can leave both the try and catch blocks empty.


* Inside your try block, log a string in the following format: '[resolved value of cookBeanSouffle() promise] is served!' ie. 'Bean Souffle is served!'. Make sure to await the cookBeanSouffle() promise. For more guidance, check out the hint.

* Now let's fill in the catch block! First log the error to the console, and then log the string: 'Ordering a pizza!' to the console.

* Awesome! Beneath your function declaration, invoke hostDinnerParty().

* Let's see your function in action. In the terminal type node app.js and press enter to run the code. If you keep executing app.js you'll see the results of the promise resolving or rejecting.

**My Code:**
```javascript
const cookBeanSouffle = require('./library.js');

// Write your code below:
async function hostDinnerParty() {
 try{
 let dinner = await cookBeanSouffle();
   console.log(`${dinner} is served!`)
 }
  catch(error){
    console.log(error)
    console.log('Ordering a pizza!')
  }
}

hostDinnerParty()
```
