## UNDERSTAND YOUR LAMBDA FUNCTION

### Add handle for HelloIntent

We have a canHandle method for the HelloHandler, which returns true when the request type is 'IntentRequest' and the request intent name is 'HelloIntent'. At this point we need to add the code that will return a JSON response: the handle method.

Instead of formulating JSON from scratch, we can use the ASK SDK's responseBuilder, which is provided in the handlerInput object.

Inside the responseBuilder object are methods which can be chained to create a JSON response:
```js
handle(handlerInput) {
   const speakOutput = 'Hello Codecademy';

   return handlerInput.responseBuilder
      .speak(speakOutput)
      .getResponse();
}
```
responseBuilder.speak() defines the text that Alexa will say. It returns an object, but the handle method must return a JSON response, so we call getResponse() to convert the object into JSON.
```js
{
  "body": {
    "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>Hello Codecademy</speak>"
        }
      },
      "sessionAttributes": {},
      "userAgent": "ask-node/2.0.0 Node/v8.10.0"
  }
}
```
The above response is sent back to Alexa, which will parse the JSON, and speak the words in the "ssml" value, which in this case is "Hello Codecademy".

What is SSML?

SSML stands for Speech Synthesis Markup Language.

You can think of SSML as HTML for speech. It is a markup language that provides a standard way to mark up text for the generation of synthetic speech.

For now, all you need to know is that the speak method will wrap its argument string in <speak> tags, as you see in the JSON response above. You can read more about the SSML tags supported by the Alexa Skills Kit at developer.amazon.com.

**Instructions:**
In your HelloHandler object, define a handle(handlerInput) method.

Using responseBuilder, write a handle method body that builds a response and returns it as a JSON object.

The text to speak should be "Hello Codecademy".

**My Code:**
```js
const Alexa = require('ask-sdk-core');

const HelloHandler = {
  canHandle(handlerInput) {
    return handlerInput.requestEnvelope.request.type === 'IntentRequest'
      && handlerInput.requestEnvelope.request.intent.name === 'HelloIntent';
  },
  handle(handlerInput){
    return handlerInput.responseBuilder
    .speak("Hello Codecademy")
    .getResponse();
  }
};
```
