# Chalice
Chalice is a framework for writing serverless apps in [[Python]]. It allows you to quickly create and deploy applications that use AWS [[Lambda]]. It provides:
- A command line tool for creating, deploying and managing your app
- A decorator based API for integrating with Amazon [[API Gateway]], Amazon [[S3]], Amazon [[SNS]], Amazon [[SQS]] and other services
- Automatic [[IAM]] policy generation.

Chalice allows you to:
- Create REST APIs
- Create tasks that run on a periodic basis
- Connect a [[Lambda]] function to an [[S3]] event
- Or an [[SQS]] queue
- And use other services

Once the code has been written, you can run `chalice deploy` and Chalice will deploy the app