---
title: "Clone container repo"
chapter: false
weight: 14
---

1. Login to your AWS Account, make sure you are in the **North Virginia (us-east-1)** region

1. Click on Services Drop down, type **Cloud9**.

1. There should be an existing environment created for you called **lab**. Click on **Open IDE**.

1. Once launched, go to a Terminal tab:

#### Clone repo and cd into it
```
git clone https://github.com/kienpham2000/docker-example.git

cd docker-example

```

Output will look like this
```
admin:~/environment $ git clone https://github.com/kienpham2000/docker-example.git
Cloning into 'docker-example'...
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (7/7), done.
remote: Total 9 (delta 1), reused 4 (delta 0), pack-reused 0
Unpacking objects: 100% (9/9), done.
```
