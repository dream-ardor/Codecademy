## UNDERSTAND YOUR LAMBDA FUNCTION

### Add handle for LaunchRequest

So far our code states that the LaunchRequestHandler can handle requests of type LaunchRequest. But how should it handle that request?

Alexa should speak back to the user: "Welcome to Codecademy".

We can use responseBuilder, .speak(), and .getResponse() to formulate that response:
```js
handle(handlerInput) {
   const speakOutput = 'Welcome to Codecademy;

   return handlerInput.responseBuilder
      .speak(speakOutput)
      .getResponse();
}
```
When executed, this handle method will generate the following JSON response:
```js
{
  "body": {
    "version": "1.0",
    "response": {
      "outputSpeech": {
        "type": "SSML",
        "ssml": "<speak>Welcome to Codecademy</speak>"
      },
      "shouldEndSession": false
    },
    "sessionAttributes": {},
    "userAgent": "ask-node/2.0.0 Node/v8.10.0"
  }
}
```
The response is sent back to Alexa, which will parse the JSON, and speak the words in the "ssml" value, which in this case is "Welcome to Codecademy".

**Instructions:**
* In your LaunchRequestHandler object, define a handle method with one parameter, handlerInput.

* Using responseBuilder, write a handle method body that builds a response and returns it as a JSON object.

* The text to speak should be "Welcome to Codecademy".

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
  }
};
```
