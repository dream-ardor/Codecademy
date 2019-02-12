DYNAMODB

IAM Permissions

Before we connect our finished Lambda function to our Interaction Model, we need to give the Lambda function specific permissions to read/write to our DynamoDB table.

We can add and change permissions using AWS Identity and Access Management (IAM) tools. IAM enables developers to securely control access to AWS services and resources for your users.

The permission we create will allow our Lambda function to automatically build and access a DynamoDB table when we open our skill (and even when we test it!).

**Instructions:**
Watch the video to see how to change your IAM permissions to integrate DynamoDB with your Lambda Function, or follow the steps below:

* Navigate to IAM, go to the roles page and click create new role
* For Role Type, choose Lambda
* For Permissions, choose DynamoDB full access (select it using the checkbox)
* In Review, name your role lambda_dynamodb_fullaccess
* Hit Save
