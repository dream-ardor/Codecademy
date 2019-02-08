## SESSION ATTRIBUTES

String Interpolation with Session Attributes

Often, you want to combine session attribute values with another string to generate a custom speech output.

Let's consider our movie genre skill. If we wanted Alexa to respond with the current genre of a movie, which has been stored in a session attribute, we could use the following to generate the speech output.
```js
'SetGenreIntent': function() {

 this.attributes['genre'] = 
 this.event.request.intent.slots.genres.value; 

 this.response.speak('Ok, so you like ' + 
 this.attributes['genre'] + ' movies.' +
 'Let me ask you a few more questions and ' + 
 'then I’ll give you my recommendation.').listen();

  this.emit(':responseReady');
}
```
We can see the interpolation in the this.response.speak speech output, where we insert the genre session attribute inside of the response.

**Instructions:**
In the SetMyLanguageIntent speech output, replace the hard-coded instance of "Ruby" with the language session attribute, making sure to use interpolation where needed.

Do the same in the AskQuestion function at the bottom of index.js.

## **My Code:**
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
        this.attributes['language'] + '. Here is your first question. ' + 
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
    return 'In' +
      this.attributes['language'] + ',' +
      currentQuestion;
  }
};

exports.handler = function(event, context, callback){
  var alexa = Alexa.handler(event, context, callback);
  alexa.registerHandlers(handlers);
  alexa.execute();
};
```
