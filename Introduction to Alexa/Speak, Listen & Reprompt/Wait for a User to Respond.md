## SPEAK, LISTEN & REPROMPT

Wait for a User to Respond

Like we said in the last exercise, .speak() generates a response and then ends the session, so we're never capturing the response from the user.

Currently, our skill is set up so that Alexa asks the user a question and the user may try to respond, but Alexa isn't listening because the session has closed. To keep the session open and get the user response we use the .listen() method.

However, we want to continue the conversation and use .listen to make the skill wait for the user to trigger the LanguageIntent.

We use .listen() by chaining it to the end of the .speak response definition.

As an example, if the handler for SampleIntent responded What is your name?, and waited for a response, the code would look like:
```js
'SampleIntent': function () {
    this.response.speak("What is your name?").listen();
    this.emit(':responseReady');
  },
```

**Instructions:**
In the index.js file to the right, add a .listen() method to the LaunchRequest response. This ensures Alexa waits for a response from the user and doesn't terminate the session.

## **My Code:**
```js
"use strict";

var Alexa = require("alexa-sdk");

var handlers = {
  'LaunchRequest': function() {
    this.response.speak("Hello, Welcome to Codecademy. What do you think is Codecademy's most popular language?").listen();
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
