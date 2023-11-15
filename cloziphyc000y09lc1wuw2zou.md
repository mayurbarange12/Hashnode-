---
title: "Day 4 - Basic Linux Commands"
datePublished: Wed Nov 15 2023 08:46:00 GMT+0000 (Coordinated Universal Time)
cuid: cloziphyc000y09lc1wuw2zou
slug: day-4-basic-linux-commands
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700034831747/47bed72a-66aa-4812-b7d2-21b54eadf0cf.jpeg
tags: linux, trainwithshubham, 90daysofdevopschallenge, tws, devopsengineer

---

# **Basic Linux Concepts**

## **File Permissions**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700034324317/0f688b8d-f80c-4dd0-8a19-39dfbe91906e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700034339247/62e9263d-7762-43b9-a56c-d19c4d6ae50d.png align="center")

**chmod :-** The chmod, or change mode, command allows an administrator to set or modify a file's permissions. Every UNIX/Linux file has an Owner user, Group and Other Users attached to it, and every file has permissions associated with it. The permissions are as follows: read, write, or execute.

**How to change the Permission of File?**

* **chmod 777 &lt;FileName&gt;           \[eg:- chmod 744 Colors.txt\]**
    
* **ls -l    --&gt;** (displays the contents of the current directory in a long listing format, one per line)
    

**Note :-** When any file changes to executable(777) then it will turn into a "**Green**" color.

**How to Create User in Linux?**

* **sudo useradd -m &lt;UserName&gt;** **\--&gt;** -m = make a folder
    
* **sudo cat /etc/passwd** **\--&gt;** It will displays the system's user account information.
    

**Note :-** Whenever a user creates an adjacent group that user will be created automatically.

**How to create Group in Linux?**

* **sudo groupadd &lt;GroupName&gt;**
    
* **sudo cat /etc/group --&gt;** It will displays a list of all groups and their respective information.
    

**How to add Single User in a Group?**

* **sudo gpasswd -a &lt;UserName&gt; &lt;GroupName&gt; --&gt;** -a = add a user
    

**How to check Ownership of File/Directory?**

* **ls -l \* --&gt;** Lists detailed information about all files and directories in the current directory.
    

**How to change Group Ownership of any File/Directory?**

* **sudo chgrp &lt;GroupName&gt; &lt;File/Directory Name&gt;**
    
    \[Changes the group ownership of a specified file or directory to the specified group name using superuser privileges.\]
    

## **SSH/SCP :-**

**SSH - (Secured Shell)**

 SSH (Secure Shell) in Linux is a cryptographic network protocol that enables secure and encrypted communication between two devices over an insecure network, ensuring the confidentiality and integrity of data exchanged. It provides a secure avenue for remote access, allowing users to log into a remote machine securely, execute commands, transfer files, and tunnel other network services securely over an encrypted channel.

* Create an EC2 instance and connect through **SSH Client**.
    
* Open command prompt(Windows)/terminal(Linux) and type "**ssh**" to check ssh client is installed or not.
    
* Locate your private key file. The key used to launch this instance is &lt;Private\_Key\_Name&gt;.pem
    
* **ssh -i "&lt;Private\_Key\_Name&gt;.pem"** [**ubuntu@ec2-54-221-173-161.compute-1.amazonaws.com**](mailto:ubuntu@ec2-54-221-173-161.compute-1.amazonaws.com)
    
* If you want log-out type the "**exit**" command.
    

**SCP - (Secured Copy Protocol)**

 SCP, or Secure Copy Protocol, is a command-line tool in Linux used for securely transferring files between a local and remote host or between two remote hosts over a Secure Shell (SSH) connection. It provides encryption and authentication, ensuring secure file transfers. SCP operates similarly to the cp command but adds encryption capabilities, enabling users to securely copy files and directories between systems. SCP is widely used in Linux for its simplicity and secure file transfer capabilities over SSH.

* Connect an EC2 instance through a Web Browser.
    
* Now I want to copy a file from **Source**: Local System to **Destination**: Remote Server(EC2)
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700037546837/c566e02a-e9de-4cf5-ac5e-6905981055fd.png align="center")
    
* Now I want to copy a file from **Source**: Remote Server(EC2) to **Destination**: Local System.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700037690802/6ad2a1ef-fcfa-4baf-b3a8-d4dd0a01767b.png align="center")
    

**Note**:- All commands will be run in the Local System because the Private-key is in the Local System.