## SLOTS

Collecting User Input

In this lesson, you will add slots to a skill so a user's response can be captured and evaluated by Alexa.

A slot is an argument to an intent that gives Alexa more information about that request.

For example: “Alexa, ask History Buff what happened on June third”. In this statement, “June third” is the value of a date slot that interprets the request.

The Lambda function for a Popular Language skill, that you may recognize from Codecademy's Speak, Listen, & Reprompt lesson, is provided in index.js to the right. The Lambda function currently provides for a static dialogue that does not evaluate user input.

We will use slots to capture user input and update our Lambda function to evaluate it, and respond based on the input received.

We will start the next exercise by creating the interaction model for our skill.

**Instructions:**
Look at the Lambda function to the right. You will update the LaunchRequest and LanguageIntent so Alexa deliver's appropriate speech output to a user's response.

```js
"use strict";

var Alexa = require("alexa-sdk");

var handlers = {
  'LaunchRequest': function() {
    this.response.speak("Hello, Welcome to Codecademy. What do you think is Codecademy's most popular language?").listen("Tell me what you think is Codecademy's most popular language.");
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
};
```
