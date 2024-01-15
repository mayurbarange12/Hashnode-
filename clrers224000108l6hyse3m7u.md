---
title: "Day 31 - AWS EC2 Launch Templates & User Data Scripts"
datePublished: Mon Jan 15 2024 10:15:54 GMT+0000 (Coordinated Universal Time)
cuid: clrers224000108l6hyse3m7u
slug: day-31-aws-ec2-launch-templates-user-data-scripts
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1705311119367/5659a583-149a-4b44-b82d-f59446bdc382.avif
tags: trainwithshubham-tws-devops-devopscommunity-shubhamlondhe-automation-awswithtws-7daysofaws-ec2-launchtemplates-userdatascripts

---

## **<mark>How to create template of EC2 in AWS?</mark>**

Firstly go to Instances --&gt; Select Running EC2 instance "**Test-Machine**" --&gt; Click on **Actions** --&gt; Select **Image and Templates** --&gt; Click on **Create template from instance** --&gt; Mention Launch template name --&gt; **zero-to-hero-template** --&gt; template version description --&gt; **v1** --&gt; Finally click on Create launch template.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705312089672/d0051a4c-0beb-47e4-aec8-070c019c7fef.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705312093282/f14d785a-982b-495c-8f56-ecbb468bbfbc.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705312097952/3a9cba4b-0cde-40c4-aa58-6d39459df1fd.png align="center")

* Click on **Create launch template**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705312185929/da9931d3-dc14-43ce-ab83-c545f337c72c.png align="center")

* Now **terminate** the Running Instance "**Test-Machine**".
    
* Go to top left 3 dots --&gt; **Launch Templates**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705312236075/6e4a5385-c6d4-4cfb-abba-f7975d96bc72.png align="center")

* Select **zero-to-hero-template** --&gt; **Actions** --&gt; Click on **Launch instance from template.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705312268308/840d2ae4-f8fb-43ef-9a16-4ee84771ac1b.png align="center")

## **<mark>User Data Scripts</mark>**

In AWS, user data scripts automate tasks during the launch of an EC2 instance, handling actions like software installation. They are written in scripting languages, executed during instance creation, and useful for configuring initial settings.

* Select **zero-to-hero-template** --&gt; **Actions** --&gt; Launch instance from template
    
    \--&gt; **Advanced details** -&gt; Below you will see **User data** option.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705312684359/c5e04ff1-0639-47b2-adcd-2341c835233d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705312724952/b9fdbac0-4a43-40fa-a0fa-1feb316e9e95.png align="center")

* click on left hand side **Launch Templates** --&gt; Select template "**zero-to-hero-template**" --&gt; **Actions** --&gt; **Modify template(Create new version)** --&gt; Template version - **v2**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705312757663/36924d08-9796-489c-bdd0-942f81e6c394.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705312883199/3992a934-faac-423c-8818-d802bbfcb56f.png align="center")

* Now click on **Advanced details** --&gt; Advanced details is a **Shell Script**.
    

```bash
	#!/bin/bash  
	
	sudo apt-get update -y
	sudo apt-get install nginx -y
	
	sudo echo "hello dosto, Server IP address is $(hostname -i)" > /var/www/html/index.html
	
	sudo systemctl restart nginx
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705312964146/af6422af-1a37-4232-94db-3ae4846b68fb.png align="center")

* click on **Create template version**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705312977869/dfee9205-842a-4613-bfd6-1648005c6a71.png align="center")

* Click on **Launch Templates** --&gt; Select "**zero-to-hero-template**" --&gt; Actions --&gt; Launch instance from template --&gt; Select Version **v2** --&gt; Launch instance.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705313009874/6d4949d2-43ab-4206-a6b4-6dbc6c1fa09d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705313032556/2985f0fe-2ceb-42af-a91f-2d1cc16250f5.png align="center")

* Take recently created "**zero-to-hero-template**" instance Public IP **"107.21.74.153:80"** check in browser URL. It is working now.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705313295235/54e9aefd-71cc-46c9-baf1-28eb14e2e064.png align="center")