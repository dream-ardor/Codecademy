## SPEAK, LISTEN & REPROMPT

Make Alexa Speak

Let's walk through the Lambda function for an example Popular Language skill.

The index.js file to the right contains a Lambda function with empty handlers for the initial speaking portions of this skill.

We'll add Alexa responses for two scenarios:

* When the user launches the skill (triggers LaunchRequest)
* When a user responds to the question from Alexa (triggers LanguageIntent)

Set up Alexa Response
Alexa's response is generated using the Alexa SDK's this.response.speak() method.

this.response contains functions used to set up a response from Alexa, like this:
```js
this.response.speak("Hello, welcome to Codecademy!")
```
Send Alexa Response
Once the response is set up, we use this.emit(':responseReady') to send our response to the user's Alexa device.
```js
'LaunchRequest': function () {
    this.response.speak("Hello, welcome to Codecademy!");
    this.emit(':responseReady');
  },
```
Together, these two lines (.speak() and .emit(':responseReady')) set up and send the response to the user's Alexa device. One thing to note, is that .speak() generates a response and then instructs Alexa to close the session.

When creating a conversation, you usually don't want to close the session. Alexa SDK's .listen() method allows us to instruct the device to keep the session open to allow a conversational dialogue.

**Instructions:**
In the index.js file to the right, within the LaunchRequest, use .speak to greet the user with:

Hello, Welcome to Codecademy. What do you think is Codecademy's most popular language?

Use .emit with the ':responseReady' argument to send the response object within the LaunchRequest handler.

Within the LanguageIntent handler, use .speak to respond to the user's guess with:

Python is our most popular language.

Use .emit with the ':responseReady' argument to send the response object within the LanguageIntent handler.

## **My Code:**
```js
"use strict";

var Alexa = require("alexa-sdk");

var handlers = {
  "LaunchRequest": function () {
    this.response.speak("Hello, Welcome to Codecademy. What do you think is Codecademy's most popular language?");
    this.emit(':responseReady');
  },
  "LanguageIntent": function () {
    this.response.speak("Python is our most popular language.");
    this.emit(':responseReady');
  }
}

exports.handler = function(event, context, callback){
    var alexa = Alexa.handler(event, context);
    alexa.registerHandlers(handlers);
    alexa.execute();
}
```
