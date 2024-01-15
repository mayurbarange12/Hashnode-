---
title: "Day 14 - Docker Advanced (Docker Bridge Network)"
datePublished: Tue Dec 12 2023 19:11:34 GMT+0000 (Coordinated Universal Time)
cuid: clq2pxytp000008jycbxf7y4j
slug: day-14-docker-advanced-docker-bridge-network
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702405169053/08b3222f-0432-426f-b3b8-07384955f777.jpeg
tags: docker, automation, devops, docker-network, 90daysofdevops, shubhamlondhe, trainwithshubham, tws

---

## **Two or more Containers how can they communicate**

### **<mark>Project: Two-Tier-Flask-App</mark>**

* `cd projects/`
    
* `git clone` [`https://github.com/LondheShubham153/two-tier-flask-app.git`](https://github.com/LondheShubham153/two-tier-flask-app.git)
    
* `cd two-tier-flask-app/`
    

### **Will create a MYSQL Container**

* `docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=test@123 -e MYSQL_DATABASE=testdb -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin mysql:latest` --&gt; **\--&gt;** This command runs a MySQL Docker container(-d) from the latest image, setting up a MySQL database with specific environment variables (-e) for the root password, database name, user, password, and mapping the container's port 3306 to the host's port 3306 (-p).
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702404680796/337a05a7-d1e3-458f-8ee8-cc5afec281c3.png align="center")

* `docker exec -it a36c23e4c051 bash` --&gt; Allows interactive access (-it) to the shell (bash) within a running container (identified by its container ID "a36c23e4c051"
    
* **bash-4.4#**`mysql -u root -p`
    
* **Enter password:** `test@123`
    
* **mysql&gt;** `show databases;`
    
* **exit**
    
* **exit**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702404993682/f02e443a-f8d1-4e92-8e35-6698618b989c.png align="center")

### **Will create a Flask Container**

* `docker build -t flask-app .`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702405105456/6bf08b10-1616-4781-a60d-5104784f38ef.png align="center")

* `docker run -d -p 5000:5000 flask-app:latest`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702405221759/b7a4e0a4-b75a-4845-9518-127b9f4c0fdd.png align="center")

* EC2-instance port **8000** should be allowed.
    
* Search on Web Browser "EC2 instance Public IP-**54.145.97.90:5000**" It will shows below web page:
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702405348092/880f3f1b-6bc9-452c-996d-14c210394716.png align="center")

### **Will create a Docker Bridge Network in between both the Containers**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702405579953/080c6d1f-8e41-4eec-9f28-252ba5e7387b.png align="center")

### **Firstly will set Name(mysql) to MYSQL Container**

* `docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=test@123 -e MYSQL_DATABASE=testdb -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin --name mysql mysql:latest`
    
* `docker ps`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702405953649/089665a8-be40-4d41-a411-24a85e8109f4.png align="center")

### **Will set Host(mysql) and Name(flask-app) to Flask-app Container**

* `docker run -d -p 5000:5000 -e MYSQL_HOST=mysql -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin -e MYSQL_DB=testdb --name flask-app flask-app:latest`
    
* `docker ps`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702406130462/59790b1a-fe9e-4c8c-82ad-a17471c72357.png align="center")

* **The error has been changed now("unknown server host 'mysql'").**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702406343126/8ddbdf3c-3529-4c04-baae-bc175a1df4d0.png align="center")

* `docker ps`
    
* `docker kill caa0207d857a cabc406edabd`
    

## **<mark>Docker Network</mark>**

"Docker network" facilitates communication and connectivity between containers, enabling isolated and secure communication across different services and applications.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702406571563/29a736ed-ffb1-45b3-b2eb-7accdd9ba09c.png align="center")

### **Types of Docker Network**

* **Bridge Network**
    
* **Overlay Network**
    
* **Macvlan Network**
    

**Note:-** The type of Docker network that you use will depend on your specific needs. If you are only running containers on a single host, then a bridge network is a good option. If you need to communicate between containers on different hosts, then an overlay network is a better choice. If you need to connect Docker containers directly to host network interfaces, then a macvlan network is the best option.

### **How to create Docker Bridge Network?**

* `docker network create -d bridge two-tier-app-nw`
    
* `docker network ls`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702406713514/aee4ec61-e1be-4e4b-84d5-aefb4cd8bdbe.png align="center")

### **Will add mysql container to "two-tier-app-nw" Network**

* `docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=test@123 -e MYSQL_DATABASE=testdb -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin --name mysql --network two-tier-app-nw mysql:latest`
    
* `docker network ls`
    
* `docker inspect two-tier-app-nw` --&gt; Retrieves detailed information about a Docker resource, such as a container, network, or volume, named "two-tier-app-nw".
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702407147999/0b5a3e57-5086-4cb4-9954-d465237f8fbe.png align="center")

### **Will add flask-app container to "two-tier-app-nw" Network**

* `docker run -d -p 5000:5000 -e MYSQL_HOST=mysql -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin -e MYSQL_DB=testdb --name flask-app --network two-tier-app-nw flask-app:latest`
    
* `docker inspect two-tier-app`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702407441042/b7aca1df-0152-4e32-81d5-13b9209a6593.png align="center")

* **The error has been changed now "Table 'testdb.messages' doesn't exist**"
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702407489646/aeca5fb5-87ac-4449-b828-21ead8e1db64.png align="center")

* `docker ps`
    
* `docker exec -it 827f25f7562b bash`
    
* **bash-4.4#** `mysql -u root -p`
    
* **Enter password:** `test@123`
    
* **mysql&gt;** `use testdb;`
    
* **mysql&gt;** `show tables;`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702407672095/2cdbad14-8142-4c9a-b0fa-733f3590baf0.png align="center")

* **Will create the table so copy & paste the code for the creation of the table. (two-tier-flask-app/message.sql) messages.sql**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702407865062/d89a2f80-998b-4b10-90fa-86d0f889ae21.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702407870041/00eb6b80-c778-4384-8d78-d5705c0ecbd1.png align="center")

* **Now two-tier app is running**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702407920112/e9721e60-7c76-424a-9ce0-409a7d85957e.png align="center")

* `select * from messages;`  **--&gt;** This is a query to get the data
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702407953910/dd29a61d-ecc8-4dc0-bedf-61e26d05339b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702408028369/ac6bbb7f-e8ab-48f6-930d-ddb2a050d447.png align="center")

* **Now data is stored in the "message" database as per the code.**