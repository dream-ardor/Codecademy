JAVASCRIPT PROMISES<br>
The onFulfilled and onRejected Functions<br>
To handle a "successful" promise, or a promise that resolved, we invoke .then() on the promise, passing in a success handler callback function:
```javascript
const prom = new Promise((resolve, reject) => {
  resolve('Yay!');
});

const handleSuccess = (resolvedValue) => {
  console.log(resolvedValue);
};

prom.then(handleSuccess); // Prints: 'Yay!'
```
Let's break down what's happening in the example code:

* prom is a promise which will resolve to 'Yay!'.
* We define a function, handleSuccess(), which prints the argument passed to it.
* We invoke prom's .then() function passing in our handleSuccess() function.
* Since prom resolves, handleSuccess() is invoked with prom's resolved value, 'Yay', so 'Yay' is logged to the console.
With typical promise consumption, we won't know whether a promise will resolve or reject, so we'll need to provide the logic for either case. We can pass both an onFulfilled and onRejected callback to .then().
```javascript
let prom = new Promise((resolve, reject) => {
  let num = Math.random();
  if (num < .5 ){
    resolve('Yay!');
  } else {
    reject('Ohhh noooo!');
  }
});

const handleSuccess = (resolvedValue) => {
  console.log(resolvedValue);
};

const handleFailure = (rejectionReason) => {
  console.log(rejectionReason);
};

prom.then(handleSuccess, handleFailure);
```
Let's break down what's happening in the example code:

* prom is a promise which will randomly either resolve with 'Yay!'or reject with 'Ohhh noooo!'.
* We pass two handler functions to .then(). The first will be invoked with 'Yay!' if the promise resolves, and the second will be invoked with 'Ohhh noooo!' if the promise rejects.<br>

Let's write some onFulfilled and onRejected functions!

* Write a function, handleSuccess(). You'll use this function later on as your success handler. handleSuccess() should have one parameter, representing a resolved value. Inside the body of handleSuccess(), log the parameter to the console.

* Write a function, handleFailure(). You'll use this function later on as your failure handler. handleFailure() should have one parameter, representing a rejection reason. Inside the body of handleFailure(), log the parameter to the console.

* Invoke checkInventory() with order. This will return a promise. Attach a .then() function to this. Pass into .then() the two handlers you wrote as callback functions.

* Type node app.js in the terminal and hit enter.

**My Code:**
```javascript
const {checkInventory} = require('./library.js');

const order = [['sunglasses', 1], ['bags', 2]];

// Write your code below:


const handleSuccess = (resolvedValue) => {
  console.log(resolvedValue)
}

const handleFailure = (rejectionReason) => {
  console.log(rejectionReason)
}

checkInventory(order).then(handleSuccess,handleFailure)
```
