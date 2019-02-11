## DYNAMODB

Refactor Session Attributes

When we save session attributes to our database table, we should always store them in a well-structured and descriptive format. Currently, our session attributes aren’t specific, and while we could write several more session attribute fields to cover the information we want to save, we would find a lot of redundancies.

DynamoDB is designed to support key:value storage, with the name of our attribute being the key and what we’ve set it to becoming its value. Use bracket notation:
```js
this.attributes['yourAttribute'] = 'value';
```
Or dot notation:
```js
this.attributes.yourAttribute = 'value';
```
For our purposes, we want our skill to remember the language we’re currently working on. For each language, we want to remember the flashcard that we’re currently on and the number of flashcards we’ve gotten correct. Because of the information we want to remember from session to session, we need to create a more complex session attribute structure that allows us to work with more data.

We can extend the key:value functionality to create a session attribute object that contains nested key:value pairs. This nested structure allows us to easily read, write, and store even more information. Since we set the session attributes value to an object, DynamoDB interprets these objects as JSON.

However, we can refactor our session attributes value into an intuitive, nested object. This structure would allow us to better maintain, persist, and remember the different states, such as our progress in each language. We want to refactor the three session attributes currently in the code so that they are now part of one flashcards object.

**Instructions:**

* In the LaunchRequest function, delete the current session attributes and create a new flashcards session attribute object. Be sure to use dot syntax instead of brackets.

* Inside the object, create a 'currentLanguage' key and set its value to an empty string.

* Inside the flashcards object but below the 'currentLanguage' key, create an empty 'languages' object.

* Inside the languages object, create objects for ruby, python, and javascript. Inside each one of those objects, add keys for numberCorrect and currentFlashcardIndex. Set their values to 0.

### **My Code:**
```js
'use strict';
var Alexa = require('alexa-sdk');
var flashcardsDictionary = [{
	question: 'How do you find the length of a string?',
	rubyAnswer: 'length',
	pythonAnswer: 'len',
	javascriptAnswer: 'length'
}, {
	question: 'How do you print to the console or terminal?',
	rubyAnswer: 'puts',
	pythonAnswer: 'print',
	javascriptAnswer: 'console.log'
}, {
	question: 'Are the boolean terms true and false capitalized or lowercase?',
	rubyAnswer: 'lowercase',
	pythonAnswer: 'capitalized',
	javascriptAnswer: 'lowercase'
}];
var DECK_LENGTH = flashcardsDictionary.length;
var handlers = {
	// Open Codecademy Flashcards
	'LaunchRequest': function() {
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
		}
		this.emit(':responseReady');
	},
	'SetMyLanguageIntent': function() {
		this.attributes.flashcards.currentLanguage = this.event.request.intent.slots.languages.value;
		if (this.attributes.flashcards.currentLanguage === 'JavaScript') {
			this.attributes.flashcards.currentLanguage = 'javascript';
		}
		var currentLanguage = this.attributes.flashcards.currentLanguage
		this.response.speak('Okay, I will ask you some questions about ' + currentLanguage + '. Here is your first question. ' + AskQuestion(this.attributes)).listen(AskQuestion(this.attributes));
		this.emit(':responseReady');
	},
	// User gives an answer
	'AnswerIntent': function() {
		var currentLanguage = this.attributes.flashcards.currentLanguage;
		var currentFlashcardIndex = this.attributes.flashcards.languages[currentLanguage].currentFlashcardIndex;
		var userAnswer = this.event.request.intent.slots.answer.value;
		var languageAnswer = currentLanguage + 'Answer';
		var correctAnswer = flashcardsDictionary[currentFlashcardIndex][languageAnswer];
		if (userAnswer == correctAnswer) {
			this.attributes.flashcards.languages[currentLanguage].numberCorrect++;
			var numberCorrect = this.attributes.flashcards.languages[currentLanguage].numberCorrect;
			this.attributes.flashcards.languages[currentLanguage].currentFlashcardIndex++;
			this.response.speak('Nice job! The correct answer is ' + correctAnswer + '. You ' + 'have gotten ' + numberCorrect + ' out of ' + DECK_LENGTH + ' ' + currentLanguage + ' questions correct. Here is your next question. ' + AskQuestion(this.attributes)).listen(AskQuestion(this.attributes));
		} else {
			var numberCorrect = this.attributes.flashcards.languages[currentLanguage].numberCorrect;
			this.attributes.flashcards.languages[currentLanguage].currentFlashcardIndex++;
			this.response.speak('Sorry, the correct answer is ' + correctAnswer + '. You ' + 'have gotten ' + numberCorrect + ' out of ' + DECK_LENGTH + ' ' + currentLanguage + ' questions correct. Here is your next question. ' + AskQuestion(this.attributes)).listen(AskQuestion(this.attributes));
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
exports.handler = function(event, context, callback) {
	var alexa = Alexa.handler(event, context, callback);
	alexa.dynamoDBTableName = 'CodecademyFlashcards';
	alexa.registerHandlers(handlers);
	alexa.execute();
};
```
