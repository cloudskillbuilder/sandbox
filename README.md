# sandbox
sandbox demo environment developing on aws

Locate the sanbox_template.yml file in the extracted folder.
You will use this template to create the sandbox environment.

This demo sandbox creates an S3 public website. To host the website, create a public S3 bucket and add a public S3 bucket policy, you must have the s3:GetObject permission. If you don't have this permission, contact your administrator to add the permission to your account. 

Meanwhile, in your AWS CloudFormation template, comment the code (line numbers 321–331) related to the webBucketPolicy resource, and proceed with the next steps. After the stack is completed and you have been granted the appropriate permissions, modify the pollyNotesWeb bucket to add s3:GetObject bucket policy permission. 

The appendix includes a sample bucket policy. If you are using this sample bucket policy, remember to change the bucket name.

5. Create an AWS CloudFormation stack by using the sandbox_template.yml template.

6. Replace the S3ResourceBucket parameter with your S3 bucket where you uploaded the demo code. Retain the remaining default settings. Acknowledge the capabilities check, and create the stack.

This stack launches two additional stacks: one creates an AWS Cloud9 instance and the other creates the lab application called the Polly Notes.

Task 3: Verifying your environment settings

7. After the stack is completed, make sure that the following resources were created so that you can help students with the demo:

Lambda functions – All five lambda functions (Python) with tracing enabled.
API Gateway resources
AWS Cloud9 instance – Contains the code necessary to host the application. You can use the code snippets in your demos.
Website– Website URL for your Polly Notes application. 
User name: student
Password: student
Polly Notes website – This is the demo application created for you. The link to the demo application is available from the Output section of your initial stack.


Appendix: S3 bucket policy

If you’re manually adding to your S3 website bucket, use this IAM policy. Remember to change the bucket name.
{
"Version": "2012-10-17",
"Statement": [
	{
	"Sid": "Statement1",
	"Principal": "*",
	"Effect": "Allow",
	"Action": ["s3:GetObject"],
	"Resource": ["arn:aws:s3:::demo-pollynotesweb-co8h0ipmv0pv/*"]
	}
]
}
