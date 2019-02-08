## SESSION ATTRIBUTES

Assigning Slot Values to Session Attributes

One good use of session attributes is to capture and store user input through slots so you can use that information at a later time. This information is sent to your Lambda function as part of the JSON response.

To get a slot value, you first need to figure out how your slot is sent in the JSON request. The following is an example JSON request for a movie recommendation skill:
```js
"request": {
    "type": "IntentRequest",
    "requestId": "EdwRequestId.d30fb1fe-8f09-4a80-ab90-b736c2959146",
    "intent": {
      "name": "SetGenreIntent",
      "slots": {
        "genres": {
          "name": "genres",
          "value": "horror"
        }
      }
    }
 ```
The structure of the JSON object tells us how to access user input. We can use the following format to set a genre session attribute to the value saved to a user slot input:

this.attributes['genre'] =  this.event.request.intent.slots.genres.value;
In this lesson we want Alexa to interpret the utterance, “Test my Ruby knowledge”, recognize “Ruby” as a slot value, and store it in the language session attribute for Alexa to use in later speech intents.

**Instructions:**
In SetMyLanguageIntent, set the language session attribute so that it equals the user’s specified language. Look at the following JSON Request Object to construct your call:
```js
"request": {
    "type": "IntentRequest",
    "requestId": "EdwRequestId.d30fb1fe-8f09-4a80-ab90-b736c2959146",
    "intent": {
      "name": "SetMyLanguageIntent",
      "slots": {
        "languages": {
          "name": "languages",
          "value": "ruby"
        }
      }
    },
```

In AnswerIntent, create a userAnswer variable and set it equal to the user’s answer. Look at the following JSON Request Object to construct your call:
```js
  "request": {
    "type": "IntentRequest",
    "requestId": "EdwRequestId.494ef95d-29c8-40a8-914c-0cc740058d53",
    "intent": {
      "name": "AnswerIntent",
      "slots": {
        "answer": {
          "name": "answer",
          "value": "length"
        }
      }
    },
```

**Solution:**
```js
'use strict';

var Alexa = require('alexa-sdk');

var flashcardsDictionary = [
  {
    question: 'How do you find the length of a string?',
    rubyAnswer: 'length',
    pythonAnswer: 'len',
    javascriptAnswer: 'length'
  },
  {
    question: 'How do you print to the console or terminal?',
    rubyAnswer: 'puts',
    pythonAnswer: 'print',
    javascriptAnswer:'console.log'
  },
  {
    question:'Are the boolean terms true and false capitalized or lowercase?',
    rubyAnswer: 'lowercase',
    pythonAnswer: 'capitalized',
    javascriptAnswer: 'lowercase'
  }];

var DECK_LENGTH = flashcardsDictionary.length;

var handlers = {

  // Open Codecademy Flashcards
  'LaunchRequest': function() {
    this.attributes['language'] = '';
    this.attributes['numberCorrect'] = 0;
    this.attributes['currentFlashcardIndex'] = 0;

    this.response
        .listen('Welcome to Flashcards. In this session, do you want to test' +
        ' your knowledge in Ruby, Python, or Javascript?').speak(
        'Which language would you like to practice?');
    this.emit(':responseReady');
  },

  'SetMyLanguageIntent': function() {

    this.attributes['language'] = this.event.request.intent.slots.languages.value;
    if (this.attributes['language'] === 'JavaScript') {
      this.attributes['language'] = 'javascript';
    }

    this.response
      .speak('Okay, I will ask you some questions about ' +
        'Ruby' + '. Here is your first question. ' + 
        AskQuestion(this.attributes))
      .listen(AskQuestion(this.attributes));

    this.emit(':responseReady');
  },

  // User gives an answer
  'AnswerIntent': function() {
    
		var userAnswer = this.event.request.intent.slots.answer.value;
    if (userAnswer === correctAnswer){
      this.attributes['numberCorrect']++;
      this.attributes['currentFlashcardIndex']++;

      this.response
        .speak('Nice job! The correct answer is ' + correctAnswer + '. You ' +
          'have gotten ' + numberCorrect + ' out of ' + DECK_LENGTH + ' ' +
          language + ' questions correct. Here is your next question. ' + AskQuestion(this.attributes))
        .listen(AskQuestion(this.attributes));
    } else {
      this.attributes['currentFlashcardIndex']++;

      this.response
        .speak('Sorry, the correct answer is ' + correctAnswer + '. You ' +
          'have gotten ' + numberCorrect + ' out of ' + DECK_LENGTH + ' ' +
          language + ' questions correct. Here is your next question. ' + 
          AskQuestion(this.attributes))
        .listen(AskQuestion(this.attributes));
    }

    this.emit(':responseReady');
  },

  // Stop
  'AMAZON.StopIntent': function() {
    this.response.speak('Ok, let\'s play again soon.');
    this.emit(':responseReady');
  },

  // Cancel
  'AMAZON.CancelIntent': function() {
    this.response.speak('Ok, let\'s play again soon.');
    this.emit(':responseReady');
  }


};

// Test my {language} knowledge
var AskQuestion = function(attributes) {
  var currentFlashcardIndex = attributes['currentFlashcardIndex'];

  if (currentFlashcardIndex >= flashcardsDictionary.length) {
    return 'No questions remaining';
  } else {
    var currentQuestion = flashcardsDictionary[currentFlashcardIndex].question;
    return 'In Ruby, ' + currentQuestion;
  }
};

exports.handler = function(event, context, callback){
  var alexa = Alexa.handler(event, context, callback);
  alexa.registerHandlers(handlers);
  alexa.execute();
};
```
    
