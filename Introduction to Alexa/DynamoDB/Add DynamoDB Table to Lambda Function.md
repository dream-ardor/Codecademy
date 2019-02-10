## DYNAMODB

Add DynamoDB Table to Lambda Function

Before you can save something to DynamoDB, you need to create a table. A database table is a space for storing a user's information.

The Alexa NodeJS SDK makes it simple to create a database table from within the Lambda function — it just takes one line of code:
```js
alexa.dynamoDBTableName = 'YourTableName';
```
We will add this line of code in the exports.handler method since this is the first method that is executed when a user opens an Alexa skill, and is a good place to make sure our database table is ready for reading and writing.

The first time the code above is called, Alexa will create the table. Subsequent calls will make the table available for reading and writing.

Also, you don't need to worry about the notion of different users, because the Alexa SDK handles that by creating a row for each unique user.

**Instructions:**
* Add a DynamoDB table to the exports.handler() function, with the table name 'CodecademyFlashcards'.

* Make sure to add it before the line: alexa.execute();, or else the rest of the code will run and the table will not be created.

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

    this.emit(':responseReady');
  },

  'SetMyLanguageIntent': function() {
    this.attributes.flashcards.currentLanguage = this.event.request.intent.slots.languages.value;
    if (this.attributes.flashcards.currentLanguage === 'JavaScript') {
      this.attributes.flashcards.currentLanguage = 'javascript';
    }
    var currentLanguage = this.attributes.flashcards.currentLanguage

    this.response
      .speak('Okay, I will ask you some questions about ' +
        currentLanguage + '. Here is your first question. ' + 
        AskQuestion(this.attributes))
      .listen(AskQuestion(this.attributes));

    this.emit(':responseReady');
  },

  // User gives an answer
  'AnswerIntent': function() {
    var currentLanguage = this.attributes.flashcards.currentLanguage;
    var currentFlashcardIndex = this.attributes.flashcards.languages[currentLanguage].currentFlashcardIndex;
    var userAnswer = this.event.request.intent.slots.answer.value;
    var languageAnswer = currentLanguage + 'Answer';
    var correctAnswer = flashcardsDictionary[currentFlashcardIndex][languageAnswer];

    if (userAnswer == correctAnswer){
      this.attributes.flashcards.languages[currentLanguage].numberCorrect++;
      var numberCorrect = this.attributes.flashcards.languages[currentLanguage].numberCorrect;
      this.attributes.flashcards.languages[currentLanguage].currentFlashcardIndex++;
      this.response
        .speak('Nice job! The correct answer is ' + correctAnswer + '. You ' +
          'have gotten ' + numberCorrect + ' out of ' + DECK_LENGTH + ' ' +
          currentLanguage + ' questions correct. Here is your next question. ' + AskQuestion(this.attributes))
        .listen(AskQuestion(this.attributes));
    } else {
      var numberCorrect = this.attributes.flashcards.languages[currentLanguage].numberCorrect;
      this.attributes.flashcards.languages[currentLanguage].currentFlashcardIndex++;
      this.response
        .speak('Sorry, the correct answer is ' + correctAnswer + '. You ' +
          'have gotten ' + numberCorrect + ' out of ' + DECK_LENGTH + ' ' +
          currentLanguage + ' questions correct. Here is your next question. ' + 
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
  var currentLanguage = attributes.flashcards.currentLanguage;
  console.log('currentLanguage: ' + currentLanguage);
  console.log('flashcards: ');
  console.log(attributes.flashcards);
  var currentFlashcardIndex = attributes.flashcards.languages[currentLanguage].currentFlashcardIndex;
  console.log('currentFlashcardIndex: ' + currentFlashcardIndex);

  if (currentFlashcardIndex >= flashcardsDictionary.length) {
    return 'No questions remaining';
  } else {
    var currentQuestion = flashcardsDictionary[currentFlashcardIndex].question;
    return 'In ' + currentLanguage + ', ' + currentQuestion;
  }
};

exports.handler = function(event, context, callback){
  var alexa = Alexa.handler(event, context, callback);
  // Add Table Here:
  alexa.dynamoDBTableName = 'CodecademyFlashcards';

  alexa.registerHandlers(handlers);
  alexa.execute();
};
```
