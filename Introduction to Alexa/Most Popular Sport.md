## INTRODUCTION TO ALEXA

Most Popular Sport

In this project, you will add a new intent called MostPopularSportIntent.

Inside this intent, you will access a slot called sport, and check if its value is equal to "soccer". If it is equal to soccer, you should generate a response that tells the user they were correct. If the user's response does not equal "soccer", you should tell them they were incorrect, and that the correct answer is "soccer".

If you get stuck during this project, check out the project walkthrough video which can be found at the bottom of the page after the final step of the project.

**Tasks:**

Mark the tasks as complete by checking them off

1. Inside the LaunchRequest, add the following speak and reprompt:
```
Speak: Hello, what do you think is the world's most popular sport?
Reprompt: Tell me what you think is the world's most popular sport.
```
Make sure to add a line that emits your responses.

2. Inside the MostPopularSportIntent, add a line that saves the value of the sport slot to a variable called worldSport.

3. Under the variable declaration, check if the value saved to worldSport is equal to "soccer".

If it is, output the following speech: Correct! Soccer is the world's most popular sport.

4. If the variable is not correct respond with: "You guessed that SPORT is the most popular. Actually, soccer is the world's most popular sport"

5. Under the conditional block, make sure to emit your response.

6. To use this new Lambda function, you must create an interaction model with the following:
```
sport slot that checks for a few popular world sports (e.g. soccer, basketball, hockey, rugby).
MostPopularSportIntent with a few utterances that grab the user's input value from the sport slot.
```
```js
"use strict";

var Alexa = require("alexa-sdk");

var handlers = {
  'LaunchRequest': function() {
    this.speak.response("Hello,what do you think is the world's most popular sport?")
    .listen("Tell me what you think is the world's most popular sport.");
    
    this.emit(":responseReady");
    
  },

  'MostPopularSportIntent': function () {
    var worldSport = this.event.request.intent.slots.sport.value;
    if(worldSport === "soccer") {
      this.response.speak("Correct! Soccer is the world's most popular sport.");
    }
    else {
      this.response.speak("You guessed that " + worldSport + "is the most popular. Actually, soccer is the world's most popular sport");
      
      this.emit(":responseReady")
    }
  },
}

exports.handler = function(event, context, callback){
    var alexa = Alexa.handler(event, context);
    alexa.registerHandlers(handlers);
    alexa.execute();
};
```
