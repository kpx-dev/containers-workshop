---
title: "Package & Deploy Lambda using SAM"
chapter: false
weight: 15
---

#### Create the S3 repo to store SAM artifact
Since the S3 repo name must be unique globally, please postfix with your username

```
aws s3api create-bucket --bucket serverless-lab-[your-username]
```

#### Upgrade SAM CLI to latest version
Run the command below and press **ENTER** to continue. Once done, please open **New Terminal**
```
./install-sam.sh
```

#### Package the template
Don't forget to replace `serverless-lab-[your-username]` with your actual S3 bucket name.

```
sam package --s3-bucket serverless-lab-[your-username] --s3-prefix lab --output-template-file template_packaged.yaml
```

#### Deploy Lambda using SAM
This will take 1-2 minutes as SAM is creating CloudFormation stack. You will also see that there's a new S3 bucket created by SAM: `serverless-lab-lambda-mys3bucket-`.

```
sam deploy --template-file template_packaged.yaml --stack-name serverless-lab-lambda --capabilities CAPABILITY_IAM
```

#### Add files to S3
Now when you add any file to the above S3 bucket (`serverless-lab-lambda-mys3bucket-`) you will see that Lambda will get triggered.
From Lambda, you can click on Monitoring / CloudWatch and view its latest logs.
