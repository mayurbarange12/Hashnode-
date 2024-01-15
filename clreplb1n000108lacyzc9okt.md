---
title: "Day 30 - AWS EC2"
datePublished: Mon Jan 15 2024 09:14:40 GMT+0000 (Coordinated Universal Time)
cuid: clreplb1n000108lacyzc9okt
slug: day-30-aws-ec2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1705300483224/e8aa1ffe-ca3b-4d36-be9f-5c3367372459.jpeg
tags: trainwithshubham-tws-devops-devopscommunity-shubhamlondhe-automation-awswithtws-7daysofaws-ec2

---

## **Elastic Compute Cloud (EC2):-**

Amazon Elastic Compute Cloud (EC2) is a foundational and highly scalable cloud computing service offered by Amazon Web Services (AWS). EC2 allows users to rent virtual servers, known as instances, in the cloud, providing on-demand compute capacity for a wide range of applications. Users can choose from a variety of pre-configured instances or customize them to meet specific requirements. EC2 instances cater to diverse workloads, from hosting websites and applications to running complex computations. With features such as scalability, flexibility, and pay-as-you-go pricing, EC2 empowers businesses and individuals to efficiently deploy and manage virtual servers in the AWS cloud environment, playing a pivotal role in modern cloud computing infrastructure. ☁️💻🚀

### How to Create, Manage, Connect to EC2 Instances:-

Creating, managing, and connecting to EC2 instances in AWS involves several steps. Here's a guide to help you through the process:

**1\. Sign in to AWS Console:**

* Log in to your AWS account and navigate to the EC2 Dashboard.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705301005705/94d824f0-d444-4b3e-a983-5d5aff334739.png align="center")

**2\. Create an EC2 Instance:**

* Click on "Launch Instance" to initiate the instance creation process.
    
* Choose an Amazon Machine Image (AMI) based on your application requirements.
    
* Select an instance type based on your computing needs.
    
* Configure instance details, add storage, and configure security groups (firewall settings).
    
* Review your settings and click "Launch." Choose or create a key pair for secure SSH access.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705301408285/f7ef5c4c-1a01-4432-9d0e-c3d3b6973293.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705309229136/aabadda4-c0ec-46c1-803b-f9888cfceb3e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705309238265/8bbba09e-0b90-4f4c-b099-bc297f0ed3c3.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705309243838/391b22ee-95f9-4a59-82fd-6f37972bdf9e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705309250097/9b64a96e-fc09-4cf0-a406-179bc6b98e80.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705309254736/f3a014e8-1049-4145-9659-d95139508110.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705309260297/4b8bfb4c-deda-4e5d-9702-d30d765269f9.png align="center")

**3\. Access EC2 Instances:**

* Once the instance is running, select it in the EC2 Dashboard.
    
* Use the "Connect" button to get connection instructions.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705309299736/adabe32e-62b5-4aba-970b-1cd8f5c85dc8.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705309305564/9c772fc9-3d48-49b2-bc84-157992496a83.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705309341480/2797e0bb-32fc-4263-aa95-268db8ca6cd2.png align="center")

**4\. Connecting via SSH (Linux Instances):**

* Open a terminal window.
    
* Use the "**ssh**" command to connect to your instance:
    

```bash
ssh -i path/to/your/key.pem ec2-user@instance-public-ip
```

* Replace "path/to/your/key.pem" with the path to your private key file.
    
* "ec2-user" is the default username for Amazon Linux instances.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705309426396/f22ae2ac-fa85-4145-ab3a-47562a5d4046.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705309430539/7767ae8f-87a2-478d-b665-832cb61b591c.png align="center")

**5\. Connecting via RDP (Windows Instances):**

* Download the Remote Desktop File provided in the AWS Console.
    
* Open the Remote Desktop Client on your local machine.
    
* Provide the instance's public IP address and credentials.
    

**6\. Managing EC2 Instances:**

* Start, stop, reboot, or terminate instances from the EC2 Dashboard.
    
* Adjust instance settings like security groups, IAM roles, or instance type as needed.
    
* Monitor performance metrics, logs, and set up alerts.
    

**7\. EC2 Best Practices:**

* Regularly create Amazon Machine Image (AMI) backups.
    
* Implement security best practices, such as using Security Groups effectively.
    
* Utilize AWS services like AWS Systems Manager for efficient instance management.
    

🌐 **Key Takeaways:**

* Creating an EC2 instance involves selecting an AMI, choosing an instance type, configuring settings, and launching.
    
* Connect to Linux instances via SSH and Windows instances via RDP.
    
* Regularly manage and monitor instances for optimal performance and security.
    

**These are instance states available in EC2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705309981318/c50ce1a1-84fa-4713-b0e3-3e3f9bc4aacf.png align="center")

### **Will create simple webpage using nginx on EC2:-**

* `sudo apt-get update`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705310628642/7e019060-e75c-47e1-add4-1dbc4fe46b6f.png align="center")

* `sudo apt-get install nginx`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705310659438/105d829f-a875-443b-a774-06cfabf72579.png align="center")

* `cd /var/www/html`
    
* `ls`
    
* `sudo vim index.html`
    

`<h1> This is my server </h1>`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705310695624/2662a296-d392-427a-8f08-369a0b1b9eab.png align="center")

* Esc:wq Enter
    
* `sudo systemctl restart nginx`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705310716380/81a11dcc-f5ca-4ad8-a9e3-622746036b16.png align="center")

* Take public IP of EC2 anf paste it in Browser "**3.92.224.183:80**"
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705310729555/fc3ff86b-b096-43bf-9aba-ff6bf11ebe09.png align="center")