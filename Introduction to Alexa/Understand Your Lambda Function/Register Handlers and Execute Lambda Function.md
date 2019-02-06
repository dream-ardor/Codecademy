## UNDERSTAND YOUR LAMBDA FUNCTION

### Register Handlers and Execute Lambda Function

We've defined our requests and error handlers, but how does AWS Lambda call them, and how does it know which to execute?

We'll create and export one function that accesses those handlers in the order we choose. Whenever a request is sent by Alexa, AWS Lambda calls that one function, passing it the JSON request. The function processes the request, returns a JSON response, and AWS Lambda sends it back to Alexa.

Instead of building this function from scratch, we will use the Alexa.SkillBuilders provided by the ASK SDK. For simple skills like ours, use the custom version:

const skillBuilder = Alexa.SkillBuilders.custom();
Earlier in the lesson, we said that the SDK will go down the line of handlers in order, checking if each handler can handle the request. We define that order by registering the handlers to the function, using the skill builder's addRequestHandlers and addErrorHandlers methods.
```js
exports.handler = skillBuilder
  .addRequestHandlers(
    LaunchRequestHandler,
    HelloHandler
  )
  .addErrorHandlers(ErrorHandler)
```
In the above code, LaunchRequestHandler is registered first, so the SDK will always call its canHandle method first. If it returns true, the SDK calls its handle method. Otherwise, the SDK continues down the list, calling the next handler's canHandle method. In this case the next handler is HelloHandler.

Finally, to create the function that AWS Lambda invokes we'll use the skill builder's lambda method:
```js
exports.handler = skillBuilder
  .addRequestHandlers(
    LaunchRequestHandler,
    HelloHandler
  )
  .addErrorHandlers(ErrorHandler)
  .lambda();
```
The lambda() method returns a function, and we export it by assigning it to exports.handler.

**Instructions:**
* At the bottom of index.js, define a custom skillBuilder using the SDK.

* Using skillBuilder, let's create the function for AWS Lambda to invoke.

* First, register the following request handlers in order:
LaunchRequestHandler
HelloHandler

* Register the following error handler:
ErrorHandler

* Generate the function with .lambda().

* Export the function by storing it in exports.handler.

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
  },
};

const skillBuilder =
      Alexa.SkillBuilders.custom();
exports.handler = skillBuilder
  .addRequestHandlers(
    LaunchRequestHandler,
    HelloHandler
  )
	.addErrorHandlers(ErrorHandler)
	.lambda()
```
