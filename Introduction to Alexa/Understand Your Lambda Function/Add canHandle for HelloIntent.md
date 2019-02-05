## UNDERSTAND YOUR LAMBDA FUNCTION

**Add canHandle for HelloIntent**

Answer to the previous exercise: Handler2 is the first one that can handle the request, so its handle method will be executed.

Now let's write some request handlers!

One of your skill's intents is the HelloIntent, which expects a greeting like "Hello, John". We can name the handler anything, but for clarity let's call the handler HelloHandler:
```js
const HelloHandler = {
  canHandle(handlerInput) {
  },
  handle(handlerInput) {
  },
};
```
The handler can handle the request if the request type is 'IntentRequest' and the request intent name is 'HelloIntent':
```js
 canHandle(handlerInput) {
    return handlerInput.requestEnvelope.request.type === 'IntentRequest'
      && handlerInput.requestEnvelope.request.intent.name === 'HelloIntent';
  }
  ```
We learned that the SDK will 'ask' each handler if they can handle the request. What's really happening is this:

The SDK calls the handlers' canHandle method with the argument handlerInput. This contains information about the request sent by the Alexa Service. It's in the form of JSON, which can be treated like a JavaScript object.
The canHandle method contains conditional logic which returns either true, if it can handle the request, or false, if it cannot.
If the canHandle method returns true, the SDK calls the handlers handle method. If false, the process repeats with the next handler in the sequence.

**Instructions:**
In your Lambda function in index.js, define an object HelloHandler. It should have one method with the signature canHandle(handlerInput).

Fill in the method canHandle so that it returns true if

handlerInput.requestEnvelope.request.type
is 'IntentRequest', and

handlerInput.requestEnvelope.request.intent.name
is 'HelloIntent'.

**My Code:**
```js
const Alexa = require('ask-sdk-core');

const HelloHandler = {
  canHandle(handlerInput) {
      return handlerInput.requestEnvelope.request.type === 'IntentRequest'
      && handlerInput.requestEnvelope.request.intent.name === 'HelloIntent';
  },
  handle(handlerInput) {
  },
};
```
