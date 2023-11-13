---
title: "Day 2 - Linux Fundamental"
datePublished: Mon Nov 13 2023 08:11:06 GMT+0000 (Coordinated Universal Time)
cuid: clowmkwri000009i961g9hnf3
slug: day-2-linux-fundamental
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699856745807/d14494ee-013b-482f-9f56-608d127086aa.png
tags: 90daysofdevops, shubhamlondhe, trainwithshubham, 90daysofdevopschallenge, tws

---

# Introduction

Linux is a robust and open-source operating system kernel that serves as the foundation for a diverse family of Unix-like operating systems. Initial development was spearheaded by Linus Torvalds, a Finnish computer science student. Linus Torvalds released the first version of the Linux kernel on September 17, 1991. Renowned for its stability, security, and flexibility, Linux has become a cornerstone in the world of computing. Developed collaboratively by a global community of contributors, Linux powers a vast array of devices, from servers and desktop computers to embedded systems and mobile devices. Its open-source nature encourages customization, enabling users to tailor their Linux-based environments to specific needs. With a reputation for efficiency and scalability, Linux has emerged as a preferred choice for developers, sysadmins, and organizations seeking a reliable and adaptable operating system that embodies the principles of open collaboration and innovation.

## Basic Linux Commands

* `ls` --&gt; The ls command is used to list files or directories in Linux and other Unix-based operating systems.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699858597632/678216fa-3329-4f2b-8fd3-eb56ae00ea3b.png align="left")
    
    * `ls -l`\--&gt; Type the ls -l command to list the contents of the directory in a table format with columns including.
        
        ```plaintext
         - content permissions
         - number of links to the content
         - owner of the content
         - group owner of the content
         - size of the content in bytes
         - last modified date / time of the content
         - file or directory name
        ```
        

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699858836508/6bf9f8f5-741d-4cfc-bb7c-9c414d0fa624.png align="center")

* `ls -a` --&gt; Type the ls -a command to list files or directories including hidden files or directories. In Linux, anything that begins with a . is considered a hidden file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699858980429/e84650be-d436-4be0-be65-33cb7ece1bfc.png align="center")

* `ls *.sh` --&gt; List all the files having .sh extension.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699859266142/2f93b1da-485a-43cb-b4b8-facb55112238.png align="center")

* `ls -i` --&gt; List the files and directories with index numbers in orders.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699859628259/c15da720-3b32-4e59-84fd-97be46c3ccc1.png align="center")

* `ls -d */` --&gt; Type the ls -d \*/ command to list only directories.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699859843074/737dc2e7-f8c9-42ef-95bf-1d3a82f6f548.png align="center")

## [**Directory Commands**](https://github.com/LondheShubham153/90DaysOfDevOps/blob/master/2023/day02/solution.md#directoy-commands)

* `pwd` --&gt; Print work directory. Gives the present working directory.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699860027461/4f13a448-9937-4c46-830f-4a0aa97bddb4.png align="center")

* `cd path_to_directory` --&gt; Change directory to the provided path.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699860181808/2aaab08d-8a91-4073-87c2-ba78dbe5cc99.png align="center")

* `cd ~` or just `cd` --&gt; Change the directory to the home directory.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699860290279/d102a553-d693-4427-978e-9678a907556f.png align="center")

* `cd -` --&gt; Go to the last working directory.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699860405448/54bbf1bc-eb10-4f01-a9e7-e30f2cde801b.png align="center")

* `cd ..` --&gt; Change the directory to one step back.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699860503672/67ce58a0-f0c5-4099-9313-40b4d788b99f.png align="center")

* `cd ../..` --&gt; Use ls ../.. for contents two levels above.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699860677090/032dfc3e-83e8-4639-8bf1-bec2c0058df4.png align="center")

* `mkdir directoryName` --&gt; Use to make a directory in a specific location.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699860894868/19790ef2-e589-4e5c-9f2d-a78a4467fc90.png align="center")

* `mkdir .NewFolder` --&gt; Make a hidden directory (also . before a file to make it hidden)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699861006686/898a7bb7-2f48-4915-b406-6a476b109277.png align="center")

* `mkdir A B C D` --&gt; Make multiple directories at the same time.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699861107509/f0f9cd74-b71f-4dec-ab37-79b8788ecf6d.png align="center")

* `mkdir /home/user/Mydirectory` --&gt; Make a new folder in a specific location.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699861429282/c08132b9-5e62-4786-b6ba-16330589908c.png align="center")

* `mkdir -p A/B/C/D` --&gt; Make a nested directory.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699861664387/424a39ed-951a-4134-89de-333c3ab8d893.png align="center")

## Some Helpful Commands

* man \[command\_name\] --&gt; Man is the built-in manual for utilizing Linux commands.
    
    If you don't know about Linux commands Linux will provide a manual to the user by using the command.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699862696512/182ff570-a688-4eef-8c3e-d512d2ff6f81.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699862765591/b8c0c6cb-1e4a-4727-83b0-5507907da53a.png align="center")

Thank you for reading this Blog. Hope you learned something new today! If you found this blog helpful, please like, share, and follow me for more blog posts like this in the future.

You can connect with me at: [https://www.linkedin.com/in/mayurbarange/](https://www.linkedin.com/in/mayurbarange/)