---
title: "Day 36 - AWS RDS, EC2, DynamoDB with Lambda (part -1)"
datePublished: Sun Feb 04 2024 09:11:32 GMT+0000 (Coordinated Universal Time)
cuid: cls7aabn3000008jq2zj9b8cq
slug: day-36-aws-rds-ec2-dynamodb-with-lambda-part-1
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1706974504062/98266071-57c0-4a64-bd8a-a082e0acbfa2.avif
tags: trainwithshubham-tws-devops-devopscommunity-shubhamlondhe-automation-awswithtws-7daysofaws-ec2-launchtemplates-iam-users-roles-policies-rds-dynamodb-lambda

---

# RDS

RDS stands for **Relational Database Service**, a fully managed database service by AWS that automates database administration tasks, offering support for various relational database engines like MySQL, PostgreSQL, Oracle, SQL Server, and MariaDB.

* Search RDS in AWS Console.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706974873892/f955dfcd-3bc6-48ab-bb18-e7b9c1b1d6b1.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706974886030/f8db962d-a240-44c2-a5f4-b5cdeb91289b.png align="center")

**DB Instances:** A DB instance in AWS refers to a running database environment provisioned by Amazon RDS, supporting various relational database engines.

**DB Clusters:** A DB Cluster in AWS is a managed database cluster by Amazon RDS, offering high availability and scalability with a primary DB instance and multiple replicas.

**Snapshots:** Snapshots in Amazon RDS are point-in-time copies of a database instance's data, crucial for data recovery and creating new instances with specific configurations.

* Click on **Create Database**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706974934521/23f309e5-3352-4b10-980d-73679631d56f.png align="center")

* Choose a database creation method: **Standard create**
    
* Engine option: Select **MySQL**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706974951856/e17ab326-6a6f-4f4c-acf1-91ff81c21b6d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706974956626/941eb841-5aaa-4b81-be02-426bc41deccc.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706974962618/51e0cba6-c560-4af9-877a-9fc29b087e7d.png align="center")

* Templates: select **Free tier**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975003330/ff40592f-fa64-4850-af72-059864c5a10e.png align="center")

* DB Instance Identifier: **database-1**
    
* Master username: **admin**
    
* Master password: **admin123**
    
* Confirm Master password: **admin123**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975017237/a3e866dd-0d37-4451-ad9f-3155f54712b9.png align="center")

* Instance Configuration:
    
* Burstable classes(includes t classes): **db.t3.micro** (By default it is selected)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975055478/0c448d7b-a4d6-4e50-9c13-d017c8ec3020.png align="center")

* Storage: **20 GiB**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975145490/34ff2e7c-5f34-459a-95cf-81de9d30701e.png align="center")

* Database authentication: **Password authentication**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975169032/1fd22071-0e97-43e5-a0ab-17d065ee8b48.png align="center")

* Click on **Create database**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975192977/b7f28918-f606-48ee-94f6-a72e79d39df3.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975214710/f08728aa-b54d-4541-a66d-6df30aa6b84c.png align="center")

* For the creation of the Database, it will take nearly 15 Min or Less.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975256042/d1dc89b3-c382-4bf4-9738-056bcc6e1e38.png align="center")

* Now we will create an EC2 instance that connects with RDS(Server) and in EC2 will install Mysql client, also will do in RDS(Server) data insert and delete.
    

**Now will create an EC2 instance in the same region: N.Virginia**

* Click on **Launch instance**
    
* Name of EC2 --&gt; **EC2-to-RDS-demo**
    
* AMI: **select Ubuntu**
    
* Instance type: **t2.micro**
    
* Key pair **\--&gt; Create key pair --&gt; Key pair name: RDS-key --&gt;** Click on **Create key pair**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975645736/f4be537c-e877-4a40-8cf2-04fb98737b05.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975650503/a0672c1c-4053-4f13-ad6b-be76d342ae7f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975655024/92f93c48-982e-443e-a8c8-7e66edc7d82a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975660912/cfe63887-393b-461c-b2ad-0f024452b935.png align="center")

* Click on **Launch instance**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975673507/9aa46baf-8ce1-40b3-ad60-1e9fbc831377.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975678651/fb87480e-0bf1-4dd6-852c-71395f47fc4e.png align="center")

* **Select the EC2 Instance and connect it through SSH client in the terminal or command prompt.**
    
* `sudo apt-get update`
    
* `sudo apt install mysql-client`
    
* `sudo apt-get install mysql-client`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975909672/d0cdc758-a028-4b19-81c0-7bd98d8bd0de.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975913400/c0a7b922-79a4-484a-995d-a80b39d6b16e.png align="center")

* `mysql -u root -p` --&gt; We can check through this command in the local system whether databases are running or not.
    
    `enter password: root`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706975975733/292d346e-7645-4633-826d-9ca21a347477.png align="center")

**RDS --&gt; Databases --&gt; database-1**

* `mysql -u admin -h database-1.cuqxi1ttp3jg.us-east-1.rds.amazonaws.com -P 3306 -p`
    
    \--&gt;  -h = host  | -P = Port  | -p = password
    
* `Enter password: admin123`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706976283322/573a7f0e-30be-4a52-9f99-e145eb1ab312.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706976287845/9c61bb64-2033-48c7-8f10-bef43f540b79.png align="center")

* To communicate between **EC2** and **RDS** will follow below steps:
    
* **Go to RDS --&gt; Databases --&gt; database-1 --&gt; Connectivity & security --&gt; Connected compute resources --&gt; Set up EC2 connection --&gt;** Select **listed one --&gt;** Click on **Continue.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706976455252/1632b414-1079-490e-8634-aac33d9c274c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706976458531/e4c56cf7-d90d-4ec1-abae-90a3506d1a83.png align="center")

* Connecting **EC2** and **RDS** will create **VPC**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707027960671/262a6c60-e9d3-4d4d-809d-fcb61e5c128f.png align="center")

* Click on **Set up**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707027975903/d4ad4e82-7702-4c10-9a00-64ae6325a3a2.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707027983973/1e082b02-3630-48d4-9efa-5191b278a5b2.png align="center")

**First way to access EC2 to RDS connection do a sudo reboot**

* `sudo reboot`
    
* `mysql -u admin -h database-1.cuqxi1ttp3jg.us-east-1.rds.amazonaws.com -P 3306 -p`
    
* `Enter password: admin123`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028302104/fa31802e-9b29-429a-9a42-6500fcc3a1e8.png align="center")

**Second way through creating IAM role for access of EC2 to RDS and vice versa**

* Search **IAM  --&gt;** Click on **Roles  --&gt; Create role --&gt; Trusted entity type: AWS service --&gt; Use case:** select **EC2 --&gt; Next --&gt;** Search **RDS:** select **AmazonRDSFullAccess --&gt;** Search **Cloudwatch:** select **CloudWatchEventsFullAccess --&gt;** Click on **Next.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028471137/1f9f3b64-bfc6-4ee6-b887-b8d5766c9298.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028475647/a37600bd-5711-4420-a973-b1cc8e75f764.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028478962/82eb66ca-1b42-4acf-af8f-154dc74a0e54.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028483443/a1fc4799-1d4f-4b3e-9059-2db6c2a1fa96.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028492040/66014be7-fc9a-45aa-9ef6-501323fbdb56.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028501372/063cd0fc-7380-4e22-b9bf-25aa21a43ff8.png align="center")

* Role name: **ec2-to-access-rds**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028531183/d34c3d7e-29c0-4cfe-aafd-729ba93033a4.png align="center")

* Click on **Create role**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028546154/f1f3e5f3-804d-4250-b9ff-6fddaf465d89.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028551807/b1cff056-5438-49d3-90e2-18e39b9db6d8.png align="center")

* **Goto EC2 instance(EC2-to-RDS-demo) --&gt;** Select **EC2-to-RDS-demo --&gt; Actions --&gt; Security --&gt;** Click on **Modify IAM role**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028580788/17bcb2c6-8942-482f-aaa1-0b67926ec9c5.png align="center")

* Choose **IAM role --&gt; ec2-to-access-rds --&gt;** Click on **update IAM role**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028605362/94a96be3-7e7c-481b-8e97-ec49155c655a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028609942/3d7c8958-a6a2-4014-839b-ee03a234eea4.png align="center")

* `mysql -u admin -h database-1.cuqxi1ttp3jg.us-east-1.rds.amazonaws.com -P 3306 -p`
    
* `Enter password: admin123`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028693067/67409c22-089c-4195-b1bc-f0164db974d9.png align="center")

* `show databases;`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028708660/cd203826-976f-4b52-beda-13f26d41fd41.png align="center")

* `create database aws;`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028726561/59ec47c1-e495-49ff-99c6-160b1c753018.png align="center")

* `show databases;`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028741282/958d8023-521d-49b6-b689-a305b6776bf0.png align="center")

* `use aws`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028757675/b2b0d0d3-9964-484e-96ed-1b96280b6c4f.png align="center")

* `CREATE TABLE learners (learner_id INT, learner_name VARCHAR(50));`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028775644/b37ed1a7-b55e-4e27-9c11-1c8285c9992c.png align="center")

* `select * from learners;`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028789504/690e6501-7ad2-4c37-9dcf-192178f37923.png align="center")

* `insert into learners (learner_id, learner_name) values (1,"Mayur");`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028800413/4797b607-1a17-4253-85b4-fed29e8c9e55.png align="center")

* `select * from learners;`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028846730/1d599484-e590-4492-8a26-4198482c3b40.png align="center")

* `delete from learners where learner_id=1;`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028888451/5acc2407-c146-4e0d-858c-83aebe5fdf30.png align="center")

* `select * from learners;`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707028908446/30f22853-9ec7-4c7c-b692-8f2e897f9f52.png align="center")