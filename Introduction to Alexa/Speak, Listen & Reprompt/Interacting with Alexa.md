## SPEAK, LISTEN & REPROMPT

Interacting with Alexa

In this lesson, you will learn the fundamentals of generating dialogue using the Alexa SDK to create the following conversation:

Alexa: Hello, welcome to Codecademy. What do you think is Codecademy's most popular language?
Once Alexa asks this, you can instruct Alexa to listen for a user's response. Regardless of the user's answer, Alexa will say:

Alexa: Python is our most popular language.
If the user doesn't understand the initial question, or does not respond in a timely manner, Alexa can reprompt the user with a custom message.

While we are focusing on the question, response, and reprompt from Alexa, in Codecademy's slots lesson, you can learn to build a skill that customizes Alexa's response based on user input.

**Instructions:**
In this lesson, you will learn to add dialogue to a Lambda function for a Popular Language skill using the Alexa-SDK, like the one in the code to the right.

## **My Code:**
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
