## UNDERSTAND YOUR LAMBDA FUNCTION

### Review
You just built your first Lambda function! In this lesson you:

* Imported the SDK using require
* Wrote handler objects with canHandle and handle methods
* Built responses using the responseBuilder, speak(), and getResponse()
* Defined an error handler
* Used skillBuilder to register handlers and create a function for AWS Lambda to call
* To learn more, check out these pages in the ASK SDK documentation:

Request and Error Handlers
ResponseBuilder
Skill Builders

For more examples, read the tutorial "Developing Your First Skill" in the same documentation.

If you're interested in learning more from the Alexa community or you have questions, you should check out:

* Amazon Alexa Developer Forums
* Alexa Office Hours on Twitch
* AlexaDevs on Twitter

**Instructions**

The complete Lambda function code is provided here. We've added three additional request handlers that are required for any basic skill: HelpIntentHandler, CancelAndStopIntentHandler, and SessionEndedRequestHandler.

If you'd like, you can copy it into AWS Lambda and test it!

```js
const Alexa = require('ask-sdk-core');

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

const HelpHandler = {
  canHandle(handlerInput) {
    return handlerInput.requestEnvelope.request.type === 'IntentRequest'
      && handlerInput.requestEnvelope.request.intent.name === 'AMAZON.HelpIntent';
  },
  handle(handlerInput) {
    const speakOutput = 'You can say hello to me!';

    return handlerInput.responseBuilder
      .speak(speakOutput)
      .getResponse();
  },
};

const CancelAndStopHandler = {
  canHandle(handlerInput) {
    return handlerInput.requestEnvelope.request.type === 'IntentRequest'
      && (handlerInput.requestEnvelope.request.intent.name === 'AMAZON.CancelIntent'
        || handlerInput.requestEnvelope.request.intent.name === 'AMAZON.StopIntent');
  },
  handle(handlerInput) {
    const speakOutput = 'Goodbye!';

    return handlerInput.responseBuilder
      .speak(speakOutput)
      .getResponse();
  },
};

const SessionEndedRequestHandler = {
  canHandle(handlerInput) {
    return handlerInput.requestEnvelope.request.type === 'SessionEndedRequest';
  },
  handle(handlerInput) {
    console.log(`Session ended with reason: ${handlerInput.requestEnvelope.request.reason}`);

    return handlerInput.responseBuilder.getResponse();
  },
};

const ErrorHandler = {
  canHandle() {
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

const skillBuilder = Alexa.SkillBuilders.custom();

exports.handler = skillBuilder
  .addRequestHandlers(
    LaunchRequestHandler,
    HelloHandler,
    HelpHandler,
    CancelAndStopHandler,
    SessionEndedRequestHandler,
  )
  .addErrorHandlers(ErrorHandler)
  .lambda();
```
