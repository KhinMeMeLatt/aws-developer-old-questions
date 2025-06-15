# aws-developer-old-questions
## Old Question 1

21. A developer needs to write an AWS CloudFormation template on a local machine and deploy a CloudFormation stack to AWS.
What must the developer do to complete these tasks?

<ol type="A">
 <li>Install the AWS CLI. Configure the AWS CLI by using an IAM user name and password.</li>
 <li>Install the AWS CLI. Configure the AWS CLI by using an SSH key.</li>
 <li>Install the AWS CLI. Configure the AWS CLI by using an IAM user access key and secret key.</li>
 <li>Install an AWS software development kit (SDK). Configure the SDK by using an X.509 certificate.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  C
</details>

22. A developer is working on a web application that runs on Amazon Elastic Container Service (Amazon ECS) and uses an Amazon DynamoDB table to store data.
The application performs a large number of read requests against a small set of the table data.
How can the developer improve the performance of these requests? (Choose two.)

<ol type="A">
 <li>Create an Amazon ElastiCache cluster. Configure the application to cache data in the cluster.</li>
 <li>Create a DynamoDB Accelerator (DAX) cluster. Configure the application to use the DAX cluster for DynamoDB requests.</li>
 <li>Configure the application to make strongly consistent read requests against the DynamoDB table.</li>
 <li>Increase the read capacity of the DynamoDB table.</li>
 <li>Enable DynamoDB adaptive capacity.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  A, B
</details>

## Old Question 2
502. A company generates SSL certificates from a third-party provider. The company imports the certificates into AWS Certificate Manager (ACM) to use with public web applications.

A developer must implement a solution to notify the company’s security team 90 days before an imported certificate expires. The company already has configured an Amazon Simple Queue Service (Amazon SQS) queue. The company also has configured an Amazon Simple Notification Service (Amazon SNS) topic that has the security team’s email address as a subscriber.

Which solution will provide the security team with the required notification about certificates?

<ol type="A">
 <li>Create an Amazon EventBridge rule that specifies the ACM Certificate Approaching Expiration event type. Set the SNS topic as the EventBridge rule’s target.</li>
 <li>Create an AWS Lambda function to search for all certificates that are expiring within 90 days. Program the Lambda function to send each identified certificate’s Amazon Resource Name (ARN) in a message to the SQS queue.</li>
 <li>Create an AWS Step Functions workflow that is invoked by each certificate’s expiration notification from AWS CloudTrail. Create an AWS Lambda function to send each certificate's Amazon Resource Name (ARN) in a message to the SQS queue.</li>
 <li>Configure AWS Config with the acm-certificate-expiration-check managed rule to run every 24 hours. Create an Amazon EventBridge rule that includes an event pattern that specifies the Config Rules Compliance Change detail type and the configured rule. Set the SNS topic as the EventBridge rule’s target.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  A
</details>

465. A company’s AWS accounts are in an organization in AWS Organizations. An application in Account A uses environment variables that are stored as parameters in AWS Systems Manager Parameter Store. A developer is creating a new application in Account B that needs to use the same environment variables.

The application in Account B needs access to the parameters in Account A without duplicating the parameters into Account B.

Which solution will meet these requirements with the LEAST operational overhead?

<ol type="A">
 <li>Configure the application in Account B to use credentials for an IAM user in AccountA that has access to the parameters.</li>
 <li>Create an assumable IAM role in Account A. Grant the role the permission to access the parameters.</li>
 <li>Configure cross-account resource sharing for the parameters by using AWS Resource Access Manager (AWS RAM).</li>
 <li>Write a script that stores the parameter values in a private Amazon S3 bucket that both accounts can access.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  C
</details>
