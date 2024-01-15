---
title: "Day 20 - Jenkins Pipeline Scripts From SCM and Agents"
datePublished: Fri Dec 22 2023 13:15:18 GMT+0000 (Coordinated Universal Time)
cuid: clqgnmbw9000008jmag05965k
slug: day-20-jenkins-pipeline-scripts-from-scm-and-agents
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1703243139757/3b0c5999-f3d1-4ace-9456-e9ce630b7ac5.png
tags: automation, devops, jenkins, cicd-cjy1vtdk2005kjjs17n8couc3, 90daysofdevops, shubhamlondhe, trainwithshubham, 90daysofdevopschallenge, jenkins-pipeline, tws, jenkins-agent

---

# <mark>Jenkins Pipeline Scripts From SCM</mark>

The practice of storing Jenkins Pipeline scripts in source control repositories (SCM) like Git, allowing for version control, collaboration, and the ability to trigger Jenkins jobs directly from the code repository.

* **Select "Pipeline script from SCM" and specify Git Project URL:** [**https://github.com/mayurbarange12/node-todo-cicd**EndFragment](https://github.com/mayurbarange12/node-todo-cicd)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703243918530/f141ddd9-233c-40c3-bf85-2099697855c4.png align="center")

* **Save it**
    
* **Build Now**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703244387041/ae16ed2c-9267-4d00-863a-c7ca3baf5d8c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703244391477/e0e064f4-3af9-4aff-9183-3c5983b49233.png align="center")

# **<mark>Agent</mark>**

An agent in Jenkins represents the execution environment where Jenkins jobs or pipelines run, allowing control over where and how the build or deployment processes take place.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703244731508/5c0a3e53-1649-456b-aad3-18d280fbcbdc.jpeg align="center")

**<mark>Note</mark>:- "Jenkins-Master" will connect with "Jenkins-Agent" through "SSH".**

* Will Create a new **EC2 Instance** named as "**jenkins-agent**" - AMI = **ubuntu** - Key pair named as **"jenkins-server-key"** - Click on Launch instance.
    
* Now Check both EC2 Instances "**jenkins-server**" and "**jenkins-agent**" should be running in the same **Networking -&gt;"VPC ID"-&gt; vpc-0b42d4e165da3765a**
    
* In **Master "Jenkins"** should be installed but In **Agent** no need to install **"Jenkins".**
    
* In **Master** and **Agent** both need to installed **"Java".**
    
* In **Master** and **Agent** both need to installed **"Docker & Docker-Compose".**
    

Jenkins-Master(Private IP-**172.31.47.94**)

Jenkins-Agent(Private IP-**172.31.13.187**)

* `cd Downloads/`
    
* `ssh -i "jenkins-server-key.pem"` [`ubuntu@ec2-18-216-126-61.us`](mailto:ubuntu@ec2-18-216-126-61.us)`-east-2.compute.amazonaws.com`
    

**Inside "Jenkins-Master":**

* `cd .ssh/`
    
* `ls`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703245584639/0a67c3e3-d899-4143-8dc3-f7b3585b6c33.png align="center")

Now will create **"Private key"** in **Jenkins-Master:**

* `ssh-keygen`
    
* **Enter 3 Times**
    
* `ls`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703245906441/230362af-492c-44b4-a69a-d94316e29779.png align="center")

* **"id\_rsa"** is a **Private Key** that will be put in the **Jenkins-Master.**
    
* **"id\_rsa.pub"** is a **Public Key** that will be put in the **Jenkins-Agent.**
    
* Inside **Jenkins-Master -&gt;** Enter this command - `cat id_rsa.pub`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703246169876/21cb2cf7-4461-474e-aa9b-4624df275b28.png align="center")

Copy this **"id\_**[**rsa.pub**](http://rsa.pub)**"** key and paste it inside "**Jenkins-Agents**" **\-&gt;** "**authorized\_keys**" file.

**Inside "Jenkins-Agents":**

* `cd .ssh/`
    
* `ls`
    
* `vim authorized_keys`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703246448479/c347c265-54ba-4373-bee7-bc55955617b7.png align="center")

* Inside "**Jenkins-Agent"** "**id\_rsa.pub**" key is pasted in the "**authorized\_keys**" file.
    

**Esc:wq Enter**

**\[** Now we need to build a connection in between **"Jenkins-Master"** and **"Jenkins-Agent" \]**

**Inside "Jenkins-Master":**

* `ssh ubuntu@18.216.126.61`
    

\[18.216.126.61 is a ienkins-agents -&gt; Public IP address\]

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703247288404/179302f2-cbc6-49b7-b7e6-ebb5f1550415.png align="center")

**Inside "Jenkins-Agent":**

* `sudo apt update`
    
* `sudo apt install fontconfig openjdk-17-jre` **\--&gt;** To install Java in "Jenkins-Agent"
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703247455838/38134b9a-1a4f-4316-8ed2-03c6a3958fdc.png align="center")

* Now will be connect **"Jenkins"** to **"Jenkins-Agent":**
    
* Dashboard -&gt; Manage Jenkins -&gt; Nodes -&gt; Click on New Nodes -&gt; Enter Node name: **dev-server** -&gt; Select Permanent Agent -&gt; Create.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703247877579/695354c5-aadc-42c8-adeb-23078ec9cac8.png align="center")

* **Add Description - This is my dev server.**
    
* **Number of Executors:- 1**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703247894293/539191ca-824d-4577-b5b7-4f58c6541691.png align="center")

**Inside "Jenkins-Agent":**

* `cd ..`
    
* `mkdir jenkins-workspace`
    
* `ls`
    
* `cd jenkins-workspace/`
    
* `pwd`
    

`/home/ubuntu/jenkins-workspace` --&gt; Copy and paste it in remote root directory.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703248068884/77ae6305-5921-4dc2-acdc-7a48ee9c34cf.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703248074068/08ac361e-1bb8-43a3-9881-248bcae7d12c.png align="center")

* **Labels -&gt; dev-server**
    
* **Usage -&gt; Only build jobs with label expressions matching this node**
    
* **Launch method -&gt; Launch agents via SSH**
    
* **Host -&gt; 18.216.126.61** --&gt; \[Jenkins-Agent Public IP Address\]
    
* **Credentials -&gt; Click on Add -&gt; Jenkins -&gt; Kind -&gt; SSH Username with private key -&gt; ID - dev-agent-key -&gt; Description - dev agent key -&gt; Username - ubuntu -&gt; Private key - click on Enter directly**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703248405122/cf12bc80-577d-4160-ac72-c2d122b18a27.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703248410096/f76cdac3-b613-4ff8-8a73-39cff32261a2.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703248415050/c476ac17-fe97-41c3-b714-4603db7f98ee.png align="center")

**Inside "Jenkins-Master":**

* `cd .ssh/`
    
* `ls`
    
* `cat id_rsa`  --&gt; Copy "Private key" and paste it in private key section of Jenkins.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703248487383/3cac20a3-7f51-4276-9615-5a262b898fcb.png align="center")

* **Copy** the above **"Private Key"** from **"Jenkins-Master"** and Pasted in the **Private key section of Jenkins**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703248821791/475b8667-ee14-4860-a792-4006dd112c2d.png align="center")

* **Click on Add button.**
    
* **In Credentials Select "ubuntu(dev agent key)"**
    
* **Host key Verification Strategy - Select "Non verifying Verification Strategy"**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703248874650/d1d0782b-0506-4f26-928c-da4a67e64e62.png align="center")

* **Save it**
    
* **Click on "dev-server"**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703248912773/622806a1-dda9-4714-88a0-341bdd2b6139.png align="center")

* It gets failed with **"id\_rsa"** and **"id\_rsa.pub"** key.
    

### **<mark>Now will try with different key called as</mark>** **<mark>"ed25519"key</mark>**

**Inside "Jenkins-Master":**

* `ssh-keygen -t ed25519` **\--&gt;** \[-t = type\]
    
* **Give any name - ed-key**
    
* **Enter 2 times**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703249210310/721d3b5f-3bd8-4d5f-a724-fc8347d35ca6.png align="center")

* `ls`
    
* `cat ed-key`
    
* `cat ed-key.pub`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703249245834/c11f1eaf-3c46-47a3-8554-a1f19ef9cd1f.png align="center")

* Will copy and paste **"ed-key.pub" Public key** inside **"Jenkins-Agent"**
    
    **\-&gt;** "`vim authorized_keys`" file.
    
* Will copy and paste **"ed-key" Private key** inside **"Jenkins"**
    

**Inside "Jenkins-Agent":**

* `cd .ssh/`
    
* `ls`
    
* `sudo vim authorized_keys`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703249837136/a9e3d870-af68-4452-a642-5bc915ee0413.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703249856034/6aef013b-b2c8-4e87-acf4-88f6e63f3d31.png align="center")

**Will change Private key in Jenkins: Dashboard -&gt; Manage Jenkins -&gt; Credentials -&gt; System(global) -&gt; Global credentials(unrestricted) -&gt; Replace new Private key (ed-key)**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703249990373/7f634bfb-ff2b-4dbb-bd7c-20935c3157c2.png align="center")

* **Disconnect "dev-server" once.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703250015534/81e9c282-3f00-47a2-adb6-642a508e1f78.png align="center")

* **Click on Launch agent**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703250039925/2ff536d1-4153-4916-9089-7f3a328fc8c4.png align="center")

* **Agent is connected Successfully and Online.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703250054674/9848fa47-a144-4ffc-b615-62af42522419.png align="center")

* Now will change is GitHub project **"node-todo-cicd" - agent { label "dev-server"}**
    
* **Commit Changes in Github.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703250120226/5ac1a0f7-a621-4c4a-8b89-2a56b83fe9ad.png align="center")

* **Build Now**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703250141928/a73848ef-8754-4af2-943a-06c67aa4fbef.png align="center")

**Inside "Jenkins-Agent":**

* **sudo apt-get install** [**docker.io**](http://docker.io) **docker-compose**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703250177090/e02c73fe-c7d1-4e2b-ac74-6aff32cd5e8b.png align="center")

* **Build Now**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703250200212/6dcdbda5-f9c7-45b7-9957-2e344f6486bc.png align="center")

* **sudo usermod -aG docker ubuntu**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703250217875/81ee1917-7785-4420-ba4c-c9ef3615b70f.png align="center")

* **Build Now**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703250238368/2dc8081d-7391-40c5-a8f1-30b8ba96841c.png align="center")

* Inside EC2 Instance\*\*(jenkins-agent)\*\* --&gt; **Security port should be allowed**: **Security** -&gt; **Inbound Rule** -&gt; Edit Inbound Rule -&gt; Port:**8000** and Source:**Anywhere-IPV4** -&gt; save rules.
    
* Search on Browser "EC2 instance Public IP-**18.216.126.61:8000**" It will be Run.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1703250354279/59a7b370-26ac-4a98-9523-ec3e5c8802ad.png align="center")