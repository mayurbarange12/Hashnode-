---
title: "Day 16 - Jenkins Fundamentals"
datePublished: Mon Dec 18 2023 17:21:01 GMT+0000 (Coordinated Universal Time)
cuid: clqb6mwsn000308jvcq71bm2t
slug: day-16-jenkins-fundamentals
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702917562373/61ad3778-c33c-47da-8819-a4f1ef9cd501.jpeg
tags: automation, devops, jenkins, cicd-cjy1vtdk2005kjjs17n8couc3, 90daysofdevops, shubhamlondhe, trainwithshubham, tws

---

# **<mark>What is Jenkins</mark>:-**

Jenkins is a popular open-source automation server for continuous integration (CI) and continuous delivery (CD). It assists developers in automating the software development, testing, and deployment processes. Jenkins is a powerful tool for increasing the quality and speed of software development. It offers a vast plugin ecosystem and supports various programming languages and tools, facilitating efficient software development practices.

### **<mark>Key Concepts in Jenkins</mark>:-**

* **Jobs:** A job is a collection of steps that are executed sequentially. Jobs are used to automate tasks such as building, testing, and deploying software.
    
* **Builds:** A build is the execution of a job. When a build is triggered, Jenkins will run the steps in the job one by one.
    
* **Agents:** Agents are machines that execute the steps in a job. Agents can be physical machines or virtual machines.
    
* **Plugins:** Plugins are extensions that add functionality to Jenkins. There are thousands of plugins available, which allows Jenkins to be customized to meet the specific needs of a project.
    
* **Pipelines:** A pipeline is a series of connected jobs. Pipelines are used to automate complex workflows, such as building, testing, and deploying a software application.
    

### **<mark>Features of Jenkins</mark>:-**

* **Easy to use:** Jenkins has a user-friendly interface that makes it easy to create and manage jobs.
    
* **Extensible:** Jenkins is highly extensible through plugins. There are plugins available for a wide variety of tasks, such as building, testing, and deploying software.
    
* **Scalable:** Jenkins can be scaled to meet the needs of large organizations. It can be run on a single server or on a cluster of servers.
    
* **Open source:** Jenkins is an open-source project. This means that it is free to use and modify.
    
* **Community-supported:** Jenkins has a large and active community of users and developers. There are many resources available to help you learn how to use Jenkins.
    

### **<mark>Benefits of Jenkins</mark>:-**

⚙️ **Automation Powerhouse:** Jenkins automates the entire software development lifecycle, from building and testing to deployment, saving time and reducing manual errors.

🛠️ **Extensibility with Plugins:** Its vast plugin ecosystem allows seamless integration with various tools, enabling customization to fit specific project requirements.

🚀 **Continuous Integration & Delivery:** Facilitates CI/CD pipelines, ensuring continuous integration of code changes, testing, and deployment, enhancing development agility.

🔒 **Robust Security Measures:** Provides authentication, access control, and encryption features, safeguarding CI/CD environments and sensitive data.

🔄 **Scalability & Flexibility:** Easily scales to accommodate growing projects, with distributed builds and load balancing capabilities, adapting to evolving development needs.

📊 **Performance Monitoring:** Offers monitoring tools and metrics, enabling real-time performance analysis for optimizing Jenkins' efficiency and reliability.

🤝 **Collaboration & Notifications:** Promotes team collaboration by sending notifications on build statuses, facilitating efficient communication among team members.

💡 **Infrastructure as Code (Jenkinsfile):** Empowers defining the entire build process as code through Jenkinsfile, enhancing consistency and reproducibility.

🔧 **Troubleshooting & Debugging:** Provides robust logging and debugging features, aiding in identifying and resolving issues within the CI/CD pipeline effectively.

### **<mark>How to Install and Configure Jenkins(Practical example)</mark>:-**

* Create an EC2 Instance in **Ohio** region named as "**jenkins-server**" - Ubuntu Image - Launch instance.
    
* Search on google "**Install jenkins on ubuntu**". --&gt; go to first link --&gt; click on Dedian/Ubuntu --&gt; Install **Java** first.
    
* `sudo apt update`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702919023782/fe684d1a-7409-49a1-9bc2-3997e337791c.png align="center")

* `sudo apt install fontconfig openjdk-17-jre`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702919189093/7d313693-13dc-495e-bba4-9223d9b706cd.png align="center")

```bash
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702919445221/fca9e2a8-4e0f-4a2f-ae1f-251e24b93266.png align="center")

* `Jenkins --version`
    
* `systemctl status jenkins`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702919503553/24c2e580-27ea-429b-9b74-8d6939b9db91.png align="center")

* EC2-instance port **8080** should be allowed:- **Security** -&gt; **Inbound Rule** -&gt; Edit Inbound Rule -&gt; Port:**8080** and Source:**Anywhere-IPV4** \-&gt; save rules.
    
* Search on Browser "EC2 instance Public IP-**18.116.27.188:8080**" It will be Run.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702919706473/ae994456-bd0c-479f-82cc-635077f8e9d1.png align="center")

* `sudo cat /var/lib/jenkins/secrets/initialAdminPassword`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702919729969/ec06609a-79a6-4ef0-8318-38088d7f1ee5.png align="center")

* Enter that password and click on Continue.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702919781111/c9ef83a1-2026-48da-90bd-6f4fcee0c8bd.png align="center")

* Click on "**Install suggested plugins**".
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702919806717/8868b25d-6ef5-4361-90a2-0a3997034425.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702919812948/f2259a30-5fb6-4039-ac94-68743560ba7c.png align="center")

* Enter details & Click on "**Save and Continue"**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702919848781/cb507af5-9400-44e9-ae7b-d834d3c25803.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702919859496/2bbe8142-616f-402e-ae74-57884acae843.png align="center")

* Click on "**Save and Finish"**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702919946535/8810662d-566d-4346-abd6-5a075817c6a4.png align="center")

* Click on "**Start using Jenkins**"
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702919965698/bc0b6a49-46e5-4625-b983-b5217c12b648.png align="center")