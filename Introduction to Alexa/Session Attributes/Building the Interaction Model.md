## SESSION ATTRIBUTES

Building the Interaction Model

Before we build the Lambda function logic for our flashcards skill, we want to build the interaction model.

To do so, we’ll navigate to developer.amazon.com and use the Alexa Skill Builder. If you are unfamiliar with this process or need a refresher, check out these videos: how to create a skill and how to build an interaction model.

Create an interaction model
* Add a custom slot named languages with the following slot values: ruby, python, javascript.
* Add a custom slot named answer with the following slot values: length, len, print, puts, console.log, capitalized, lowercase.
* Create a custom intent named SetMyLanguageIntent
* Add the following utterances to SetMyLanguageIntent: Test my {languages} knowledge and Practice {languages}
* Create a custom intent named AnswerIntent
* Add the following utterances to AnswerIntent: I think it's {answer} and Is it {answer}
