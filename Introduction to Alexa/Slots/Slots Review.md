## SLOTS

Slots Review

You have learned how to use slots to pass a user response to our skill's Lambda function.

* Slots are used like variables in user utterances.
* There are two types of slots: built-in and custom.
* You must provide a list of sample values for your custom slots.
* A slot's sample values improves the chances of Alexa getting the user input accurately.
* User response slot values are passed through a JSON from Alexa to your Lambda function.
* You can access user input values from Alexa's JSON request using the following:
this.event.request.intent.slots.yourSlotName.value

As a user of the Codecademy skill, you will now know whether your guess to the question was correct or not.

Try creating a working version of the updated skill within your Amazon account.

**Instructions:**

Copy the code from index.js on the right into your existing Lambda function (or new one if you are starting from scratch, use the alexa-skill-kit-sdk-factskill blueprint). Make sure the Lambda function is associated with your Alexa skill using the ARN.

Once the configuration of the Alexa skill is complete, you can test the skill.

In the next lesson, you will learn how to keep track of user stats and information between sessions.

```js
"use strict";

var Alexa = require("alexa-sdk");

var handlers = {
  'LaunchRequest': function() {
    this.response.speak("Hello, Welcome to Codecademy. What do you think is Codecademy's most popular language?").listen("Tell me what you think is Codecademy's most popular language.");
    this.emit(':responseReady');
  },

  'LanguageIntent': function () {
    var myLanguage = this.event.request.intent.slots.language.value;
    if (myLanguage == "python") {
        this.response.speak("Correct! Python is the most popular language.");
    }
    else {
        this.response.speak("You guessed that " + myLanguage + " is the most popular. Actually, Python is our most popular language");
    }
    this.emit(':responseReady');
  }
}

exports.handler = function(event, context, callback){
    var alexa = Alexa.handler(event, context);
    alexa.registerHandlers(handlers);
    alexa.execute();
};
```
