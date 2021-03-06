## SESSION ATTRIBUTES

Create the Lambda Function

Now that we’ve added all of the functionality of session attributes, let’s create our Lambda function.

We’ve detailed the steps below, but if you need a refresher, check out this video on creating a Lambda function and this video on adding your ARN to your Alexa skill.

**Instructions:**
* Navigate to aws.amazon.com, head to your lambda service and create a new function named CodecademyFlashcards
* Make sure your region is set to Northern Virginia
* Select the Fact Skill blueprint
* Paste the code from index.js into Lambda function text editor
* Set your role to lambda_basic_execution
* Set the trigger for your Lambda function to Alexa Skills Kit. You can do that by clicking on the triggers tab and adding it.
* Grab your ARN number and navigate to developers.amazon.com, paste it in your configuration section

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

    var language = this.attributes['language'];

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
      var numberCorrect = this.attributes['numberCorrect'];
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
  var language = attributes['language'];
  var currentFlashcardIndex = attributes['currentFlashcardIndex'];

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
