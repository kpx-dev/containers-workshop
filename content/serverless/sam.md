---
title: "Package & Deploy Lambda using SAM"
chapter: false
weight: 15
---

#### Create the S3 repo to store SAM artifact
Since the S3 repo name must be unique globally, please postfix with your **username**. We'll use this S3 bucket to store our built artifact.

```
aws s3api create-bucket --bucket serverless-lab-[change-to-your-username]
```

#### Upgrade SAM CLI to latest version
This can take up to 2-3 minutes to install all required packages.
```
./install-packages.sh
```

#### Package the template
Don't forget to replace `serverless-lab-[your-username]` with your actual S3 bucket name created earlier.

```
sam package --s3-bucket serverless-lab-[your-username] --s3-prefix lab -t s3-watcher/template.yaml --output-template-file built.yaml
```

#### Deploy Lambda using SAM
This will take 1-2 minutes as SAM is creating CloudFormation stack. You will also see that there's a new S3 bucket created by SAM: `serverless-lab-lambda-s3-watcher-mys3bucket-[random-chars]`.

```
sam deploy --template-file built.yaml --stack-name serverless-lab-lambda-s3-watcher --capabilities CAPABILITY_IAM
```

#### Add files to S3
Now when you add any file to the above S3 bucket, you will see that Lambda will get triggered.

1. Go to **S3** service. Select your bucket, should starts with: `serverless-lab-lambda-s3-watcher-mys3bucket-[random-chars]`. Select **Upload** and upload any random file.
![S3 Upload](/images/serverless/s3-upload.png)
1. Go to **Lambda**. Click on the Lambda function: `serverless-lab-lambda-s3-SimpleS3ListenerFunction-[random-chars]`
1. Click on **Monitoring**. Click on **View logs in CloudWatch**.
![Lambda Monitoring](/images/serverless/lambda-mon.png)
1. At CloudWatch Logs, click on the latest Log Streams.
You will see output looks like this:
![CloudWatch Logs](/images/serverless/lambda-cwlogs.png)

#### Congrats!

You are done with this lab.
