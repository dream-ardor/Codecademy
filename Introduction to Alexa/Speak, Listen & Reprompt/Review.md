## SPEAK, LISTEN & REPROMPT

Review

You have learned a number of methods in this lesson to control how Alexa interacts with a user.

* this.response.speak() sets up a response to the user and ends the session.
* Chaining .listen() to the .speak() response keeps the session open and opens the michrophone to listen for a user's response.
* You can provide an optional string as an argument to the .listen() method, which will be used by Alexa to reprompt the user if no response was detected.
* You use this.emit(':responseReady') to send your response to a user's Alexa device.

The work that you have done in this lesson lays the foundation for a more complete skill that you can build in Codecademy's slots lesson.

**Instructions:**
Copy the code from index.js on the right into your own Lambda function (start from the alexa-skill-kit-sdk-factskill blueprint) and associate it with your Alexa skill using the ARN.

Once the configuration of the Alexa skill is complete, you can test the skill.

In the next lesson, you will learn how to ingest the user's response and act on it accordingly.

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
