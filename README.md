# serverless-todo

Original Application: https://github.com/evanchiu/serverless-todo

React [TodoMVC](http://todomvc.com/) with a Serverless backend.

It provides a demo integration of [React](https://reactjs.org) + [API Gateway](https://aws.amazon.com/api-gateway/) + [AWS Lambda](https://aws.amazon.com/lambda) + [Node.js](https://nodejs.org/) + [Amazon DynamoDB](https://aws.amazon.com/dynamodb/)

## Deploy with CloudFormation

Prerequisites: [Node.js](https://nodejs.org/en/) and [AWS CLI](http://docs.aws.amazon.com/cli/latest/userguide/installing.html) installed

* Create an [AWS](https://aws.amazon.com/) Account and [IAM User](https://aws.amazon.com/iam/) with the `AdministratorAccess` AWS [Managed Policy](http://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-vs-inline.html)
* Run `aws configure` to put store that user's credentials in `~/.aws/credentials`
* Create an S3 bucket for storing the Lambda code and store its name in a shell variable with:
  * `aws s3 mb s3://<bucket name>`
  * `export S3_BUCKET=<bucket name>`
* Npm install:
  * `npm install-modules`
* Build:
  * `npm run build`
* Upload package to S3, transform the CloudFormation template:
  * `npm run package`
* Deploy to CloudFormation:
  * `npm run deploy`

## Deploy from the AWS Serverless Application Repository
* Hit "Deploy" from the [application](https://serverlessrepo.aws.amazon.com/#/applications/arn:aws:serverlessrepo:us-east-1:233054207705:applications~serverless-todo) page

## Use
1. In the [API Gateway Console](https://console.aws.amazon.com/apigateway)
1. Navigate to APIs / aws-serverless-repository-serverless-todo / Settings
    1. Hit Add Binary Media Type
    1. Enter `*/*` in the box
    1. Hit Save Changes
    1. Navigate to APIs / aws-serverless-repository-serverless-todo / Resources
    1. Click the Actions dropdown
    1. Click Deploy API
        1. Deployment stage: **prod**
        1. Deployment description: *Adding binary support*
        1. Hit Deploy
1. Navigate to APIs / aws-serverless-repository-serverless-todo / Dashboard
    1. Find the Invocation url, something like *https://xxxxxxxxx.execute-api.region.amazonaws.com/Prod/*
    1. (You can also set up [custom domain name](http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-custom-domains.html))
1. Open the invocation url in your browser

## Links
* [serverless-todo](https://github.com/evanchiu/serverless-todo) on Github
* [serverless-todo](https://serverlessrepo.aws.amazon.com/#/applications/arn:aws:serverlessrepo:us-east-1:233054207705:applications~serverless-todo) on the AWS Serverless Application Repository

## License
&copy; 2017-2018 [Evan Chiu](https://evanchiu.com). This project is available under the terms of the MIT license.
