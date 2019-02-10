## DYNAMODB

Building the Interaction Model

In this lesson, we are going to create a flashcards skill that saves your progress, including the language you’re working on, the current card, and how many you have gotten correct. We’re going to use DynamoDB to store this information, so we can retrieve it when we open up the skill and continue from where we left off.

Before we update the Lambda function logic to include saving to DynamoDB, we want to build the interaction model.

If you created a flashcards skill in the Codecademy Session Attributes Lesson, you can skip this exercise, and use your existing flashcards interaction model with the Lambda function that you will build in this lesson.

### Interaction Model

To build your interaction model, navigate to developer.amazon.com and use the Alexa Skill Builder. If you are unfamiliar with this process or need a refresher, check out these videos: how to create a skill and how to build an interaction model.

If you would like to skip the steps below, use the JSON version of the final interaction model as a guide. In the Skill Builder, you can click on the JSON Editor button and paste the JSON.

### Intents and Utterances

* Add a custom slot named languages with the following slot values: ruby, python, javascript.
* Add a custom slot named answer with the following slot values: length, len, print, puts, console.log, capitalized, lowercase.
* Create a custom intent named SetMyLanguageIntent
* Add the following utterances to SetMyLanguageIntent: 'Test my {languages} knowledge' and'`Practice {languages}'
* Create a custom intent named AnswerIntent
* Add the following utterances to AnswerIntent: 'I think it's {answer}' and 'Is it {answer}'
