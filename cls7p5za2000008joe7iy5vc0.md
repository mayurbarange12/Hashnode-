---
title: "Day 37 - AWS RDS, EC2, DynamoDB with Lambda (part -2)"
datePublished: Sun Feb 04 2024 16:08:04 GMT+0000 (Coordinated Universal Time)
cuid: cls7p5za2000008joe7iy5vc0
slug: day-37-aws-rds-ec2-dynamodb-with-lambda-part-2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707040391541/129f6710-8dda-4d5b-90df-d9cbbd624a1e.png
tags: trainwithshubham-tws-devops-devopscommunity-shubhamlondhe-automation-awswithtws-7daysofaws-ec2-iam-roles-policies-rds-dynamodb-lambda-boto3

---

# DynamoDB

DynamoDB is a fully managed NoSQL database service by AWS, offering seamless scalability and low-latency access to store and retrieve any amount of data. It is designed for high-performance, flexible, and serverless applications.

* Search **DynamoDB**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707058413407/c6823e83-f994-4c0d-8d61-a888d0a90e83.png align="center")

* Click on **Create table**
    
* Table name: **learners**
    
* Partition key: **learner\_id  - String**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707058427855/8cfd3794-72a6-488e-9cfe-a00e20c0a761.png align="center")

* Table settings: **Default settings**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707058450118/852819dc-e901-4e5a-8f46-3617a5019081.png align="center")

* Click on **Create table**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707058462175/bf27942f-a6dc-4454-b58d-de2e0529bab6.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707058468805/2ddf6c18-a7ee-47f6-9dea-664d7bd6ac1d.png align="center")

* How to add data in **DynamoDB** using **Lambda**.
    

# **Lambda**

AWS Lambda is a **serverless** computing service, enabling you to run code without managing servers. It automatically **scales**, **executes code** in response to events, and charges based on compute time. it is used for **cost optimization.**

* Search **lambda**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707058769258/cf34c228-4714-4657-a364-ee3f8e53d2b2.png align="center")

* Click on **Create function**
    
* Select **Author from scratch**
    
* Function name: **insert-into-dynamo**
    
* Runtime: **Python 3.12**
    
* Click on **Create function**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707058787680/336ff842-0aae-4d3a-95fb-8e5d5528550f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707058804828/00b75bd7-8ee7-41e1-8f6d-f204490864b3.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707058809337/aae0a795-73b6-4e9b-8487-23a6bfb9c7a0.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707058814238/13d8873b-aa2b-492c-9134-0c0771de3523.png align="center")

* Removed --&gt; **#TODO implement**
    
* Add --&gt; **print ("hello Dosto")**
    
* Click on **Deploy**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707058829141/fa0d6534-0574-46d6-95b4-109b3de66547.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707058833277/80ff1e1d-2663-456b-8cb9-05aeff82de7a.png align="center")

* Click on **Test  --&gt; Function** run through **Event**.
    
* Event name: **insert-event**
    
* **Event JSON:**
    

```json
{
	"message":"Hello Dosto" 
}
```

* Click on **Save**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707058932816/83ea8188-3f70-46d5-873f-11f29bba6895.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707058936314/91dc4d2d-93b8-4142-aa05-0b4b37e88f01.png align="center")

* Click on the **Test** drop-down **insert-event**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707059032079/c80972b2-cad8-46ff-983d-0a773f89d193.png align="center")

* Click on **Test**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707059041636/ba1c15cc-1548-4693-b45b-b0e00f4d4ea0.png align="center")

* Click on **lambda\_function**
    

```json
print(event["message"]) 
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707059085208/68eca27e-2a35-401b-8b0d-7c9d0fd77f64.png align="center")

* Click on **Test**  \--&gt; **Hello Dosto** will Print.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707059133590/5694df5a-f2fc-4b8e-973a-c9345119cacf.png align="center")

* If I make changes in **Test.**
    

```json
{
	"message":"Hello Dosto from AWS"
}  
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707059221910/b909507a-9c4f-47cd-9bc8-23d945a266d6.png align="center")

* Click on **Test**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707059232198/fc3ace92-f023-4b74-9d80-92cda51d700a.png align="center")

* Click on **Details**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707059245776/2d948fb4-b0f5-4fee-b8db-1fc07c9eedb4.png align="center")

* If you want to insert data in Dynamodb, you will have to establish a connection between Dynamodb and Python. Python library will be required for that.
    
* **Code --&gt; lambda\_function**
    

```json
import boto3
```

### **<mark>boto3</mark>**

Boto3 is the Amazon Web Services (AWS) Software Development Kit (SDK) for Python, enabling developers to interact with AWS services programmatically.

```json
import json
import boto3

def lambda_handler(event, context):
	print(event["message"])
	dynamodb = boto3.resource("dynamodb")
	table = dynamodb.table("learners")
	items = table.get_item()
	return {
	        'statusCode': 200,
	        'body': json.dumps('Hello from Lambda!')
	    }
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707060017439/3c93e784-2638-4ef8-a828-39704b8c84ce.png align="center")

### **<mark>How to add an item</mark>**

* **DynamoDB --&gt; Tables --&gt; learners --&gt; Action --&gt; Create item**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707060075463/c3f0f15b-3308-47c5-8a3b-b2dfc7d923d3.png align="center")

* Value: **1**
    
* Click on **Create item**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707060092224/789462c1-6c46-4027-b400-36366eaaa6d7.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707060109486/afdcf1c3-d588-4e14-b09d-1865db54a4af.png align="center")

* **Lambda --&gt;**
    

```json
import json
import boto3

def lambda_handler(event, context):
	print(event["message"])
	
	# Establish connection to DynamoDB Resource
	dynamodb = boto3.resource("dynamodb")
	
	# Get the table learners
	table = dynamodb.Table("learners")
	
	# Get item from table
	items = table.get_item(Key={"learner_id":"1"})
	
	return {
	        'statusCode': 200,
	        'body': json.dumps('Hello from Lambda!')
	    }
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707060867410/95df5d6f-5b54-4a48-a8b4-50af661ebe1d.png align="center")

* Click on **Deploy**
    
* Click on **Test**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707060880509/5dea0ac0-e8b1-4ca4-b864-1c4887ab7b7a.png align="center")

* **Lambda functions** do not have access to **DynamoDB** and will give access through **IAM Role** so follow the below steps.
    
* **IAM  --&gt; Roles --&gt; Create role --&gt;** Use case: **lambda  --&gt; Next --&gt;** Search **Dynamodb:** Select **AmazonDynamoDBFullAccess --&gt;** Search **Cloudwatch:** Select **CloudWatchEventsFullAccess --&gt;** Click on **Next --&gt;** Role name: **lambda-to-access-dynamodb --&gt;** Click on **Create role.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061373877/9319d265-4ce1-41a8-b2e8-179c7cb0f3b5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061377283/f8ef34cf-f7b6-4d8b-8fec-f062a4b04a0f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061381497/01d7b24e-319b-46a2-a2e0-52de303e35d5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061385059/9bcca2c3-69b1-47a5-9d34-8caa59a346de.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061389065/22faef77-268c-4984-ae47-50367bb40a07.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061393425/793327c9-d487-4a6f-ba62-99324c180ca8.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061401595/740219d9-a3f1-4a39-b53e-e3a961a6a91e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061406087/6f82dbfb-f5ba-4881-b12e-6e1f205e85a2.png align="center")

* **Lambda --&gt; Functions --&gt; insert-into-dynamo --&gt; Configuration --&gt; Permissions --&gt; Execution role --&gt; Edit --&gt; Existing role --&gt;** Select **lambda-to-access-dynamodb --&gt;** Click on **Save.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061444103/f906b016-1181-4e7a-94c4-5c56dd1557cc.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061448236/1a95e6d4-d5c9-402f-9602-83aafbb0f5e0.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061452175/1dc40a85-b225-4cb4-9226-4d8296572fa9.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061456616/52711446-5b41-4e29-9385-7a03d45fed15.png align="center")

* Click on **Test** 
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061485860/6157d1d5-bc5c-42da-a458-d78ade188488.png align="center")

* **Lambda --&gt; Code**
    

```json
import json
import boto3

def lambda_handler(event, context):
    print(event["message"])
    
    # Establish connection to DynamoDB Resource
    dynamodb = boto3.resource('dynamodb', region_name='us-east-1')
    table = dynamodb.Table('learners')
    
    items_to_insert = {
        'learner_id': '2',
        'learner_name': 'mayur',
        'learner_location': 'pune'
    }
    
    try:
        response = table.put_item(Item=items_to_insert)
        print(response)
        
        return {
            'statusCode': 200,
            'body': json.dumps('Items inserted successfully')
        }
    except Exception as e:
        print(str(e))
        return {
            'statusCode': 200,
            'body': json.dumps(str(e))
        }
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061531100/dcfe5dc6-3dbb-42dd-bb90-082c92ed64d6.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061566990/9c166bac-d230-481b-bdb0-2489626ed9fe.png align="center")

*  It is inserted into the **DynamoDB** --&gt; learner\_id=2, learner\_location=pune, learner\_name=mayur.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061591312/76063418-afc3-4e0b-aee8-903420751dce.png align="center")

### **<mark>Insertion in Lambda through Event</mark>**

* **If we want to input items through Events.**
    
* Click on **Test  --&gt; Configure test event**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061709098/8f64031e-967b-499c-8f83-e22f83f8cc5f.png align="center")

```json
{
  "message":"Hello Dosto from AWS",
  "learner_id":"5",
  "learner_name":"divya",
  "learner_location":"punjab"
}
```

* Click on **Save**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061734466/7337fbda-3a6c-4cb1-8534-057a4a765fc7.png align="center")

* **Lambda --&gt; Functions --&gt; insert-into-dynamo --&gt; Code --&gt; lambda\_function**
    

```json
import json
import boto3

def lambda_handler(event, context):
    print(event["message"])
    
    # Establish connection to DynamoDB Resource
    dynamodb = boto3.resource('dynamodb', region_name='us-east-1')
    table = dynamodb.Table('learners')
    
    items_to_insert = {
        'learner_id': event["learner_id"],
        'learner_name': event["learner_name"],
        'learner_location': event["learner_location"]
    }
    
    try:
        response = table.put_item(Item=items_to_insert)
        print(response)
        
        return {
            'statusCode': 200,
            'body': json.dumps('Items inserted successfully')
        }
    except Exception as e:
        print(str(e))
        return {
            'statusCode': 200,
            'body': json.dumps(str(e))
        }
```

* Click on **Deploy** and **Test**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061820689/4a7affb2-0c6d-4a30-90e3-40e35d83a3c6.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061823967/5e403442-d20c-4a1c-899d-896f6f305a3d.png align="center")

### **<mark>Deletion in Lambda through Event</mark>**

* **Lambda  --&gt; Functions --&gt; Create function --&gt;** Function name: **delete-from-dynamo --&gt;** Runtime: **Python 3.11 --&gt; Create function.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061907149/6e0d371e-1af7-4bae-84cf-d17490c0c04c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061911767/bab1badd-d92e-4ec3-95cf-2197f9a33ad3.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061915622/15fabf30-c0ed-404c-80e6-0119199b4b57.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061919299/3027e6b4-ae01-401f-ae36-b13020d0b160.png align="center")

* **Lambda --&gt; Functions --&gt; delete-from-dynamo  --&gt; Configuration --&gt; Permissions --&gt; Edit --&gt;** Existing role: **lambda-to-access-dynamodb --&gt; Save.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061971944/429073a0-21ff-41b5-aee1-eb7e9b41684e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061977065/b515d367-8edb-4c85-ab86-0d0f02613c6b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061982165/9486323a-303c-4bb2-9af2-8335205cd45c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707061986637/b877812f-3fbf-4ad3-af07-710b61fdf4f9.png align="center")

* **Copy** code from **insert-into-dynamo** and **paste** it into the **delete-from-dynamo** and make some **changes.**
    

```json
import json
import boto3

def lambda_handler(event, context):
    
    dynamodb = boto3.resource('dynamodb', region_name='us-east-1')
    table = dynamodb.Table('learners')
    
    key_to_delete = {
        'learner_id': event["learner_id"]
    }
    
    try:
        response = table.delete_item(Key=key_to_delete)
        print(response)
        
        return {
            'statusCode': 200,
            'body': json.dumps('Item deleted successfully')
        }
    except Exception as e:
        print(str(e))
        return {
            'statusCode': 200,
            'body': json.dumps(str(e))
        }
```

* Click on **Deploy**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707062047289/9753120d-05f4-4c48-9001-169ff338c0fc.png align="center")

* Click on the **Test** drop-down and select **Configure test event.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707062074992/77571799-37e3-4a62-a52b-b1a9a4d081f2.png align="center")

* Event name: **delete-event**
    

```json
{
  "learner_id":"1"
}
```

* Click on **Save**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707062124393/6784e977-6416-4a23-9cdd-6d2ba85d017d.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707062128549/2dbf5cec-f891-4817-b4f7-f19f8ff5f446.png align="center")

* Click on **the Test** drop-down and click on **delete-event**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707062166354/948cb918-50bf-49ab-ab79-df1a45262f73.png align="center")

* Click on **Test**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707062189674/f2a7c9df-5fa4-4681-a3a1-37e92dfd7c5f.png align="center")

* From **DynamoDB "learner\_id: 1"** is **deleted** successfully.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707062237963/868d3742-a3e3-4b77-9ba0-8b4c4f88d94f.png align="center")