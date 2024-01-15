---
title: "Day 12 - Docker For Devops"
datePublished: Sat Dec 02 2023 20:15:56 GMT+0000 (Coordinated Universal Time)
cuid: clpohu88x000108l88t8ngh1l
slug: day-12-docker-for-devops
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701548054358/b79dae42-ab07-457d-87fd-d0c2b2bbc57d.webp
tags: docker, automation, devops, dockerfile, 90daysofdevops, shubhamlondhe, trainwithshubham, tws

---

### **Let check some practical examples**

* **Create an EC2 Instance named as "boom-server"**
    
* `sudo apt update`
    
* `sudo apt install` [`docker.io`](http://docker.io)  **\--&gt;** To install docker
    
* `systemctl status` [`docker.io`](http://docker.io)  **\--&gt;** To check status of docker
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701544144338/b6512356-0862-448b-b59f-64b72ca05243.png align="center")

* `sudo apt purge docker.io` **\--&gt;** To completely remove the Docker package along with its configuration files and dependencies from the system.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701544255147/8193b974-7640-416c-86c3-affbfc7801ea.png align="center")

* `docker ps`  **\--&gt;** Displaying the list of currently running containers along with their relevant information like names, IDs, status, and more.
    
* `sudo docker ps`
    
* `sudo cat /etc/group`  **\--&gt;** Displays the contents of the system's group file, listing all user groups and their associated group IDs.
    
* `sudo usermod -aG docker ubuntu` **\--&gt;** -aG=add to a Group &lt;**GroupName**&gt; &lt;**UserName**&gt;  (To add "**ubuntu**"user into a "**Docker**" Group.)
    
* `sudo cat /etc/group`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701544556933/a766bdbf-cf95-487d-8fe7-4b30b2c64710.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701544582128/402cad0b-071b-4a4e-9c78-f98e72e41805.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701544601223/69d74ead-04d9-43d2-9d2f-2eac5d36e6fd.png align="center")

* **Now it is not denying while trying to check running container's process status command because "ubuntu" User is added into the "docker" Group.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701544681227/cb22b819-ad58-408e-8c61-3ff9ff06ee11.png align="center")

## **How to create a Container?**

**<mark>File --&gt; Image --&gt; Container</mark>**

**<mark>Image</mark>:-** An image in Docker is a read-only template containing application code, libraries, dependencies, and configurations used to create containers.

* `docker pull mysql` **\--&gt;** This command pulls the MySQL image from Docker Hub to your local machine, allowing you to create containers based on this image for running MySQL databases.
    
* `docker images` **\--&gt;** Lists all available Docker images stored locally on your machine.
    
* `docker run mysql:latest` **\--&gt;** Initiates a new container using the latest version of the MySQL image, allowing you to run a MySQL database instance.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701545095541/4b73fc03-98c8-4ea6-b60d-a4ff54dcf234.png align="center")

* `docker run -e MYSQL_ROOT_PASSWORD=test@123 mysql:latest`  **\--&gt;** Initializes a MySQL container with the specified root password "test@123" using the latest MySQL image.\[-e = environment variable\]
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701545199233/221d7de8-d343-45cc-b719-4761c707a7a9.png align="center")

* `docker ps`
    
* `docker kill 4e5864129099` --&gt; Container runs and after that, if it is not exit then kill he container.
    
* `docker run -d -e MYSQL_ROOT_PASSWORD=test@123 mysql:latest` --&gt; To Run Container in background or detached mode.
    
* `docker ps`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701545545000/4b82d298-a549-4f39-98ba-0f37d862bf53.png align="center")

## **How to create our own image?**

**<mark>Will run "Hello Dosto" in Local System using Java code</mark>:-**

* `mkdir projects`
    
* `cd projects/`
    
* `mkdir java-app`
    
* `cd java-app/`
    
* `vi Hello.java`
    
    ```java
    public class Hello{
    
            public static void main(String Args[]){
                    System.out.println("Hello Dosto");
            }
    }
    ```
    
* `javac` [`Hello.java`](http://Hello.java)
    
* `sudo apt install openjdk-11-jdk-headless`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701546438087/68b39099-34c8-436f-a471-8f2976e0091b.png align="center")

* `javac` [`Hello.java`](http://Hello.java)
    
* `java Hello`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701546535762/b8b5bb9b-186d-4174-8f71-0e207f546f87.png align="center")

**<mark>Will run same "Hello Dosto" java code through Dockerfile</mark>**:-

**How to write a Dockerfile:-**

* `vim Dockerfile`
    

```dockerfile
# Get the base image
FROM openjdk:11

# Create a working directory to keep all the files
WORKDIR /app

# Code copy to the image for running in container
COPY Hello.java /app

# Compile the code
RUN javac Hello.java

# App is now ready to run

# Actually passing the run commands as arguments
CMD ["java","Hello"]
```

**Note:- <mark>"Intermediate commands"</mark> will not be changed but <mark>Run Command "CMD"</mark> will be changed anytime if we want, that is why we use Arguments.**

* `docker build -t java-app:latest .` **\--&gt;** Command to build a Docker image tagged as "java-app" with the "latest" version, using the current directory (".") as the build context.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701547706895/e6bcbe25-7b42-441b-8937-d1578f123f86.png align="center")

* `docker images`
    
* `docker run java-app:latest`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701547787159/76025c0e-10d6-48d5-925d-510409564d0a.png align="center")