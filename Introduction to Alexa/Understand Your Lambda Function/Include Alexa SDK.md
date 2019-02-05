##UNDERSTAND YOUR LAMBDA FUNCTION

Include Alexa SDK

In the first lesson, you copied code from Codecademy and pasted it into your AWS account. In this lesson, we will walk you through that code, which lays the foundation for more advanced Alexa concepts, like saving user input, creating synonyms, and managing complex dialog.

While you can create a skill using any modern language, including Java and Python, we will build skills using Node.js® — a popular server-side JavaScript platform.

The event-driven model of Node is well suited for an Alexa skill. Also, Node is one of the largest ecosystems of open source libraries in the world.

One such library is the Alexa Skills Kit Software Development Kit (ASK SDK) from Amazon. The Node ASK SDK provides a set of functions that make it fast and easy to build skills — we'll use those throughout this lesson. You can read more in the ASK SDK documentation.

One of the first things we will do is include the ASK SDK in our Lambda function — this makes the SDK's core functions available in our Lambda function. We do this with the following require() statement:

const Alexa = require('ask-sdk-core');
This lesson assumes that you have basic JavaScript knowledge: variables, conditionals, and functions. If you've taken the first three courses of our Introduction to JavaScript series, you're ready! If not, you may want to take those before continuing.

**Instructions:**
At the top of index.js, import the ask-sdk-core.

**My Code:**
```js
const Alexa = require('ask-sdk-core');
```
