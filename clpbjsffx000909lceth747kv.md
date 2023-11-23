---
title: "Day 7 - Basic Git & GitHub for DevOps"
datePublished: Thu Nov 23 2023 18:49:31 GMT+0000 (Coordinated Universal Time)
cuid: clpbjsffx000909lceth747kv
slug: day-7-basic-git-github-for-devops
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700760658689/b51bc45c-089f-4379-9d98-7b11c7d104d6.jpeg
tags: github, git, devops, 90daysofdevops, shubhamlondhe, trainwithshubham, tws

---

## What is Git?

Git is a version control system that allows you to track changes to files and coordinate work on those files among multiple people. It is commonly used for software development, but it can be used to track changes to any set of files.

With Git, you can keep a record of who made changes to what part of a file, and you can revert back to earlier versions of the file if needed. Git also makes it easy to collaborate with others, as you can share changes and merge the changes made by different people into a single version of a file.

## What is GitHub?

GitHub is a web-based platform that provides hosting for version control using Git. It is a subsidiary of Microsoft, and it offers all of the distributed version control and source code management (SCM) functionality of Git as well as adding its own features. GitHub is a very popular platform for developers to share and collaborate on projects, and it is also used for hosting open-source projects.

## What is Version Control? How many types of version controls we have?

Version control is a system that tracks changes to a file or set of files over time so that you can recall specific versions later. It allows you to revert files back to a previous state, revert the entire project back to a previous state, compare changes over time, see who last modified something that might be causing a problem, who introduced an issue and when, and more.

There are two main types of version control systems:

* **Centralized Version Control Systems.**
    
* **Distributed Version Control Systems.**
    

## **Centralized Version Control Systems**

A centralized version control system (CVCS) uses a central server to store all the versions of a project's files. Developers "check out" files from the central server, make changes, and then "check in" the updated files. Examples of CVCS include Subversion and Perforce.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700761274459/2ece74d7-d1f3-465a-8803-54a2725acba9.png align="center")

## **Distributed Version Control Systems.**

A distributed version control system (DVCS) allows developers to "clone" an entire repository, including the entire version history of the project. This means that they have a complete local copy of the repository, including all branches and past versions. Developers can work independently and then later merge their changes back into the main repository. Examples of DVCS include Git, Mercurial, and Darcs.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700761367916/49119675-ffac-4df2-b86b-20e81feedb1d.png align="center")

## Why we use distributed version control over centralized version control?

1. Better collaboration: In a DVCS, every developer has a full copy of the repository, including the entire history of all changes. This makes it easier for developers to work together, as they don't have to constantly communicate with a central server to commit their changes or to see the changes made by others.
    
2. Improved speed: Because developers have a local copy of the repository, they can commit their changes and perform other version control actions faster, as they don't have to communicate with a central server.
    
3. Greater flexibility: With a DVCS, developers can work offline and commit their changes later when they do have an internet connection. They can also choose to share their changes with only a subset of the team, rather than pushing all of their changes to a central server.
    
4. Enhanced security: In a DVCS, the repository history is stored on multiple servers and computers, which makes it more resistant to data loss. If the central server in a CVCS goes down or the repository becomes corrupted, it can be difficult to recover the lost data.
    

Overall, the decentralized nature of a DVCS allows for greater collaboration, flexibility, and security, making it a popular choice for many teams.

## Exercises:

1. Create a new repository on GitHub and clone it to your local machine:
    

`git clone <Repository-Url>`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700761955000/d3532107-6417-4eab-8abb-dd74cc14498e.png align="center")

Create a new folder in your local machine and right-click into that folder, open git bash and type the below command:

* `git clone` [`https://github.com/mayurbarange12/demo.git`](https://github.com/mayurbarange12/demo.git)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700762473633/796fbb90-cfa1-40ba-b7b8-e9e4e21033e8.png align="center")

1. Make some changes to a file in the repository and commit them to the repository using Git:
    

`git add <Filename>` `.(dot) = All`

`git commit -m "Your Message"`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700762900691/613c1265-b18c-4a19-87eb-c2cf42601878.png align="center")

1. Push the changes back to the repository on GitHub:
    

`git push <Repository-Url>`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700763386002/06f298a7-abb6-4ef5-aef6-c4b16ca3eab7.png align="center")

## Today I learned these commands in Git:

* `git init` --&gt; Initializes a new Git repository in the current directory, setting up the necessary files and structure for version control.
    
* `git add <Filename>` --&gt; Stages the specified file for the next commit in Git.
    
* `git commit -m "Your Message"` --&gt; Captures changes in the code with a descriptive message for version control.
    
* `git rm --cached <Filename>` --&gt; Removes a file from Git's staging area while preserving it in the working directory.
    
* `git status` --&gt; Displays the current status of the repository, showing changes to tracked files, staged modifications, and untracked files.
    
* `git restore <Filename>` --&gt; Reverts changes in the specified file to the last committed version.
    
* `git diff <Filename>` --&gt; Displays the differences in a specific file between the working directory and the staging area in Git. \[**It will be used for only untracked files**\]
    
* `git log --oneline --preety` --&gt; Displays a concise one-line view of commit history with customized formatting in Git.
    
* `git config --global user.name "Your Name"` --&gt; Sets the global username for Git usage across all repositories.
    
* `git config --global user.email "Your Email"` --&gt; Sets the global email address for Git usage across all repositories.
    
* `git config -l` \--&gt; Lists all the Git configurations set on your system.
    
* `git push <Repository-Url>` --&gt; Pushes committed changes from your local repository to the specified remote repository URL in Git.
    
* `git pull <Repository-Url>` --&gt; Updates your local repository with changes from the remote repository
    
* `git fork <Remote-Repository-Url>` --&gt; Git fork creates a copy of a repository, allowing independent experimentation or contributions without altering the original codebase.