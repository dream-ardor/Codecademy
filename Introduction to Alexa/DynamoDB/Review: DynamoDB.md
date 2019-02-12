## DYNAMODB

Review: DynamoDB

In this lesson, you learned how to use DynamoDB to give your skill "long-term memory" — so it can remember session attributes across sessions.

To integrate a DynamoDB table into your Lambda function, remember the following:

* We learned that adding DynamoDB to our skill takes only one line of code
* .emit(‘:responseReady’) will save updated session attributes to DynamoDB.
* To ensure that a session saves if a user quits or a session times out, include this.emit(‘:saveState’, true) in the SessionEndedRequest handler.
* Provide your Lambda function IAM permissions so it has full access to DynamoDB.

**Instructions:**
* Now that you've finished, test your skill on echosim.io here or at this link.
* Be sure to launch the session a few times and return to your DynamoDB table to see the changes.
* Challenge yourself: how could you extend this Alexa skill? Try modifying this skill so that the user can separate the deck based on which flashcards they've answered correctly, incorrectly, and what ones they have yet to study.
