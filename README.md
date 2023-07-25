# AWS-Inspector-Report
Auto generates Amazon Inspector reports in csv format and email link to download it

## Table of contents
- [AWS-Inspector-Report](#aws-inspector-report)
  - [Table of contents](#table-of-contents)
  - [Intro](#intro)
  - [What it does](#what-it-does)
  - [Deployment](#deployment)
  - [Credits](#credits)

## Intro
This project builds all you need in order to get a report from Amazon Inspector delivered directly to your mailbox.

## What it does
This CloudFormation Stack creates the following resources:
* a S3 bucket to host all your reports;
* a Lambda function that extracts all the needed data from SecurityHub and saves it into the bucket above (all logs will be saved to CloudWatch);
* an IAM role, with 3 policies, so that the Lambda can do its job;
* a SNS Topic with 2 preconfigured subscriptions to get the notification into your mailbox;
* an EvenBridge rule that triggers the Lambda above on a schedule;

Note: the link you receive is configured to expire after 12 hours for security reasons.

## Deployment
In order to deploy this template:
* open CloudFormation in the account in which you have SecurityHub configured;
* populate all the required fields above
* submit

## Credits
* [Bryan Chua - ykbryan](https://github.com/ykbryan) - Original author of the lambda function that I repurposed, available [here](https://github.com/ykbryan/lambda-get-securityhub-findings).
