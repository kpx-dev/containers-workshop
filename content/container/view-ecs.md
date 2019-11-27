---
title: "View Fargate Container"
chapter: false
weight: 23
---

1. Click on **Tasks** tab from **ECS** default cluster, you'll see one container running on Fargate. If you go back to EC2 and check, there's no new EC2 instance launched!
![](/images/ecs-tasks.png)
1. Click into the link under **Task** column
1. Under Network, you'll see the **Public IP**. Open this IP in a new browser tab, you will see the content of your container running on Fargate serverlessly!
![](/images/ecs-task-ip.png)
