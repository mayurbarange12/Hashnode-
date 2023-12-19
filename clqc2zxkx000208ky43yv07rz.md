---
title: "Day 18 - Jenkins CI/CD Project"
datePublished: Tue Dec 19 2023 08:26:56 GMT+0000 (Coordinated Universal Time)
cuid: clqc2zxkx000208ky43yv07rz
slug: day-18-jenkins-cicd-project
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702967863783/8ac0005e-ee32-45f6-8943-a3813af6099f.png
tags: devops, jenkins, cicd-cjy1vtdk2005kjjs17n8couc3, 90daysofdevops, shubhamlondhe, trainwithshubham, tws

---

## **Project** - **django-todo-cicd**

* **Click on "Create a job" or "New Item"**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702970974891/07a8a3f9-d5e0-4885-af4e-f3592f986d7f.png align="center")

* **Add Description and click on "Discard old builds"**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702971109867/7de2d305-5b52-4208-99a4-d988c4f34001.png align="center")

* **Provide GitHub Project URL and Display name:**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702971181208/709aeb18-7021-4136-8d2a-c9bcd54f8b4b.png align="center")

* **Provide Source Code Management -&gt; Git Repository URL:**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702971260854/bb143478-05c8-43c2-8530-3204bceaa1dc.png align="center")

* **Branches to build : \*/develop --&gt;** Specify the proper Branch name here.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702971296441/2f9965f9-92b8-40f9-9b93-0ec5be0ebdac.png align="center")

* **Build Steps: Execute Shell Command**
    

```bash
echo "-------- DEVOPS CICD STARTED ---------"

echo "CI/CD started by User"
whoami

echo "Code Stage"

echo "Build Stage"
docker build -t django-app .

echo "Test Stage"

echo "Deploy Stage"
docker run -d -p 8000:8000 django-app:latest
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702971388725/e9f88bec-404a-457a-961b-7e002006e2e7.png align="center")

* **Save it**
    
* **Click on Build Now --&gt;** The "django-todo-cicd " Job gets failed
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702971430821/39e3396f-2943-40c2-b448-f35c71ffec08.png align="center")

* **Inside Console Output:**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702971552630/b79db4a1-743b-4790-9cfb-2f4cc0e327b8.png align="center")

* **sudo apt install** [**docker.io**](http://docker.io)  **--&gt;** Docker installed now.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702971722598/3904b3bc-d16c-4542-9649-5514d121be33.png align="center")

* **Again Build Now --&gt;** Again "django-todo-cicd " Job gets failed
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702971830903/324bc239-0969-40cc-a55e-297c0bea4789.png align="center")

* **sudo usermod -aG docker jenkins** \--&gt; Jenkins user added to Docker Group.
    
* **sudo reboot**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702971924424/fc74b0d0-ce5e-40ef-8934-692341210c65.png align="center")

* **Build Now**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702971945370/fec137a0-8cc3-4d9a-97e7-c935a81b4fb9.png align="center")

* **Build is Successful**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702971987718/30a55504-c245-4716-bc8e-9ed1157eca5b.png align="center")

* EC2 Instance **Security port** should **allowed:-** **Security** -&gt; **Inbound Rule** -&gt; Edit Inbound Rule -&gt; Port:**8000** and Source:**Anywhere-IPV4** \-&gt; save rules.
    
* Search on Browser "EC2 instance Public IP-**18.116.27.188:8000**" It will be Run.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702972108256/2d98099d-6daf-4096-a8ec-a3e3e07341ce.png align="center")

* **If I do Again Build now then it gets failed.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702972280331/2b64641e-51e8-4bd6-9601-59d4b2632f9d.png align="center")

* The error says **the port is already allocated.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702972319030/16a8c3e3-da8d-4209-a607-90235af4af9a.png align="center")

* **sudo apt install docker-compose** --&gt; **Solution** for this "**port is already allocated**" error.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702972383111/020e66ac-1330-4b75-b93d-4acff01286bf.png align="center")

```bash
echo "-------- DEVOPS CICD STARTED ---------"

echo "CI/CD started by User"
whoami

echo "Code Stage"

echo "Build & Deploy Stage"
docker-compose down && docker-compose up -d
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702972511815/970bd3de-4198-4a56-8f80-c68d05c077bc.png align="center")

* **Save it**
    
* **Build now --&gt;** Again "django-todo-cicd " Job gets failed because **Port is already allocated**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702972605342/24aa2e7c-735b-4569-a75b-ab968c0f62cd.png align="center")

* **So we need to kill that old container.**
    
* **sudo docker ps**
    
* **sudo docker kill 31b0e9a3d7c8**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702972689842/b34b44a3-64ac-48d7-ba56-1efb8aaae2e3.png align="center")

* **Build now**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702972732474/53b50129-fe4a-468f-9ea7-8a751b5453ac.png align="center")

* **Now if I do build Now multiple times it will** **get a successful build every time.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702972941914/944c17ee-4572-4b28-8987-2f3723caec97.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702974103419/6bdb184e-5ced-4cb4-a115-3535d8b4fe38.png align="center")