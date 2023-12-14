---
title: "Day 15 - Docker Compose and Multi-Stage Docker Build"
datePublished: Thu Dec 14 2023 15:42:52 GMT+0000 (Coordinated Universal Time)
cuid: clq5dda2f00000akz4bzc7ct9
slug: day-15-docker-compose-and-multi-stage-docker-build
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702558687784/83cde74c-76c5-4fd9-b698-fb26f239f60c.jpeg
tags: docker, docker-compose, dockerhub, 90daysofdevops, shubhamlondhe, trainwithshubham, multi-stage-docker-file, tws

---

## **<mark>Docker Compose</mark>:-**

"Docker Compose" is a tool that simplifies the management of multi-container Docker applications by defining and running them with a single YAML file configuration.

### **<mark>Project</mark>:- <mark>two-tier-flask-app</mark>** (using docker-compose)

* `mkdir projects`
    
* `cd projects/`
    
* `mkdir two-tier-flask-app`
    
* `cd two-tier-flask-app/`
    
* `sudo apt  install docker-compose`
    
* `vim docker-compose.yml`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702566321571/f937ab21-e593-4cfe-928e-0782d2eb4fa2.png align="center")

* `docker-compose up -d`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702566415870/db312d84-11af-4194-9f9d-efa846ec4d31.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702566422028/96575167-5116-4783-adf0-6d5d215e6d1d.png align="center")

## **<mark>Multi-Stage-Docker-Build</mark>:-**

"Multi-Stage Docker Build" is a technique allowing for efficient Docker image creation by using multiple build stages in a single Dockerfile, segregating build environments to optimize final image size and performance.

### **<mark>Project</mark>:- <mark>python-multistage-docker</mark>** (using multi-stage-docker-build)

* `git clone`[`https://github.com/LondheShubham153/python-multistage-docker.git`](https://github.com/LondheShubham153/python-multistage-docker.git)
    
* `cd python-multistage-docker/`
    
* `vim Dockerfile`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702566756087/96249725-fdb3-4732-9e6e-993ce8df1529.png align="center")

* `docker build -t python-flask-app .`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702566845493/8d07f5a7-37ac-47a7-9a41-6c3315277850.png align="center")

* `docker run -d -p 5000:5000 python-flask-app:latest`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702566895957/b109d60a-78c9-4fc8-a0d3-0ac2ff328694.png align="center")

* `docker ps`
    
* `docker ps -a`
    
* `docker logs 0d312d347902`
    
* `cd backend/`
    
* `vim requirements.txt`
    
* `cd ..`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702567057836/c1be608c-db04-44db-a5f2-ebe4dec9052a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702567046376/2c83e30d-248f-4975-acc7-243e968eb8cf.png align="center")

* `docker build -t python-flask-app .`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702567398836/8e33d25a-c188-4521-a6ba-064bc3b22856.png align="center")

* `docker run -d -p 5000:5000 python-flask-app:latest`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702567473588/56e866ae-f627-413c-a38d-3a900f60ebb3.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702567483413/25cc887f-c680-4c38-819b-57fcb7a789b6.png align="center")

* `docker images` --&gt; "**python-flask-app**" size is more **1.01GB**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702567549916/a4a533ba-a103-4f8d-9e91-6f22b18b37b0.png align="center")

* `vim Dockerfile` --&gt; **Multi Stage Docker Build**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702567580131/f45a080d-da5e-47ed-bffc-a1ff35a67935.png align="center")

* `docker build -t multi-stage-python .` --&gt; "**multi-stage-python**" name has been given for the docker build.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702567621496/fc3ab558-0c08-4fb6-a720-15313cb63dcc.png align="center")

* `docker images` --&gt; "**multi-stage-python**" size is reduced **116MB**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702567654223/3695277b-fb41-477e-806d-45abf8b3f124.png align="center")

* `docker run -d -p 5000:5000 multi-stage-python:latest`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702567927415/8e8e413f-c33c-4207-98d8-ab19610e1c22.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702567941121/d0c1572b-3400-4b78-be36-8fab9fa974c4.png align="center")