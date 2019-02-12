## DYNAMODB

Linking the Lambda Function

Now that we’ve created a script that supports session attributes, let’s create our Lambda function.

The IAM work we added comes into play when you navigate to the Lambda function configuration page, where under existing role you’ll select the newly added role, lambda-dynamodb-fullaccess.

If you created a flashcards skill in the Codecademy Session Attributes Lesson, you can update your existing Lambda function. If you prefer, you can follow the steps below to create a new one.

* Update your lambda function
* Navigate to aws.amazon.com, head to your lambda service and find your CodecademyFlashcards function.
* Paste the code from index.js into the Lambda function code editor
* Under Execution Role, set the first dropdown to Choose an existing role and set the second dropdown to our newly created lambda-dynamodb-fullaccess role.
* Copy your ARN from the top of the page, navigate to developer.amazon.com, open your skill, and paste the ARN in your 
* Configuration or Endpoint section.
* Create a new lambda function
* Navigate to aws.amazon.com, head to your lambda service and create a new function named CodecademyFlashcards2
* Make sure your region is set to Northern Virginia
* Select the Fact Skill blueprint
* In the Basic information section, set the first dropdown to Choose an existing role and set the second dropdown to our newly created lambda-dynamodb-fullaccess role.
* Click on the Create Function button
* Paste the code from index.js into the Lambda function code editor
* Set the trigger for your Lambda function to Alexa Skills Kit. You can do that by clicking on the triggers tab and adding it.
* Copy your ARN from the top of the page, navigate to developer.amazon.com, open your skill, and paste the ARN in your Configuration or Endpoint section.
