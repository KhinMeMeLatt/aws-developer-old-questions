# aws-developer-old-questions
## Old Question 1

11. A developer creates a customer managed key for multiple AWS users to encrypt data in Amazon S3. The developer configures Amazon Simple Notification
Service (Amazon SNS) to publish a message if key deletion is scheduled. The developer needs to preserve any SNS messages that cannot be delivered so that those messages can be reprocessed.
Which AWS service or feature should the developer use to meet this requirement?

<ol type="A">
 <li>Amazon Simple Email Service (Amazon SES)</li>
 <li>AWS Lambda</li>
 <li>Amazon Simple Queue Service (Amazon SQS)</li>
 <li>Amazon CloudWatch alarm</li>
</ol>
<details><summary>Show Correct Answer</summary>
  C
</details>

***

14. A company is using AWS Elastic Beanstalk to deploy a three-tier application. The application uses an Amazon RDS DB instance as the database tier. The company wants to decouple the DB instance from the Elastic Beanstalk environment.
Which combination of steps should a developer lake to meet this requirement? (Choose two.)

<ol type="A">
 <li>Create a new Elastic Beanstalk environment that connects to the DB instance.</li>
 <li>Create a new DB instance from a snapshot of the previous DB instance.</li>
 <li>Use the Elastic Beanstalk CLI to decouple the DB instance.</li>
 <li>Use the AWS CLI to decouple the DB instance.</li>
 <li>Modify the current Elastic Beanstalk environment to connect to the DB instance.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  A, B
</details>

***

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

153. A company uses a custom root certificate authority certificate chain (Root CA Cert) that is 10 KB in size to generate SSL certificates for its on-premises HTTPS endpoints. One of the company’s cloud-based applications has hundreds of AWS Lambda functions that pull data from these endpoints. A developer updated the trust store of the Lambda execution environment to use the Root CA Cert when the Lambda execution environment is initialized. The developer bundled the Root CA Cert as a text file in the Lambda deployment bundle.

After 3 months of development, the Root CA Cert is no longer valid and must be updated. The developer needs a more efficient solution to update the Root CA Cert for all deployed Lambda functions. The solution must not include rebuilding or updating all Lambda functions that use the Root CA Cert. The solution must also work for all development, testing, and production environments. Each environment is managed in a separate AWS account.

Which combination of steps should the developer take to meet these requirements MOST cost-effectively? (Choose two.)

<ol type="A">
 <li>Store the Root CA Cert as a secret in AWS Secrets Manager. Create a resource-based policy. Add IAM users to allow access to the secret.</li>
 <li>Store the Root CA Cert as a SecureString parameter in AWS Systems Manager Parameter Store. Create a resource-based policy. Add IAM users to allow access to the policy.</li>
 <li>Store the Root CA Cert in an Amazon S3 bucket. Create a resource-based policy to allow access to the bucket.</li>
 <li>Refactor the Lambda code to load the Root CA Cert from the Root CA Cert’s location. Modify the runtime trust store inside the Lambda function handler.</li>
 <li>Refactor the Lambda code to load the Root CA Cert from the Root CA Cert’s location. Modify the runtime trust store outside the Lambda function handler.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  A, E
</details>

***
260. A developer is writing an application that will retrieve sensitive data from a third-party system. The application will format the data into a PDF file. The PDF file could be more than 1 MB. The application will encrypt the data to disk by using AWS Key Management Service (AWS KMS). The application will decrypt the file when a user requests to download it. The retrieval and formatting portions of the application are complete.

The developer needs to use the GenerateDataKey API to encrypt the PDF file so that the PDF file can be decrypted later. The developer needs to use an AWS KMS symmetric customer managed key for encryption.

Which solutions will meet these requirements?

<ol type="A">
 <li>Write the encrypted key from the GenerateDataKey API to disk for later use. Use the plaintext key from the GenerateDataKey API and a symmetric encryption algorithm to encrypt the file.</li>
 <li>Write the plain text key from the GenerateDataKey API to disk for later use. Use the encrypted key from the GenerateDataKey API and a symmetric encryption algorithm to encrypt the file.</li>
 <li>Write the encrypted key from the GenerateDataKey API to disk for later use. Use the plaintext key from the GenerateDataKey API to encrypt the file by using the KMS Encrypt API.</li>
 <li>Write the plain text key from the GenerateDataKey API to disk for later use. Use the encrypted key from the GenerateDataKey API to encrypt the file by using the KMS Encrypt API.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  A
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

294. A company's developer has deployed an application in AWS by using AWS CloudFormation. The CloudFormation stack includes parameters in AWS Systems Manager Parameter Store that the application uses as configuration settings. The application can modify the parameter values.

When the developer updated the stack to create additional resources with tags, the developer noted that the parameter values were reset and that the values ignored the latest changes made by the application. The developer needs to change the way the company deploys the CloudFormation stack. The developer also needs to avoid resetting the parameter values outside the stack.

Which solution will meet these requirements with the LEAST development effort?

<ol type="A">
 <li>Modify the CloudFormation stack to set the deletion policy to Retain for the Parameter Store parameters.</li>
 <li>Create an Amazon DynamoDB table as a resource in the CloudFormation stack to hold configuration data for the application. Migrate the parameters that the application is modifying from Parameter Store to the DynamoDB table.</li>
 <li>Create an Amazon RDS DB instance as a resource in the CloudFormation stack. Create a table in the database for parameter configuration. Migrate the parameters that the application is modifying from Parameter Store to the configuration table.</li>
 <li>Modify the CloudFormation stack policy to deny updates on Parameter Store parameters.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  A
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

373. A company has a serverless application that uses Amazon API Gateway backed by AWS Lambda proxy integration. The company is developing several backend APIs. The company needs a landing page to provide an overview of navigation to the APIs.

A developer creates a new/LandingPage resource and a new GET method that uses mock integration.

What should the developer do next to meet these requirements?

<ol type="A">
 <li>Configure the integration request mapping template with Content-Type of text/html and statusCode of 200. Configure the integration response mapping template with Content-Type of application/json. In the integration response mapping template, include the LandingPage HTML code that references the APIs.</li>
 <li>Configure the integration request mapping template with Content-Type of application/json. In the integration request mapping template, include the LandingPage HMTL code that references the APIs. Configure the integration response mapping template with Content-Type of text/html and statusCode of 200.</li>
 <li>Configure the integration request mapping template with Content-Type of application/json and statusCode of 200. Configure the integration response mapping template with Content-Type of text/html. In the integration response mapping template, include the LandingPage HTML code that references the APIs.
</li>
 <li>Configure the integration request mapping template with Content-Type of text/html. In the integration request mapping template, include the LandingPage HTML code that references the APIs. Configure the integration response mapping template with Content-Type of application/json and statusCode of 200.</li>
</ol>
<details><summary>Show Correct Answer</summary>
  C
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
