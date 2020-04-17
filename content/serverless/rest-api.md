---
title: "REST API"
chapter: false
weight: 20
---

#### Overview
In this lab, we'll deploy a very simple REST API running on Lambda and served by API Gateway.

#### Change into the repo
```
cd ~/environment/lambda-example/rest-api/
```

#### Package the template
Don't forget to replace `serverless-lab-[your-username]` with your actual S3 bucket name created earlier.

```
sam package --s3-bucket serverless-lab-[your-username] --s3-prefix lab --output-template-file built.yaml
```

#### Deploy Lambda using SAM
This will take 1-2 minutes as SAM is creating CloudFormation stack.

```
sam deploy --template-file built.yaml --stack-name serverless-lab-lambda-rest-api --capabilities CAPABILITY_IAM
```

#### Make request to the API
Once deployed, you'll see under the **Outputs** section there will be an url to API Gateway. You can make a request to that.

The API Gateway url will look something like this:
```
http https://[your url here].execute-api.us-east-1.amazonaws.com/Prod/
```

#### Congrats!

You are done with this lab. Please take sometime and view the source codes of the cloned repos to see how it was setup.

**Challenge**: Try to change the output from the API, package and re-deploy the service.
