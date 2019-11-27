---
title: "Docker build & run"
chapter: false
weight: 15
---

#### Build the Docker image
```
docker build -t web .
```

Output
```
admin:~/environment/docker-example (master) $ docker build -t web .
Sending build context to Docker daemon  65.54kB
Step 1/2 : FROM nginx:alpine
 ---> b6753551581f
Step 2/2 : COPY index.html /usr/share/nginx/html
 ---> Using cache
 ---> d44b90c272d6
Successfully built d44b90c272d6
Successfully tagged web:latest
```

#### Run the container
```
docker run -p 80:80 --name web web
```

#### Verify the container is running
Create a new Terminal tab

```
docker ps
```

Output
```
admin:~/environment $ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                NAMES
eadc9b959908        web                 "nginx -g 'daemon of…"   33 seconds ago      Up 32 seconds       0.0.0.0:80->80/tcp   web
```
