## SESSION ATTRIBUTES

Session Attributes and Variables

In the last exercise, we used interpolation to create a speech output. Though, accessing session attributes and slot values can get messy. In this exercise we'll see how variables can help us clean up our code.

Look at how our speech output changes when we add a variable to our intent:
```js
'CurrentGenreIntent': function() {

var genre = this.event.request.intent.slots.genres.value;

this.attributes['genre'] = genre;

this.response.listen('Ok, so you like ' + 
genre + ' movies. Let me ask you a few ' + 
'more questions and then I’ll give you ' +
'my recommendation.");

this.emit(':responseReady');

}
```
By saving our session attributes to the genre variable, we have refactored the string in our speech output to be more readable.

**Instructions:**
In the SetMyLanguageIntent and AskQuestion functions, save the user's language:

In both functions, create a variable called language and set it equal to the 'language' session attribute.

In the SetMyLanguageIntent and AskQuestion functions, replace the session attributes that are in the speech outputs with the variable language.

In AnswerIntent, save the user's language:

Underneath the userAnswer variable, save the 'language' session attribute to a language variable.
Then create a languageAnswer variable that concatenates language and 'Answer'.

Underneath the languageAnswer variable, create two new variables called currentFlashcardIndex and correctAnswer.

Set currentFlashcardIndex equal to the current flashcard index attribute.
Set correctAnswer variable equal to the correct answer for the current language. You'll need to make a call to the flashcardsDictionary. Use the currentFlashcardIndex variable to select the appropriate question, and the languageAnswer variable to get the corresponding answer.

In both parts of the conditional statement within AnswerIntent, create a variable called numberCorrect and set the 'numberCorrect' session attribute as its value.

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
    var language = this.attributes['language'];

    if (this.attributes['language'] === 'JavaScript') {
      this.attributes['language'] = 'javascript';
    }

    this.response
      .speak('Okay, I will ask you some questions about ' +
        language + '. Here is your first question. ' + 
        AskQuestion(this.attributes))
      .listen(AskQuestion(this.attributes));

    this.emit(':responseReady');
  },

  // User gives an answer
  'AnswerIntent': function() {
    var userAnswer = this.event.request.intent.slots.answer.value;
    var language = this.attributes['language'];
    var languageAnswer = language + 'Answer';
    var currentFlashcardIndex = this.attributes['currentFlashcardIndex'];
		var correctAnswer = flashcardsDictionary[currentFlashcardIndex][languageAnswer];


    if (userAnswer === correctAnswer){
      this.attributes['numberCorrect']++;
      var numberCorrect = this.attributes['numberCorrect'];
      this.attributes['currentFlashcardIndex']++;

      this.response
        .speak('Nice job! The correct answer is ' + correctAnswer + '. You ' +
          'have gotten ' + numberCorrect + ' out of ' + DECK_LENGTH + ' ' +
          language + ' questions correct. Here is your next question. ' + AskQuestion(this.attributes))
        .listen(AskQuestion(this.attributes));
    } else {
      this.attributes['currentFlashcardIndex']++;
      var numberCorrect = this.attributes['numberCorrect'];
      
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
  var language = this.attributes['language'];

  if (currentFlashcardIndex >= flashcardsDictionary.length) {
    return 'No questions remaining';
  } else {
    var currentQuestion = flashcardsDictionary[currentFlashcardIndex].question;
    return 'In ' + language + ', ' + currentQuestion;
  }
};

exports.handler = function(event, context, callback){
  var alexa = Alexa.handler(event, context, callback);
  alexa.registerHandlers(handlers);
  alexa.execute();
};
```
