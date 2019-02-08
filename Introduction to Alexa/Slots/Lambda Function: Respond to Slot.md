## SLOTS

Lambda Function: Respond to Slot

We now have access to the slot within the Lambda function. The only thing left to do is respond appropriately. If the user guesses correctly ("python"), we can congratulate them on getting it correct:

Correct! Python is the most popular language.

Conversely, if they get it incorrect, we'll repeat their guess and let them know the correct answer:

You guessed that java is the most popular. Actually, python is our most popular language.

**Instructions:**
Add an if statement after the definition of myLanguage. If the user has guessed correctly ("python"), respond to the user with the string - "Correct! Python is the most popular language."

Follow the if statement with an else statement to repeat the user's guess and let them know the correct answer.

Use this string: "You guessed that java is the most popular. Actually, python is our most popular language", but replace java with the user's guess.

**Solution:**
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
    if(myLanguage === "python") {
      this.response.speak("Correct! Python is the most popular language.")
    }
    else {
    this.response.speak("You guessed that " + myLanguage + " is the most popular. Actually, python is our most popular language");
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
