---
title: "Create ECR Repo"
chapter: false
weight: 17
---

1. Go to **ECR** service, **Get Started**.
1. Type in **web** and click on **Create repository**.
![ecr](/images/ecr.png)
1. Click on **web** / **View push commands**. Go ahead and copy and paste each command. You will run these commands at **Cloud9 Terminal**. Note: the first command make sure to include *$()*
![ecr-push](/images/ecr-push.png)
Output
![ecr-push-output](/images/ecr-push-output.png)
1. Now if you close the push command and refresh the registry, you will see **latest** image tag pushed to the repo.
![ecr-img](/images/ecr-img.png)
