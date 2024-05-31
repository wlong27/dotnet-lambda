# dotnet-lambda
hello world aws lambda

# Install lambda templates
```bash
dotnet new install "Amazon.Lambda.Templates::*"
```

# AWS SSO
Create new sso profile. User will be prompted from browser.
```bash
aws configure sso
```

Check that profile is saved successfully
```bash
aws configure list-profiles
```
You can use any profile that is saved by specifying the profile name.
```bash
aws s3 ls --profile my-sso-profile
```



# AWS Extensions 
.NET CLI specifically focuses on Lambda functions and is invoked as a .NET tool 

```bash
dotnet tool install -g Amazon.Lambda.Tools
dotnet lambda
```

# Create .NET Project
```bash
dotnet new lambda.EmptyFunction -n HelloLambda
```

## Deploy 
```bash
dotnet lambda deploy-function --function-name HelloLambda

dotnet lambda invoke-function --function-name HelloLambda --payload "Hello World!"
```

- if there are no roles, create new IAM role HelloLambdaRole
- for permissions, attach AWSLambdaBasicExecutionRole
  
```bash
dotnet lambda delete-function --function-name HelloLambda
```

## Here are some steps to follow from Visual Studio:
- To deploy your function to AWS Lambda right click the project in Solution Explorer and select *Publish to AWS Lambda*.

- To view your deployed function open its Function View window.

- To perform testing against your deployed function use the Test Invoke tab in the opened Function View window.

- To configure event sources for your deployed function, for example to have your function invoked when an object is created in an Amazon S3 bucket, use the Event Sources tab in the opened Function View window.

- To update the runtime configuration of your deployed function use the Configuration tab in the opened Function View window.

- To view execution logs of invocations of your function use the Logs tab in the opened Function View window.

## Here are some steps to follow to get started from the command line:

Once you have edited your template and code you can deploy your application using the [Amazon.Lambda.Tools Global Tool](https://github.com/aws/aws-extensions-for-dotnet-cli#aws-lambda-amazonlambdatools) from the command line.

Install Amazon.Lambda.Tools Global Tools if not already installed.
```
    dotnet tool install -g Amazon.Lambda.Tools
```

If already installed check if new version is available.
```
    dotnet tool update -g Amazon.Lambda.Tools
```

Execute unit tests
```
    cd "HelloLambda/test/HelloLambda.Tests"
    dotnet test
```

Deploy function to AWS Lambda
```
    cd "HelloLambda/src/HelloLambda"
    dotnet lambda deploy-function
```

