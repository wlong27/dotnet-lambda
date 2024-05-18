# dotnet-lambda
hello world aws lambda

# Install lambda templates
`dotnet new install "Amazon.Lambda.Templates::*"`

# AWS Extensions 
.NET CLI specifically focuses on Lambda functions and is invoked as a .NET tool 

`dotnet tool install -g Amazon.Lambda.Tools ` 
`dotnet lambda`

# Create .NET Project
`dotnet new lambda.EmptyFunction -n HelloLambda`

## Deploy 
`dotnet lambda deploy-function --function-name HelloLambda`
`dotnet lambda invoke-function --function-name HelloLambda --payload "Hello World!" `