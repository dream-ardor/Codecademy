Handling Dependent Promises<br>
The true beauty of async...await is when we have a series of asynchronous actions which depend on one another. For example, we may make a network request based on a query to a database. In that case, we would need to wait to make the network request until we had the results from the database. With native promise syntax, we use a chain of .then() functions making sure to return correctly each one:
```javascript
function nativePromiseVersion() {
    returnsFirstPromise()
    .then((firstValue) => {
        console.log(firstValue);
        return returnsSecondPromise(firstValue);
    })
   .then((secondValue) => {
        console.log(secondValue);
    });
}
```
**Instructions:**
Take a look at the provided code. We require in three functions: shopForBeans(), soakTheBeans(), and cookTheBeans(). These functions each return a promise.

shopForBeans() expects no arguments and returns a promise which will resolve to a string of a bean type.
soakTheBeans() expects a bean type string as an argument and returns a promise which resolves to a boolean indicating whether or not the beans are softened.
cookTheBeans() expects a boolean as an argument and, if that value is true, returns a promise which will resolve to a string announcing that dinner is ready.
If you'd like, look at the library.js file to see how these functions work. Press "Check Work" to move on to the next step.

* In the following checkpoints, you'll create an async function that handles the three dependent promises we just walked through. It will simulate shopping for, soaking, and then cooking the beans. To get started, declare an async function, makeBeans(). You can leave the function body blank for now.

* Inside your function, declare a variable, type, assigned to the resolved value of shopForBeans(). This must be accomplished in one statement.

* Next inside your function, declare a variable, isSoft, assigned to the resolved value of soakTheBeans(). Don't forget: the soakTheBeans() function expects an argument. Make sure to pass the expected value into soakTheBeans().

* Next inside your function, declare a variable, dinner, assigned to the resolved of cookTheBeans(). Don't forget: the cookTheBeans() function also expects an argument. Make sure to pass the expected value into cookTheBeans().

* Next inside your function, log your dinner variable to the console.

* Beneath your function declaration, invoke the makeBeans() function.

* Let's see your async function in action! In the terminal, type node app.js and press enter to execute the code.

**My Code:**
```javascript
const {shopForBeans, soakTheBeans, cookTheBeans} = require('./library.js');

// Write your code below:
async function makeBeans(){
  let type =  await shopForBeans();
  let isSoft = await soakTheBeans(type);
  let dinner = await cookTheBeans(isSoft);
  console.log(dinner);
  makeBeans()
}
```
