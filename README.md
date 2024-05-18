# dotnet-lambda
hello world aws lambda

# Install lambda templates
```bash
dotnet new install "Amazon.Lambda.Templates::*"
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



