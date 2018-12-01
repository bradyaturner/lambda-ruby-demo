# Lambda Ruby Demo

## Starting point for creating a new AWS Lambda function using Ruby

### Includes:
* Basic Lambda function handler script
* Basic Gemfile
* Rakefile with tasks to deploy to AWS
* Basic exclude file for excluding files from deployment
* .gitignore populated with project-specific entries
* Sample config file

### Getting started:
* Clone repository
* Create config file: `cp lambdaconfig.yml.sample lambdaconfig.yml`
* Populate config file with your AWS info
* Install and configure [AWS CLI](https://aws.amazon.com/cli/)
* Edit script and Gemfile to add your own functionality
* Run `rake deploy` to upload the project to your Lambda

### Resources:
* AWS CLI: https://aws.amazon.com/cli/
* AWS Lambda Ruby Support Announcement: https://aws.amazon.com/blogs/compute/announcing-ruby-support-for-aws-lambda/
* AWS Lambda Docs: https://docs.aws.amazon.com/lambda/latest/dg/welcome.html
* AWS Lambda Ruby Docs: https://docs.aws.amazon.com/lambda/latest/dg/lambda-ruby.html
