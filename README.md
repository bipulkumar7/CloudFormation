Write a cloud formation template to deploy a lambda function with the following:
> An SQS queue which subscribes to a SNS topic based on a particular message type
> A lambda function which is listening to the SQS Queue (in point 1) events and writing the messages body to s3
> S3 bucket configured with versioning and lifecycle polices for that data
> Necessary policies and roles required for this use-case


Use `aws cloudformation create-stack --stack-name  s3Stack  --template-body file://00_s3Stack.yml --capabilities "CAPABILITY_NAMED_IAM" ` to deploy the s3 bucker and upload your code into it.

Use `aws cloudformation create-stack --stack-name  LambdaFunction  --template-body file://00_LambdaStack.yml --capabilities "CAPABILITY_NAMED_IAM" ` to deploy the stack.

Use `aws cloudformation delete-stack --stack-name LambdaFunction` to delete the stack.

