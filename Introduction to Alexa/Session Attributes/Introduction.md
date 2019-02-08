## SESSION ATTRIBUTES

Introduction

In this lesson, we're going to build a Codecademy Flashcards skill and look at how you can program Alexa to remember details about your conversation within a session — the time between when you open the skill and close the skill.

Imagine you were working through a deck of vocabulary flashcards. As you progress through the deck, you keep track of which flashcards you have completed and which you have not. Also, you may keep track of the number of flashcards you have answered correctly.

In this lesson, you will add a notion of short-term memory. As a user progresses through the flashcards in your skill, you can keep track of the user's progress through the deck by keeping track of the current index and number of correct cards.

Additionally, you will add an option for users to choose the programming language for the questions in their flashcard deck.

To remember all of these things, we need to use session attributes. Session attributes allow Alexa to remember and update user-provided details throughout a session.

You can think of session attributes as being similar to variables that store information about the program, except values stored in session attributes persist throughout a session. In a later lesson, we'll talk about how you can persist attributes between sessions by writing them to a DynamoDB database (aka long-term memory).
