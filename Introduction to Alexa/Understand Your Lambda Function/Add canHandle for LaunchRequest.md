## UNDERSTAND YOUR LAMBDA FUNCTION

### Add canHandle for LaunchRequest

We can request a response from our skill in two ways:

Style 1: "Alexa, tell code academy hello"

and

Style 2: "Alexa, open code academy"

Style 1: IntentRequest
When the user says "Alexa, tell code academy hello", Alexa recognizes that a specific intent is being requested (IntentRequest), and using the sample utterances provided in the Interaction Model, maps it to HelloIntent. (You may have added these utterances in Build Your First Alexa Skill.)

You can see in the truncated JSON response below that our skill receives a request of type "IntentRequest", and name "HelloIntent".
```js
{
  "session": {
     ...
     ...
  },
  "request": {
    "type": "IntentRequest",
    "intent": {
      "name": "HelloIntent",
      "slots": {}
    },
     ...
  },
     ...
}
```
Style 2: LaunchRequest
If however, the user invokes the skill with the invocation name, but does not provide any command mapping to an intent, like "Alexa, open code academy", our skill will receive a "LaunchRequest", instead of "IntentRequest".

You can see in the truncated JSON response below that our skill receives that the type of request is "LaunchRequest".
```js
{
  "session": {
     ...
     ...
    }
  },
  "request": {
    "type": "LaunchRequest",
     ...
  },
     ...
}
```
To provide a response for this type of request, we will add another handler called LaunchRequestHandler. Its canHandle method will return true if the request type is 'LaunchRequest'.
```js
const LaunchRequestHandler = {
   /* canHandle and handle go here */
};
```
**Instructions:**
Below the HelloHandler, create another handler named LaunchRequestHandler.

In LaunchRequestHandler, define a canHandle method with one argument, handlerInput.

Fill in the method canHandle so that it returns true if

handlerInput.requestEnvelope.request.type
is 'LaunchRequest'.

**My Code:**
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
    return handlerInput.requestEnvelope.request.type === 'LaunchRequest'
  }
}
```
