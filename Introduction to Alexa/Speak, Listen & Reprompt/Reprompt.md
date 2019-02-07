## SPEAK, LISTEN & REPROMPT

Reprompt

Currently, the Lambda function for our Popular Language skill responds with the welcome message, waits for the next user utterance and then sends the LanguageIntent response.

Although this is the behavior we desire, what happens if a user misses the question or Alexa was unable to understand the user's utterance?

When Alexa does not process a valid response to the .listen() method, it times out and ends the session. Alexa provides a reprompt capability to improve these interactions — you can pass a string as an argument into the .listen() method that Alexa uses to re-state a question to the user.
```js
'LaunchRequest': function () {
    this.response.speak("What is Codecademy's most popular language?").listen("Sorry I didn't get that. What is Codecademy's most popular language?");
    this.emit(':responseReady');
  },
```
In the example above, a user's device will reprompt them with, "Sorry I didn't get that. What is Codecademy's most popular language?" if they don't respond in a timely manner:
```
Alexa: What is Codecademy's most popular language?
User doesn't respond
Alexa: Sorry I didn't get that. What is Codecademy's most popular language?
User: Python
Alexa: Python is Codecademy's most popular language.
```

**Instructions:**
In the index.js file to the right, pass a string as an argument to the .listen() method within the LaunchRequest handler.

We want Alexa to reprompt the user with:

Tell me what you think is Codecademy's most popular language

## **My Code:**
```js
"use strict";

var Alexa = require("alexa-sdk");

var handlers = {
  'LaunchRequest': function() {
    this.response.speak("Hello, Welcome to Codecademy. What do you think is Codecademy's most popular language?").listen("Tell me what you think is Codecademy's most popular language");
    this.emit(':responseReady');
  },
  'LanguageIntent': function () {
    this.response.speak("Python is our most popular language.");
    this.emit(':responseReady');
  },
}

exports.handler = function(event, context, callback){
    var alexa = Alexa.handler(event, context);
    alexa.registerHandlers(handlers);
    alexa.execute();
}
```
