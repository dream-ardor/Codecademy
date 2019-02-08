## SLOTS

Lambda Function: Read Slot

We saw how slots are sent within the JSON request from Alexa to the Lambda function. Now we need to modify our Lambda function to read the slot values.

Within the Alexa-SDK, the request JSON is available as an object. You can access this object using this.event.request.

In the previous exercise, we saw that the JSON request containing our slot looked like this:
```
"intent": {
    "name": "LanguageIntent",
    "slots": {
        "language": {
            "name": "language",
            "value": "ruby"
         }
     }
}
```
You can access the input using the following syntax:

this.event.request.intent.slots.yourSlotName.value

In the JSON example above, we can access our user's language response value with the following

this.event.request.intent.slots.language.value

**Instructions:**
In the index.js file to the right, define a variable within the LanguageIntent called myLanguage. Assign it the slot value passed in via the JSON object.

**My Code:**
```js
"use strict";

var Alexa = require("alexa-sdk");

var handlers = {
  'LaunchRequest': function() {
    this.response.speak("Hello, Welcome to Codecademy. What do you think is Codecademy's most popular language?").listen("Tell me what you think is Codecademy's most popular language.");
    this.emit(':responseReady');
  },

  'LanguageIntent': function () {
    var myLanguage = this.event.request.intent.slots.language.value
    this.emit(':responseReady');
  }
}

exports.handler = function(event, context, callback){
    var alexa = Alexa.handler(event, context);
    alexa.registerHandlers(handlers);
    alexa.execute();
};
```
