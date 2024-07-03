Step 1: Setting Up AWS Environment
1. Create an AWS Account
* Sign up for an AWS account if you don't have one.
* Ensure you have appropriate permissions to manage EC2 and EBS resources.
2. Install AWS CLI
* Download and install the AWS Command Line Interface (CLI) from the official website.
* Configure the AWS CLI with your credentials:
  - aws configure
 3. Set Up IAM Role for Lambda
* Go to the AWS IAM Console.
* Create a new role with the following policies:
-  AmazonEC2ReadOnlyAccess
- AmazonEC2FullAccess
- AWSLambdaBasicExecutionRole

Step 2: Creating the Lambda Function
1. Go to AWS Lambda Console
* Create a new Lambda function.
* Choose the runtime (Python 3.8 or later is recommended).
2. Lambda Function Code - use the code provided in the code.py file in the repository
3. Environment Variables
* Configure environment variables if needed for additional configurations (e.g., logging level).
4. Set Up Lambda Permissions
* Ensure the Lambda function has the necessary permissions to describe and delete EBS snapshots.

Step 3: Testing the Lambda Function
1. Create Test Event
* Go to the "Test" tab in the Lambda console.
* Create a new test event with any JSON payload (it's not used in this function).
2. Run the Test
* Execute the test and check the CloudWatch logs for the output.
* Verify that stale snapshots are being identified and deleted correctly.

Step 4: Automating the Lambda Function
1. Create a CloudWatch Event Rule
* Go to the CloudWatch Console.
* Create a new rule to trigger the Lambda function periodically (e.g., daily).
2. Configure the Rule
* Set the event source to "Event Source" and choose "Schedule".
* Configure the schedule expression (e.g., cron(0 0 * * ? *) for daily at midnight).
3. Add Target
* Add the Lambda function as the target for the rule.

Step 5: Monitoring and Logging
1. Enable CloudWatch Logs
* Ensure CloudWatch Logs are enabled for the Lambda function.
* Monitor the logs for any issues or errors.
2.  Set Up Alerts
* Create CloudWatch alarms to notify you of any failures or anomalies.

Step 6: Cost Analysis and Reporting
1. Analyze Cost Savings
* Use AWS Cost Explorer to track cost savings over time.
* Compare costs before and after implementing the Lambda function.
2. Generate Reports
* Generate periodic reports on cost savings and optimization.
