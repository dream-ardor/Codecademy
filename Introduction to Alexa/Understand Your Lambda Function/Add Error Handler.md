## UNDERSTAND YOUR LAMBDA FUNCTION

### Add Error Handler

If all goes well, our skill's users can say "Alexa, tell code academy hello", which sends a HelloIntent request, and get the response "Hello John". They can also say "Alexa, open code academy", which sends a LaunchRequest, and get the response "Welcome to Codecademy".

What if the user does neither of those? What if we made a mistake in our code?

Our skill should be able to handle them gracefully, providing a friendly explanation to users. To do that, the ASK SDK supports error handlers, which are like request handlers, but they are responsible for handling errors that are thrown during request processing. They have canHandle and handle methods, though they have two parameters:

handlerInput — the same object we used with request handlers. It contains the JSON request and helper methods
error — an object describing the error, with stack, message, and name properties
```js
const ErrorHandler = {
  canHandle(handlerInput, error) {
  },
  handle(handlerInput, error) {
  },
};
```
The error handler's canHandle method defines the type of errors it can handle. For example, you can return true when the error's name starts with "AskSdk":
```js
canHandle(handlerInput, error) {
  return error.name.startsWith('AskSdk');
}
```
To create a catch-all handler, simply return true for all cases:
```js
canHandle(handlerInput, error) {
  return true;
}
```
**Instructions:**
* Below your request handlers, define an ErrorHandler object.

* Within the ErrorHandler, define a catch-all canHandle method.

It should return true in all cases.
It should accept two arguments.

* Within the ErrorHandler, define a handle method with

two parameters, handlerInput and error, and
the following body:
```js
  console.log(`Error handled: ${error.message}`);
  console.log(error.trace);

  return handlerInput.responseBuilder
    .speak('Sorry, I can\'t understand the command. Please say again.')
    .getResponse();
```
This will log information about the error and tell the user "Sorry, I can't understand the command. Please say again."

## **My Code:**
```js
const Alexa = require('ask-sdk-core');

const HelloHandler = {
  canHandle(handlerInput) {
    return handlerInput.requestEnvelope.request.type === 'IntentRequest'
      && handlerInput.requestEnvelope.request.intent.name === 'HelloIntent';
  },
  handle(handlerInput) {
    const speakOutput = 'Hello Codecademy';

    return handlerInput.responseBuilder
      .speak(speakOutput)
      .getResponse();
  },
};

const LaunchRequestHandler = {
  canHandle(handlerInput) {
    return handlerInput.requestEnvelope.request.type === 'LaunchRequest';
  },
  handle(handlerInput) {
    const speakOutput = 'Welcome to Codecademy';

    return handlerInput.responseBuilder
      .speak(speakOutput)
      .getResponse();
  },
};

const ErrorHandler = {
  canHandle(handlerInput, error) {
    return true;
  },
  handle(handlerInput, error) {
     console.log(`Error handled: ${error.message}`);
  console.log(error.trace);

  return handlerInput.responseBuilder
    .speak('Sorry, I can\'t understand the command. Please say again.')
    .getResponse();
  }
}
```
