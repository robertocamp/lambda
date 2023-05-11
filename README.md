# lambda
basic lambda using various tutorials (linked in README) re AWS, Go, SNS and SQS

## setup
1. `go mod init github.com/robertocamp/lambda`
2. diagram: ./img/github-lambda-sns-sqs.png
3. AWS CONSOLE
  - create SQS queue (use default access policy)
  - create SNS topic (standard; default access policy)
  - create a *subscription* in the SNS topic
    + choose *Amazon SQS* for the protocol
    + *select the queue that we just created as the endpoint*
4. **SNS needs permissions to use the queue**
  - copy the SNS topic ARN: arn:aws:sns:us-east-1:417055865024:agc-lambda-sns-sqs
  - 

## go code
- typical distributed systems flow:
  +  producer -> events -> consumer
  +  *our Lambda code can play the role of producer or consumer*
  + a lambda can produce events and put them onto SQS queues and publish notifications onto SNS topcis

## links
https://www.youtube.com/watch?v=ciTa2I7-tDE
https://www.youtube.com/watch?v=SMWmz1oLqx4&t=1701s