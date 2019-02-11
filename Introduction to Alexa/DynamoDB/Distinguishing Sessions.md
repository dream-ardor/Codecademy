## DYNAMODB

Distinguishing Sessions

Now that we have saved the session state, let's use it to deliver a different response to a first time user versus a returning user.

For returning users, the session attributes are retrieved from the database automatically, are available for use in the current session, and can be accessed in the same way you have been, like:
```js
var myLanguage = this.attributes['currentLanguage'];
```
Checking for New Users

It is good skill design practice to check for new users and deliver an introductory response as compared to returning users — this is similar to the sign-up flow when you first open a mobile app.

To determine if the user is new, we can check if the attributes key in the JSON request is empty. If it is, we can assume that the user has never opened the skill. The following syntax checks to see if an object is empty by checking the length:
```js
Object.keys(this.attributes).length === 0
```
If the attributes object is not empty then we can assume it is not the first time that the user has launched the skill. So, we can generate a different response that welcomes them back.
```js
if (Object.keys(this.attributes).length === 0) {
  this.attributes['currentIndex'] = 0;
  this.response.speak('Welcome to Codecademy!' 
  + 'What is your name?');

} else {
  this.response.speak('Welcome back!' +
 'Are you ready to start where you ' +
 'left off?');
}
```
In the example above, we provide two different responses for users who are new or returning.

**Instructions:**
In the LaunchRequest, write a conditional statement that will check to see if it’s a user’s first time opening this skill:

if the attributes object is empty, use the existing code to initialize the flashcards session attributes
make an an empty else block for now
Make sure you leave the ‘:responseReady’ emit outside of the conditional statement.

If it’s the first time a user opens the skill, have Alexa .speak:

'Welcome to Flashcards. Do you want to test your knowledge in Ruby, Python, or Javascript?'
and .listen with:
```
'Which language would you like to practice?'
```
If it’s a later session, have Alexa .speak with:
```
'Welcome back to Flashcards. You are currently working on ' + currentLanguage + '. You\'re on question ' + currentFlashcardIndex + ' and have answered ' + numberCorrect + ' correctly.' + ' Do you want to test your knowledge in Ruby, Python, or Javascript?'
```
and .listen with:
```
'Which language would you like to practice?'
```
You may have noticed that we included some variables in the 'else' statement speech output. So let’s define them! You will create variables for currentLanguage, currentFlashcardIndex, and numberCorrect.

In the else statement, create a currentLanguage variable and set it equal to the value of the currentLanguage key in our flashcards session attribute object.

Set currentFlashcardIndex and numberCorrectto the corresponding values inside the flashcards.languages object.

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
    if (Object.keys(this.attributes).length === 0) {
      this.attributes.flashcards = {
        'currentLanguage': '',
        'languages': {
          'ruby': {
            'numberCorrect': 0,
            'currentFlashcardIndex': 0
          },
          'python': {
            'numberCorrect': 0,
            'currentFlashcardIndex': 0
          },
          'javascript': {
            'numberCorrect': 0,
            'currentFlashcardIndex': 0
          }
        }
      };
      this.response
        .speak('Welcome to Flashcards. Do you want to test your knowledge in Ruby, Python, or Javascript?')
        .listen('Which language would you like to practice?');
      
    } else {
      var currentLanguage = this.attributes.flashcards.currentLanguage;
      var numberCorrect = this.attributes.flashcards.languages[currentLanguage].numberCorrect;
			var currentFlashcardIndex = this.attributes.flashcards.languages[currentLanguage].currentFlashcardIndex;

      this.response
        .speak('Welcome back to Flashcards. You are currently working on ' + currentLanguage + '. You\'re on question ' + currentFlashcardIndex + ' and have answered ' + numberCorrect + ' correctly.' + ' Do you want to test your knowledge in Ruby, Python, or Javascript?')
        .listen('Which language would you like to practice?');
    }

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
  },

  // Save state
  'SessionEndedRequest': function() {
    console.log('session ended!');
    this.emit(':saveState', true);
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
  alexa.dynamoDBTableName = 'CodecademyFlashcards';
  alexa.registerHandlers(handlers);
  alexa.execute();
};
```
