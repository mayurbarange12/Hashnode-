---
title: "Day 17 -Jenkins Freestyle Project"
datePublished: Tue Dec 19 2023 06:14:50 GMT+0000 (Coordinated Universal Time)
cuid: clqbya1rh000409l2ghc79g8p
slug: day-17-jenkins-freestyle-project
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702965101152/16466978-b791-4a7e-8bdf-37a7afd7bb47.avif
tags: devops, jenkins, cicd-cjy1vtdk2005kjjs17n8couc3, 90daysofdevops, shubhamlondhe, trainwithshubham, freestyle-jenkins-project, 90daysofdevopschallenge, tws

---

## **What is CI/CD?**

* CI or Continuous Integration is the practice of automating the integration of code changes from multiple developers into a single codebase. It is a software development practice where the developers commit their work frequently into the central code repository (Github or Stash). Then there are automated tools that build the newly committed code and do a code review, etc as required upon integration. The key goals of Continuous Integration are to find and address bugs quicker, make the process of integrating code across a team of developers easier, improve software quality and reduce the time it takes to release new feature updates.
    
* CD or Continuous Delivery is carried out after Continuous Integration to make sure that we can release new changes to our customers quickly in an error-free way. This includes running integration and regression tests in the staging area (similar to the production environment) so that the final release is not broken in production. It ensures to automate the release process so that we have a release-ready product at all times and we can deploy our application at any point in time.
    

## **What Is a Build Job?**

A Jenkins build job contains the configuration for automating a specific task or step in the application building process. These tasks include gathering dependencies, compiling, archiving, or transforming code, and testing and deploying code in different environments.

Jenkins supports several types of build jobs, such as freestyle projects, pipelines, multi-configuration projects, folders, multibranch pipelines, and organization folders.

## **What is Freestyle Project ?? 🤔**

A freestyle project in Jenkins is a type of project that allows you to build, test, and deploy software using a variety of different options and configurations. Here are a few tasks that you could complete when working with a freestyle project in Jenkins**:**

## **Task to Create a Freestyle Project to print Hello Dosto and Date:-**

* **Click on "Create a job" or "New Item"**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702965223759/0b51d09a-e331-412a-8f2b-8113a69f9d56.png align="center")

* **Enter an item name - hello-dosto**
    
* **Select - Freestyle Project**
    
* **Click on "OK"**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702965324938/b067e8e4-6c1e-42e3-9be6-7b4de43a8ef0.png align="center")

* **Specify Description.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702965338969/950d3183-6e52-45cf-983f-cd60212cbec9.png align="center")

* **Enter Git Repository URL**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702965487255/93dcb0c0-c0cf-44e8-9b00-db785c5c9c35.png align="center")

* **Inside Build Steps -&gt; Enter Shell Commands**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702965541938/b2816209-62ff-4561-bc98-6c27b4e8923f.png align="center")

* **Save it**
    
* **Click on Build**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702965611610/45f9a50c-fefb-493f-b876-2f5388d4a055.png align="center")

* **Enter Shell Command -&gt; To Print Date**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702965684132/1620891b-6b2b-4e61-b080-9774383f23c3.png align="center")

* **Save it**
    
* **Click on Build**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1702965822075/fe9ecd81-cfeb-4478-a27f-8d0e9b50d1a2.png align="center")