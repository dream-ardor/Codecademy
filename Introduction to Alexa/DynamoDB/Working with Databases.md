## DYNAMODB

Working with Databases

In this lesson, we’re going to use a DynamoDB database so our Alexa Skill will remember things from one session to the next.

A database holds and organizes information so that it can be easily accessed, managed, and updated. Databases save information sent from the frontend of our skill and then can respond with that information later. Our Lambda function manages that relationship in the backend.

One common use of a database is to store emails. When you search for an email, your email provider (Gmail, Yahoo mail, etc.) queries a database and responds with the emails that match your query.

**Instructions:**
The diagram to the right explains the interactions between our interaction model, Lambda function, and DynamoDB database.

Let's walk through the diagram in the context of our flashcards skill:

* The user opens the flashcards skill on their Alexa device, and makes progress through the deck.
* Throughout the session, the user's progress is tracked through slots and session attributes in the Lambda function.
* When the user ends their session, the Lambda function writes their progress to DynamoDB.
