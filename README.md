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

***

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

1. A company is implementing an application on Amazon EC2 instances. The application needs to process incoming transactions. When the application detects a transaction that is not valid, the application must send a chat message to the company's support team. To send the message, the application needs to retrieve the access token to authenticate by using the chat API.
A developer needs to implement a solution to store the access token. The access token must be encrypted at rest and in transit. The access token must also be accessible from other AWS accounts.
Which solution will meet these requirements with the LEAST management overhead?
<ol type="A">
 <li>Use an AWS Systems Manager Parameter Store SecureString parameter that uses an AWS Key Management Service (AWS KMS) AWS managed key to store the access token. Add a resource-based policy to the parameter to allow access from other accounts. Update the IAM role of the EC2 instances with permissions to access Parameter Store. Retrieve the token from Parameter Store with the decrypt flag enabled. Use the decrypted access token to send the message to the chat.</li>
 <li>Encrypt the access token by using an AWS Key Management Service (AWS KMS) customer managed key. Store the access token in an Amazon DynamoDB table. Update the IAM role of the EC2 instances with permissions to access DynamoDB and AWS KMS. Retrieve the token from DynamoDDecrypt the token by using AWS KMS on the EC2 instances. Use the decrypted access token to send the message to the chat.</li>
 <li>Use AWS Secrets Manager with an AWS Key Management Service (AWS KMS) customer managed key to store the access token. Add a resource-based policy to the secret to allow access from other accounts. Update the IAM role of the EC2 instances with permissions to access Secrets Manager. Retrieve the token from Secrets Manager. Use the decrypted access token to send the message to the chat.
</li>
 <li>Encrypt the access token by using an AWS Key Management Service (AWS KMS) AWS managed key. Store the access token in an Amazon S3 bucket. Add a bucket policy to the S3 bucket to allow access from other accounts. Update the IAM role of the EC2 instances with permissions to access Amazon S3 and AWS KMS. Retrieve the token from the S3 bucket. Decrypt the token by using AWS KMS on the EC2 instances. Use the decrypted access token to send the massage to the chat.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  C
</details>

***

2. A company is running Amazon EC2 instances in multiple AWS accounts. A developer needs to implement an application that collects all the lifecycle events of the EC2 instances. The application needs to store the lifecycle events in a single Amazon Simple Queue Service (Amazon SQS) queue in the company's main AWS account for further processing.
Which solution will meet these requirements?

<ol type="A">
 <li>Configure Amazon EC2 to deliver the EC2 instance lifecycle events from all accounts to the Amazon EventBridge event bus of the main account. Add an EventBridge rule to the event bus of the main account that matches all EC2 instance lifecycle events. Add the SQS queue as a target of the rule.</li>
 <li>Use the resource policies of the SQS queue in the main account to give each account permissions to write to that SQS queue. Add to the Amazon EventBridge event bus of each account an EventBridge rule that matches all EC2 instance lifecycle events. Add the SQS queue in the main account as a target of the rule.</li>
 <li>Write an AWS Lambda function that scans through all EC2 instances in the company accounts to detect EC2 instance lifecycle changes. Configure the Lambda function to write a notification message to the SQS queue in the main account if the function detects an EC2 instance lifecycle change. Add an Amazon EventBridge scheduled rule that invokes the Lambda function every minute.</li>
 <li>Configure the permissions on the main account event bus to receive events from all accounts. Create an Amazon EventBridge rule in each account to send all the EC2 instance lifecycle events to the main account event bus. Add an EventBridge rule to the main account event bus that matches all EC2 instance lifecycle events. Set the SQS queue as a target for the rule.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  D
</details>

***

262. A company wants to test its web application more frequently. The company deploys the application by using a separate AWS CloudFormation stack for each environment. The company deploys the same CloudFormation template to each stack as the application progresses through the development lifecycle.

A developer needs to build in notifications for the quality assurance (QA) team. The developer wants the notifications to occur for new deployments in the final preproduction environment.

Which solution will meet these requirements?
<ol type="A">
 <li>Create an Amazon Simple Notification Service (Amazon SNS) topic. Subscribe the QA team to the Amazon SNS topic. Update the CloudFormation stack options to point to the SNS topic in the pre-production environment.</li>
 <li>Create an AWS Lambda function that notifies the QA team. Create an Amazon EventBridge rule to invoke the Lambda function on the default event bus. Filter the events on the CloudFormation service and on the CloudFormation stack Amazon Resource Name (ARN).</li>
 <li>Create an Amazon CloudWatch alarm that monitors the metrics from CloudFormation. Filter the metrics on the stack name and the stack status. Configure the CloudWatch alarm to notify the QA team.</li>
 <li>Create an AWS Lambda function that notifies the QA team. Configure the event source mapping to receive events from CloudFormation. Specify the filtering values to limit invocations to the desired CloudFormation stack.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  A
</details>

***

269. A developer is optimizing an AWS Lambda function and wants to test the changes in production on a small percentage of all traffic. The Lambda function serves requests to a RE ST API in Amazon API Gateway. The developer needs to deploy their changes and perform a test in production without changing the API Gateway URL.

Which solution will meet these requirements?
<ol type="A">
 <li>Define a function version for the currently deployed production Lambda function. Update the API Gateway endpoint to reference the new Lambda function version. Upload and publish the optimized Lambda function code. On the production API Gateway stage, define a canary release and set the percentage of traffic to direct to the canary release. Update the API Gateway endpoint to use the $LATEST version of the Lambda function. Publish the API to the canary stage.</li>
 <li>Define a function version for the currently deployed production Lambda function. Update the API Gateway endpoint to reference the new Lambda function version. Upload and publish the optimized Lambda function code. Update the API Gateway endpoint to use the $LATEST version of the Lambda function. Deploy a new API Gateway stage.</li>
 <li>Define an alias on the $LATEST version of the Lambda function. Update the API Gateway endpoint to reference the new Lambda function alias. Upload and publish the optimized Lambda function code. On the production API Gateway stage, define a canary release and set the percentage of traffic to direct to the canary release. Update the API Gateway endpoint to use the $LATEST version of the Lambda function. Publish to the canary stage.</li>
 <li>Define a function version for the currently deployed production Lambda function. Update the API Gateway endpoint to reference the new Lambda function version. Upload and publish the optimized Lambda function code. Update the API Gateway endpoint to use the $LATEST version of the Lambda function. Deploy the API to the production API Gateway stage.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  C
</details>

***

302. A company runs a serverless application on AWS. The application includes an AWS Lambda function. The Lambda function processes data and stores the data in an Amazon RDS for PostgreSQL database. A developer created a user credentials in the database for the application.

The developer needs to use AWS Secrets Manager to manage the user credentials. The password must to be rotated on a regular basis. The solution needs to ensure that there is high availability and no downtime for the application during secret rotation.

What should the developer do to meet these requirements?
<ol type="A">
 <li>Configure managed rotation with the single user rotation strategy.</li>
 <li>Configure managed rotation with the alternating users rotation strategy.</li>
 <li>Configure automatic rotation with the single user rotation strategy.</li>
 <li>Configure automatic rotation with the alternating users rotation strategy.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  D
</details>

***

303. A company runs an application on AWS. The application consists of a static website that is hosted on Amazon S3. The application includes Amazon API Gateway APIs that invoke AWS Lambda functions. During a period of high traffic on the application, application users reported that the application was slow at irregular intervals. There were no failed requests.

A developer needs to find the slow executions across all the Lambda functions.

Which solution will meet these requirements?

<ol type="A">
 <li>Perform a query across all the Lambda function log groups by using Amazon CloudWatch Logs Insights. Filter on type of report and sort descending by Lambda function execution duration.</li>
 <li>Enable AWS CloudTrail Insights on the account where the Lambda functions are running. After CloudTrail Insights has finished processing, review CloudTrail Insights to find the anomalous functions.</li>
 <li>Enable AWS X-Ray for all the Lambda functions. Configure an X-Ray insight on a new group that includes all the Lambda functions. After the X-Ray insight has finished processing, review the X-Ray logs.</li>
 <li>Set up AWS Glue to crawl through the logs in Amazon CloudWatch Logs for the Lambda functions. Configure an AWS Glue job to transform the logs into a structured format and to output the logs into Amazon S3. Use the Amazon CloudWatch dashboard to visualize the slowest functions based on the duration.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  C
</details>

***

359. A company has an application that uses an AWS Lambda function to process data. A developer must implement encryption in transit for all sensitive configuration data, such as API keys, that is stored in the application. The developer creates an AWS Key Management Service (AWS KMS) customer managed key.

What should the developer do next to meet the encryption requirement?
<ol type="A">
 <li>Create parameters of the String type in AWS Systems Manager Parameter Store. For each parameter, specify the KMS key ID to encrypt the parameter in transit. Reference the GetParameter API call in the Lambda environment variables.</li>
 <li>Create secrets in AWS Secrets Manager by using the customer managed KMS key. Create a new Lambda function and set up a Lambda layer. Configure the Lambda layer to retrieve the values from Secrets Manager.</li>
 <li>Create objects in Amazon S3 for each sensitive data field. Specify the customer managed KMS key to encrypt the object. Configure the Lambda function to retrieve the objects from Amazon S3 during data processing.</li>
 <li>Create encrypted Lambda environment variables. Specify the customer managed KMS key to encrypt the variables. Enable encryption helpers for encryption in transit. Grant permission to the Lambda function's execution role to access the KMS key.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  D
</details>

***

451. A developer is using an AWS Lambda function to process data. The developer needs to extract custom metrics about processing times from the Lambda logs. The developer needs to analyze the metrics, set alarms, and detect issues in real time.

Which solution will meet these requirements?
<ol type="A">
 <li>Publish custom metric data to AWS CloudTrail by using the PutMetricData API operation. Classify and collect the metrics. Create graphs and alarms in CloudTrail for the custom metrics.
</li>
 <li>Use the open source client libraries provided by Amazon to generate the logs in the Amazon CloudWatch embedded metric format. Use CloudWatch to create the required graphs and alarms for the custom metrics.</li>
 <li>Use Amazon CloudWatch Logs Insights to create custom metrics by querying the logs that come from the Lambda function. Use CloudWatch to create the required graphs and alarms for the custom metrics.</li>
 <li>Create an Amazon Kinesis data stream to stream log events in real time from Lambda. Specify an Amazon S3 bucket as the destination for the Kinesis data stream. Use Amazon CloudWatch to visualize the log data and to set alarms.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  B
</details>

***

463. An application is experiencing performance issues based on increased demand. This increased demand is on read-only historical records pulled from an Amazon RDS-hosted database with custom views and queries. A developer must improve performance without changing the database structure.

Which approach will improve performance and MINIMIZE management overhead?
<ol type="A">
<li>Deploy Amazon DynamoDB, move all the data, and point to DynamoDB.</li>
<li>Deploy Amazon ElastiCache (Redis OSS) and cache the data for the application.</li>
<li>Deploy Memcached on Amazon EC2 and cache the data for the application.</li>
<li>Deploy Amazon DynamoDB Accelerator (DAX) on Amazon RDS to improve cache performance.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  B
</details>

***

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

***

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

***

548. A developer is creating a new application that will give users the ability to upload documents to Amazon S3. The contents of the documents must not be accessible to any third party.

Which type of encryption will meet this requirement?
<ol type="A">
 <li>Client-side encryption by using the S3 Encryption Client with a Raw RSA wrapping key that is stored on the user’s device</li>
 <li>Server-side encryption with S3 managed keys (SSE-S3)</li>
 <li>Server-side encryption with AWS KMS keys (SSE-KMS)</li>
 <li>Dual-layer server-side encryption with AWS KMS keys (DSSE-KMS)</li>
</ol>
<details><summary>Show Correct Answer</summary>
  C
</details>

***
