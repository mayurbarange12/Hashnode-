---
title: "Day 2 - Linux Fundamental (Part-1)"
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
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699899882878/fea7e90d-b54a-4b7d-aafc-c2e2d125aca5.png align="center")

* `ls -l`\--&gt; Type the ls -l command to list the contents of the directory in a table format with columns including.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699899955007/22037b37-0ebd-4d50-96c7-67548d0da7dd.png align="center")

```plaintext
 - content permissions
 - number of links to the content
 - owner of the content
 - group owner of the content
 - size of the content in bytes
 - last modified date / time of the content
 - file or directory name
```

* `ls -a` --&gt; Type the ls -a command to list files or directories including hidden files or directories. In Linux, anything that begins with a . is considered a hidden file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699900024716/717f9d58-a9f7-49bc-a78a-04e969094f90.png align="center")

* `ls *.sh` --&gt; List all the files having .sh extension.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699900538612/f8397f17-716d-4883-95d2-2a8316713e20.png align="center")

* `ls -i` --&gt; List the files and directories with index numbers in order.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699900315288/8ee781df-b8d5-4b92-aec6-d7c8268b628e.png align="center")

* `ls -d */` --&gt; Type the ls -d \*/ command to list only directories.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699900442851/81d47ddb-f223-4b52-b10b-73a3b0f66518.png align="center")

## [**Directory Commands**](https://github.com/LondheShubham153/90DaysOfDevOps/blob/master/2023/day02/solution.md#directoy-commands)

* `pwd` --&gt; Print work directory. Gives the present working directory.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699900644162/45d699ce-958d-4751-a412-dc8b78f23ccc.png align="center")

* `cd path_to_directory` --&gt; Change directory to the provided path.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699900743730/88f00101-ea2c-49c9-8ab1-efb87f101fcf.png align="center")

* `cd ~` or just `cd` --&gt; Change the directory to the home directory.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699900806205/b4d827f9-acd2-4e73-b940-810e12ba3fb9.png align="center")

* `cd -` --&gt; Go to the last working directory.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699900881497/48751636-78ec-4ea5-8c04-f55c0f4313ca.png align="center")

* `cd ..` --&gt; Change the directory to one step back.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699900964076/b2953080-f0a8-4d90-8ade-c68a370c4d6f.png align="center")

* `cd ../..` --&gt; Use ls ../.. for contents two levels above.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699901114571/8c288532-2bb1-4504-8c19-aa2d9987b9ad.png align="center")

* `mkdir directoryName` --&gt; Use to make a directory in a specific location.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699901230850/685643b0-da2d-4a68-b851-734405c4141a.png align="center")

* `mkdir .NewFolder` --&gt; Make a hidden directory (also . before a file to make it hidden)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699901385755/01d7eff8-0cb1-4f2f-a578-d32430ab3176.png align="center")

* `mkdir A B C D` --&gt; Make multiple directories at the same time.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699901519128/7ea9e8f6-d95b-40f1-ac08-43feba8fdbb2.png align="center")

* `mkdir /home/user/Mydirectory` --&gt; Make a new folder in a specific location.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699901680993/1948272c-da3e-4add-9e76-c88c01163072.png align="center")

* `mkdir -p A/B/C/D` --&gt; Make a nested directory.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699901882267/6fcdd1c7-8738-46e6-8b7e-79045eccd0f1.png align="center")

**man** \[command\_name\] --&gt; Man is the built-in manual for utilizing Linux commands.

* If you don't know about Linux commands Linux will provide a manual to the user by using the command.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699901970142/4424d640-a34c-4661-95df-9e696dbb7cdc.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699902019547/0ac2bc9b-11ba-4ea5-a06b-49f3c3af8be3.png align="center")