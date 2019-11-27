---
title: "View the container content"
chapter: false
weight: 16
---

#### Allow your laptop to access EC2 port 80
1. Go to **EC2** / **Instances**
1. Click on the one running instance
1. Click on **Security groups** and **Inbound / Edit**. Allow port **80** to **My IP** and **Save**.

![sg](/images/sg-01.png)

#### Go back to Cloud 9, get the EC2 Public IP
```
curl 169.254.169.254/latest/meta-data/public-ipv4; echo
```

#### Open the IP in a new browser tab

You should see a text: **Hello RTS team!**

#### Stop the container

Try stopping the container and refresh the last page, it should not work anymore.

```
docker stop web
```
