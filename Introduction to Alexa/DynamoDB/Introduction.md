## DYNAMODB

Introduction

Once you have session attributes that persist throughout a session, it’s helpful to save them to a database. The information that is saved within a session can be accessed in subsequent sessions.

Database Use-cases for Alexa

Imagine you wanted to greet a user with their name every time they opened your skill. The database can save the name of a user between session, so you don't have to ask them at the beginning of each session.
You can use a database to deliver different responses to first-time users, and custom responses to recurring visitors.
In this lesson, you will learn how to persist progress through a deck of flashcards using an AWS DynamoDB database. This will allow us to add long-term memory to a flashcards skill, so a user can resume from where they left off.

Regardless of your familiarity with databases, Alexa SDK's built-in integration with DynamoDB makes it possible to keep track of user progress between sessions with a single line of code.
