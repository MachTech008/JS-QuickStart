Set up DynamoDB on your desktop!

[Source](https://gist.github.com/christianchang/699818b57469e1a175ff361e6cefce1f
): Team Member Christian Chang

# DynamoDB Tutorial:

## Installing Amazon Command Line Interface

### Windows

http://docs.aws.amazon.com/cli/latest/userguide/installing.html#install-msi-on-windows

Download and run the 64-bit or 32-bit Windows installer.

### Mac
Mac should already have python 2.7 installed. If you do not have python 2.7, be sure to download it here:
https://www.python.org/downloads/

Once you have downloaded python, run this command:
``$ easy_install pip``

Once pip has been installed, run this command to download and install AWS CLI:
``$ sudo pip install awscli``

More instructions here: 
http://docs.aws.amazon.com/cli/latest/userguide/installing.html#install-with-pip

## Test Amazon Command Line Interface

Once you have installed AWS CLI, run ``$ aws `` in your terminal to ensure the $PATH is configured.

``$ aws dynamodb describe-table --table-name dogs-test``

## Configure your AWS credentials

``$ aws configure``

### Downloading AWS SDK for Node.js

``$ npm install aws-sdk``

To learn more about the SDK, please visit: 

http://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/getting-started-nodejs.html

## Getting Your AWS Key Id & Secret Access Key

Sign up for AWS free tier account.

### Configuring your AWS Key Id & Secret Access Key

Here are the ways you can supply your credentials in order of recommendation:
* Loaded from AWS Identity and Access Management (IAM) roles for Amazon EC2 (if running on Amazon EC2)
* Loaded from the shared credentials file (~/.aws/credentials)
* Loaded from environment variables
* Loaded from a JSON file on disk

In this session, we will load the shared credentials file (~/.aws/credentials), so we can use it locally when developing.

## Requiring AWS SDK in your .js file & Configure the region

```
var AWS = require('aws-sdk');

AWS.config.update({
	region: process.env['AWS_REGION'] || 'us-west-1'
});
```

## Creating an instance for your dynamoDB

```
var dynamodb = new AWS.DynamoDB({
	endpoint: 'https://localhost:8000
});
```

## Read through the methods of dynamodb here:
http://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/DynamoDB.html

## DynamoDB Local
http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBLocal.html

After you extract the .zip or .tar file, run:
``$ java -Djava.library.path=./DynamoDBLocal_lib -jar DynamoDBLocal.jar -sharedDb -port 3000``

Open the browser and navigate to http://localhost:3000/shell/


External References:
[Amazon AWS Info on DynamoDB](http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBLocal.html)
