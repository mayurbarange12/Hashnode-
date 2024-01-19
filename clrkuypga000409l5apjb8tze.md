---
title: "Day 33 - AWS S3:Static Website Hosting"
datePublished: Fri Jan 19 2024 16:31:40 GMT+0000 (Coordinated Universal Time)
cuid: clrkuypga000409l5apjb8tze
slug: day-33-aws-s3static-website-hosting
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1705675548681/c611ff55-f89f-4f59-a0fa-8a94aaf312c8.webp
tags: trainwithshubham-tws-devops-devopscommunity-shubhamlondhe-automation-awswithtws-7daysofaws-ec2-launchtemplates-userdatascripts-autoscaling-elasticloadbalancer-webapplicationfirewall-elb-waf-s3

---

# **Simple Storage Services (S3)**

Amazon S3 (Simple Storage Service) in AWS is a highly scalable and durable object storage solution. It allows you to store and retrieve any amount of data securely over the web. S3 is designed for 99.999999999% durability and offers features such as easy data management, access control, and seamless integration with other AWS services. It is commonly used for storing and retrieving files, hosting static websites, and supporting various data storage needs in cloud applications.

### <mark>What is the difference between a Bucket and an Object?</mark>

**Bucket:**

Top-level container for organizing and storing objects. Each bucket has a globally unique name.

**Object:**

The fundamental unit of data stored in S3 consists of data(files, code), a key, and metadata. Objects are stored within buckets, and each object in a bucket must have a unique key.

* On AWS Console search **S3** service.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705675998791/7a938cef-a5cc-41fb-8ce4-9af5c7a05342.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676003738/8b93cad9-fa3e-4c51-8095-b0c4c873fadc.png align="center")

* Click on **Create bucket**
    
* **Bucket name - aws-z-to-h-demo-bucket**
    
* **AWS Region** - **Asia Pacific (Mumbai) ap-south-1**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676044114/ad553863-008f-4ecc-90cf-69c33834737e.png align="center")

* **Object Ownership - Select ACLs disabled (recommended)**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676080152/2f4242f0-d720-4221-bc4c-3d3b84947215.png align="center")

* **Block Public Access settings for this bucket: unselect Block all public access** 
    
* **Turning off block all public access might result in this bucket and the objects within becoming public:**
    
    Select the box **I acknowledge that the current settings might result in this bucket and the objects within becoming public.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676139688/7dd1828c-af64-46f8-800b-05e6f16a4bba.png align="center")

* **Bucket Versioning: Disable**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676273574/d3092bdd-434a-42ab-a1eb-f9c8b6c75ebd.png align="center")

* **Tags- optional --&gt;** click on **Add tag**
    
* **Key: name**
    
* **Value:** **zero-to-hero**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676345349/e7fbd66c-7f95-4840-89c2-e9cbbb86cfb1.png align="center")

* **Default encryption:** Select **Server-side encryption with Amazon S3 managed keys (SSE-S3)**
    
* Click on **Create bucket**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676369746/8b0f2ea1-5ba1-44ac-966a-b1ba9872ae94.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676548290/d90d5a7d-d6e2-4539-9a50-1676f46a5b26.png align="center")

* Click on **aws-z-to-h-demo-bucket**
    
* Click on **Upload**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676721682/233c5ba3-845f-4ff1-ba6c-93dc5d91ce28.png align="center")

* Click on **Add files --&gt;** Here add any file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676772635/90b24b66-c2d4-43b5-be1f-2d4821228acb.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676776872/c50d3785-5c58-4c1a-9c13-4a5c5018a76c.png align="center")

* Add any file and click on **Upload.**
    
* Click on that file, If We want to share that file with anyone because it is public now and anyone can **Download** that file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676822979/1857b3e1-30b1-48c0-8227-905551662c13.png align="center")

* If we want to delete that file: Select that file and click on **Delete.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676850591/e32abc86-6e6f-4141-bcf9-d16fddacf23b.png align="center")

* **Permanently delete objects? -** Type **Permanently delete** and then click on **Delete objects.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676888496/909b9821-670e-47d9-a8b7-2038b7f3cd6c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676894462/b9757e51-4776-435d-a9e5-5ca6e80a6d6a.png align="center")

* If we want to **Delete Bucket:** Firstly Bucket should be **Empty** then Select that Bucket "**aws-z-to-h-demo-bucket**" then click on **Delete** type **Bucket Name** "**aws-z-to-h-demo-bucket**" and click on **Delete bucket.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676929545/af79095a-b229-4f47-862e-fd8b846fd8af.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676934345/635796d1-3767-4214-8a02-086a8eae0a32.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705676938940/40b96eb3-1ca4-46b4-807f-1c24adf2f1d2.png align="center")

### **<mark>Will Host Static Website on S3 Bucket</mark>**

* Click on **Create bucket**
    
* Bucket name **- aws-static-demo12**
    
* AWS Region - **Asia Pacific (Mumbai) ap-south-1**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705677312779/a31a1a34-4600-4fa7-9f51-7a96997e2c4e.png align="center")

* **Block Public Access settings for this bucket:** unselect **Block all public access** 
    
* **Turning off block all public access might result in this bucket and the objects within becoming public:**
    
    Select that box **I acknowledge that the current settings might result in this bucket and the objects within becoming public.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705677355499/26d0ca8d-3de8-4e55-b793-852358d1f892.png align="center")

* Click on **Create bucket**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705677434367/8d55b253-10ce-40f7-b04c-ca7acd979b63.png align="center")

* Click on "**aws-static-demo12**"
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705677438972/20ad3b7a-1595-45f3-a695-e05d90cbef94.png align="center")

* Click on **Properties**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705677456285/4cad1b11-dc9f-408e-95f5-cb3101b7ad17.png align="center")

* At bottom we will get **Static website hosting**
    
* Click on **Edit**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705677537237/0701e383-66fd-462a-8e4e-7c2dc2ab7d7b.png align="center")

* **Static website hosting:** Select **Enable**
    
* **Hosting type:** **Host a static website**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705677566358/49c34675-8e28-48aa-b672-0b7242533c35.png align="center")

* **Index document:** **index.html**
    
* **Error document:** **error.html**
    

* **Redirection rules** – *optional*  \--&gt; Click on **Learn more** we will get the structure JSON Script **Copy** that and **paste** it inside the **Redirection rules.**
    
* Click on **Save changes**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705677651748/08148e12-a2af-44d9-96ee-913cba6196bd.png align="center")

```bash
[
    {
        "Condition": {
            "KeyPrefixEquals": "home"
        },
        "Redirect": {
            "ReplaceKeyPrefixWith": "index.html"
        }
    }
]
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705677679691/cde4a4f6-0eb5-4955-b661-55cbeabb0abe.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705677968794/ddd5d4e1-4155-43f4-b531-b7986a307fe3.png align="center")

* When we click on the link of **Static website hosting** - [http://aws-static-demo12.s3-website.ap-south-1.amazonaws.com](http://aws-static-demo12.s3-website.ap-south-1.amazonaws.com)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705678138776/48447bf8-cd50-4244-8310-2dccff248761.png align="center")

* It is showing **403 Forbidden** error.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705678287960/54158aa9-dd44-40ec-a6ac-97dc2b93e37b.png align="center")

* Go to **Permissions**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705678314266/77cbc9ba-deb0-45a1-9102-b1b788cedf51.png align="center")

* **Bucket policy:** Click on **Edit**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705678366210/98b4c9de-f4ab-4d31-a79d-1cf05899b13d.png align="center")

**<mark>First way to generate Policy</mark>:**

* Click on **Policy examples** \--&gt; Here we will get policy examples which are written in JSON format.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705678444530/4a166e2c-018d-4960-87f1-d8921c273c74.png align="center")

* Enter below JSON Script inside the **Policy** section:
    

```bash
{
   "Version":"2012-10-17",
   "Statement":[
     {
       "Sid":"PublicReadGetObject",     
       "Effect":"Allow",
       "Principal":"*",   
       "Action":"s3:GetObject",  
       "Resource":"arn:aws:s3:::aws-static-demo12/*"   
     }
   ]
}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705678666345/0675ab00-55e9-4e4f-badd-dc3244346f82.png align="center")

**<mark>Second way to generate Policy</mark>:**

**Step 1: Select Policy Type**

* Click on **Policy generator**
    

**Step 2: Add Statement(s)**

* Select Type of Policy: **S3 Bucket Policy**
    
* Effect: **Allow**
    
* Principal: **\***
    
* Actions: **GetObject**
    
* Amazon Resource Name (ARN): **arn:aws:s3:::aws-static-demo12**
    
* Click on **Add Statement**
    

**Step 3: Generate Policy**

* Click on **Generate Policy**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705678724171/bd15247e-6fb1-4367-bf05-96780cc54f4b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705678729549/d18e47a0-fcef-40e0-8489-ba2bdfabc318.png align="center")

* We will follow the **First way** and click on **Save changes.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705678744201/3b070b07-1604-4a32-b983-557296a330f5.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705678784380/1bc844a4-b7d1-41f3-a197-6b81071ef782.png align="center")

* If we refresh that **Static website hosting** - [http://aws-static-demo12.s3-website.ap-south-1.amazonaws.com](http://aws-static-demo12.s3-website.ap-south-1.amazonaws.com) --&gt; Now it shows a different error (**404 Not Found**) Because we have not uploaded "**index.html**" inside S3 Bucket "**aws-static-demo12**".
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705679195796/b5f75a8c-27af-42f2-8333-4eb40ee7f9f0.png align="center")

* We are writing **index.html** file
    

```bash
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Welcome To My Website</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background-color: #f5f5f5;
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .container {
      text-align: center;
    }

    .button {
      display: inline-block;
      padding: 10px 20px;
      font-size: 16px;
      text-align: center;
      text-decoration: none;
      outline: none;
      cursor: pointer;
      border: 2px solid #3498db;
      color: #3498db;
      background-color: transparent;
      border-radius: 25px;
      transition: background-color 0.3s, color 0.3s;
      margin: 10px;
    }

    .button:hover {
      background-color: #3498db;
      color: #ffffff;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Welcome To My Static Website Using S3 Buckets</h1>
    <a href="#" class="button">Button 1</a>
    <a href="#" class="button">Button 2</a>
    <a href="#" class="button">Button 3</a>
  </div>
</body>
</html>
```

* Copy and paste the code in **VS Code** and save it as **index.html** on the desktop location**.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705679551812/a8de93c4-14e8-4257-a276-0ebe7390d75b.png align="center")

* **Amazon S3** --&gt; **Buckets**  --&gt; **aws-static-demo12** \--&gt; **Upload --&gt; Add files --&gt; index.html --&gt;** Click on **Upload**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705679623002/db1c8280-3e52-42a0-aabc-2d7b0aee6c68.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705679672967/67fd6604-a387-4cce-b07c-aa93ceea4eb1.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705679678766/82fd6aaa-70ca-41fc-af3b-c0cab05c7488.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705679684106/da214de4-5ee6-431f-a81a-6ece17187ca8.png align="center")

* Now If we refresh that **Static website hosting** - [http://aws-static-demo12.s3-website.ap-south-1.amazonaws.com](http://aws-static-demo12.s3-website.ap-south-1.amazonaws.com) on Web Browser.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705679716169/26cf1147-6bcb-42b2-b0f9-d7d893489a12.png align="center")

* If we type this random link [http://aws-static-demo12.s3-website.ap-south-1.amazonaws.com/profile](http://aws-static-demo12.s3-website.ap-south-1.amazonaws.com/profile) it will show an error.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705680116728/bf4588a4-5377-454d-b6c3-59e634aa06b1.png align="center")

* Now If we want to show a **proper error page**.
    

```bash
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Error - Page Not Found</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background-color: #f5f5f5;
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      text-align: center;
    }

    .container {
      background-color: #ffffff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }

    h1 {
      color: #e74c3c;
    }

    .button {
      display: inline-block;
      padding: 10px 20px;
      font-size: 16px;
      text-align: center;
      text-decoration: none;
      outline: none;
      cursor: pointer;
      border: none;
      border-radius: 5px;
      color: #ffffff;
      background-color: #3498db;
      transition: background-color 0.3s;
    }

    .button:hover {
      background-color: #2980b9;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Page Not Found</h1>
    <p>Sorry, the requested page could not be found.</p>
    <a href="index.html" class="button">Go to Home Page</a>
  </div>
</body>
</html>
```

* Copy and paste the above code in **VS code** on the **desktop location** and save it as **error.html**
    
* **Amazon S3** --&gt; **Buckets**  --&gt; **aws-static-demo12** --&gt; **Upload --&gt; Add files --&gt; error.html --&gt;** Click on **Upload**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705680478940/aab3829f-45b9-49d2-8111-51e54a3d7de9.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705680697791/d4d13125-b467-4a9a-8b0a-925787e7077c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705680701992/62cb20b9-fdfe-4513-976b-de3822718544.png align="center")

* Click on **upload**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705680731047/0e93141c-fdc2-4acd-a4e4-9d32c3184405.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705680735547/6d50eede-bde6-412a-9933-d1068bd137ca.png align="center")

* Now If we refresh again that **Static website hosting** - [http://aws-static-demo12.s3-website.ap-south-1.amazonaws.com/profile](http://aws-static-demo12.s3-website.ap-south-1.amazonaws.com/profile) on the web Browser it will show a proper error page.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705680779532/b83df280-a8f5-489c-93bc-247af9c00c21.png align="center")