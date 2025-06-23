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
