---
title: "Day 3 - Linux Fundamental (Part-2)"
datePublished: Mon Nov 13 2023 19:43:26 GMT+0000 (Coordinated Universal Time)
cuid: cloxbb8sk00020ajy5bv31on0
slug: day-3-linux-fundamental-part-2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699881661431/b69d3853-e8f0-48d8-a822-01035c3da5d3.png
tags: linux, devops, trainwithshubham, 90daysofdevopschallenge, tws

---

# Basic Linux Commands

**Mostly Used Commands in DevOps**:

1\. To view what's written in a file

* `cat filename`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699884467960/c7029a5c-6712-4a87-998f-10bd314f92cf.png align="center")

2\. To change the access permissions of files.

* `chmod 777 foldername`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699884636169/cf1fb11c-f11b-4260-bc69-e32f42e92b13.png align="center")

3\. To check which commands you have run till now.

* `history`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699884743293/8101ee9f-0688-435f-beb3-6d17b8b5eb90.png align="center")

4\. To remove a directory/ Folder.

* `rm -r foldername`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699884870831/52305f44-0c5a-4091-9691-2dcabf31008a.png align="center")

5\. To create a fruits.txt file and to view the content.

* `vim fruits.txt`
    
* cat fruits.txt
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699885329929/67b8d20e-9db9-4e9f-a40d-c2677af7d167.png align="center")

6\. Add content in devops.txt (One in each line) - Apple, Mango, Banana, Cherry, Kiwi, Orange, Guava.

* `vimdevops.txt`
    
* cat devops.txt
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699886923554/a69e02f8-a687-4022-8cf1-85c09eb4245d.png align="center")

7\. To Show only top three fruits from the file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699898349103/2582a847-633b-4123-866f-378d178c5870.png align="center")

8\. To Show only bottom three fruits from the file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699898457472/ab08a268-4ff6-4f41-8674-867118fd25c5.png align="center")

9\. To create another file Colors.txt and to view the content.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699898722863/d4b96b1a-0c3b-4723-8d95-49321dd4f258.png align="center")

10\. Add content in Colors.txt (One in each line) - Red, Pink, White, Black, Blue, Orange, Purple, Grey.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699899052229/ab7c9fd1-6b80-4b6b-9fe3-8024d5604a57.png align="center")

11\. To find the difference between fruits.txt and Colors.txt file.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1699899234620/afc4e61c-96f8-431a-8753-8c9cc30b21fe.png align="center")

## Some Important Commands

**1\. Sudo:** This command executes only that command with superuser privileges.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQF-KxTDXUC6OA/article-inline_image-shrink_1500_2232/0/1671202870928?e=1705536000&v=beta&t=HsOZxqvqxcvNoF4SGXf-AoNwxFWgOZ3ZaEnqrtU6_Qk align="left")

**2\. Cat:** This is used to concatenate and display files on the terminal. It can also be used to modify existing ones.

***cat -b:*** This adds line numbers to non-blank lines

***cat -n:*** This adds line numbers to all lines

***cat -s:*** This squeezes blank lines into one line

***cat –E:*** This shows $ at the end of the line

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQFX2ZTvZDGfUw/article-inline_image-shrink_1500_2232/0/1671203017878?e=1705536000&v=beta&t=NAp5TKVBCiqkG8LYUYPimd2w52Hqpz3PGWMvu5AcYQQ align="left")

**3\. Vim:** This is a text editor used in Linux. It stands for “Vi Improved”.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQHFszYQzynT2g/article-inline_image-shrink_1500_2232/0/1671203035027?e=1705536000&v=beta&t=Et3VMLQTaoztXuyKqQVTxMlSkFBFZwV5HNIT7QlmGQc align="left")

Mostly used modes in VIM:

* **Normal mode:** This is the default mode in which vim starts. In normal mode, you can use various commands to navigate and edit the text.
    
* **Insert mode:** In insert mode, you can type text into the file. To enter insert mode, press the "i" key. To exit insert mode and return to normal mode, press the "Esc" key.
    
* **Command mode:** In command mode, you can enter commands to perform various actions, such as saving the file or quitting vim. To enter command mode, press the ":" key.
    

**4\. Grep:** (Global Regular Expression Print)This command searches for a particular string/ word in a text file. This is similar to “Ctrl+F” but executed via a CLI.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQHxKcfcfhRX8w/article-inline_image-shrink_1500_2232/0/1671203095927?e=1705536000&v=beta&t=ozjVBC163minpqYtYURBZYsa_XGPUNv1h6PL6VAUUbw align="left")

This would print all of the lines in “chxtan.txt” that contain the word “This".

**5\. Sort:** This command is used to sort the results of search either alphabetically or numerically. It also sorts files and directories.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQEgu6Paz3GTgg/article-inline_image-shrink_1500_2232/0/1671203130514?e=1705536000&v=beta&t=P73JFjhDKPi4Bdm0oxzOK8kOXG018iHDC-jd3bOGxow align="left")

***sort -r:*** the flag returns the results in reverse order.

***sort -f:*** the flag does case-insensitive sorting.

***sort -n:*** the flag returns the results as per numerical order.

**6\. Tail:** This command prints the last N number of data of the given input. By default, it prints 10 lines.

We can specify the number of lines, that we want to display.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQGt--B3XF0wWw/article-inline_image-shrink_1500_2232/0/1671203289035?e=1705536000&v=beta&t=pVIE5nDnT18FfW7tKeCCWNKiaP2_hvEGYNA1oWgUQcY align="left")

**7\. Chmod:** This command is used to change the access permissions of files and directories.

For example: Following “chmod” command will give the user permission to read, write and execute a file.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQGgkewPOw1J0A/article-inline_image-shrink_1500_2232/0/1671203318642?e=1705536000&v=beta&t=pO_rMwN0LBufAfrwDjIHuAdkOVmDw4Wgchdn-5W4c6I align="left")

**8\. Chown:** This command is used to change the file Owner or group.

Here, below the ownership of “Chetan.txt” file got changed to root.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQEDmIFgXtDBKQ/article-inline_image-shrink_1500_2232/0/1671203381032?e=1705536000&v=beta&t=jW_7X_8tCv9L3n2RpbUntUOZEuTAdQ_b_bBRya3HSok align="left")

**9\. Ping –**  (Packet InterNet Groper)This command will ping a host and check if it is responding.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQEZ_lUIhwl8Ug/article-inline_image-shrink_1500_2232/0/1671203452523?e=1705536000&v=beta&t=5DdqOf_kekAO_Xp9G3FVEZ-D8JR3qOC9kqOcVMlcO2c align="left")

**10\. Lsof:** (List Open Files)It is used to display a list of all the open files on a Linux system.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQE65C8RqbghBA/article-inline_image-shrink_1500_2232/0/1671203483627?e=1705536000&v=beta&t=d991T-xXDMed2Zx0Q7SM9K_vFGTeR1ITekikz8PELPU align="left")

11\. **Ifconfig:** (InterFace Configuration)This is used to configure the kernel-resident network interfaces.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQFggVBJPRLZtw/article-inline_image-shrink_1500_2232/0/1671203498025?e=1705536000&v=beta&t=-UxIwA2ZYEGrTMa4OKDI-QqUiIPVxUWERcx6jWjb-NU align="left")

12. **ID:** This is used to find out user and group names and numeric ID’s (UID or group ID) of the current user or any other user in the server.

**Syntax:** id &lt;option&gt; &lt;user\_name&gt;

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQHsEEm2IfzJ0A/article-inline_image-shrink_1500_2232/0/1671203511023?e=1705536000&v=beta&t=hTDloaSyaGbPi4xOML-ku7ZmgrD4ozRoUoAIOzNSlU8 align="left")

13\. **Cut:** This command is used to extract specific fields or columns from a file or standard input.

It is often combined with other commands, such as sort, uniq, and grep, to perform more complex text-processing tasks.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQE6JdWuD96fTg/article-inline_image-shrink_1500_2232/0/1671203536370?e=1705536000&v=beta&t=ZJ6n9oU_T4EValhYvSgA1jtQPGmtGRxl3fUBLrJchf8 align="left")

14\. **Sed:** This is used to perform basic text transformations on an input file. It stands for "Stream Editor" and is a powerful tool for editing text files or streams in a Linux environment.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQGo9fGYfS0BQg/article-inline_image-shrink_1500_2232/0/1671203751390?e=1705536000&v=beta&t=HXNN4KoqHVc_vNXjnUaVG49VPTyRpbAqeqsf81afJD4 align="left")

15\. **Diff:** This command is used to find the difference between two files.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQGeKt-V-HyJ-A/article-inline_image-shrink_1500_2232/0/1671203799716?e=1705536000&v=beta&t=09P1JbdfcZuUf4FJT5kD0xJsv75EvdPPXE4vUxqYUfY align="left")

16\. **History:** This command is used to view the previously executed command.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQEipXYqdH79aQ/article-inline_image-shrink_1500_2232/0/1671203863792?e=1705536000&v=beta&t=ZyDQCUyEQSUbwg1gWONW_8HjzMaPRIWohlDB-xHCj9M align="left")

“History 10” – Will give you the last 10 executed commands.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQEXfc2bMxhF9g/article-inline_image-shrink_1500_2232/0/1671203841111?e=1705536000&v=beta&t=wE-M0UWVn7wKLCHHIAPJabagyONA5uZCsE5UQmoGv_0 align="left")

17\. **Find:** This is used to find files and directories and perform subsequent operations on them.

In the below command, It will search in the present working directory and its subdirectories, and print the name of the file that have “.txt” file extension.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQG0_RIf217sHA/article-inline_image-shrink_1500_2232/0/1671203978450?e=1705536000&v=beta&t=xpp6vNwJLo-BxoNI9SvO3ngQiaAhflX2Vlh9OzfacZ8 align="left")

18\. **Free:** This command displays the total amount of free space available along with the amount of memory used and swap memory in the system, and also the buffers used by the kernel.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQHav8Cm-4iOYw/article-inline_image-shrink_1500_2232/0/1671204031678?e=1705536000&v=beta&t=CjyrxzhuDOSEFqADhO1IkGYfL3I8HNb-9WmYAKTC6tI align="left")

19\. **ssh user@host –** connect to the host as a user.

20\. **Ssh-keygen:** This command is used to generate a public/private authentication key pair.

This process of authentication allows the user to connect remote server without providing a password.

(This authentication method we will use to authenticate the server with Jenkins while deploying CI/CD pipelines).

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQHlV8crlNw2Zw/article-inline_image-shrink_1500_2232/0/1671205801638?e=1705536000&v=beta&t=LgUvvR8IruPkDbF7rGESppJGVjxgR77ptAC3k1kijLc align="left")

21\. **Nslookup:** This stands for “Name server Lookup”. This is a tool for checking DNS hostname to Ip or Ip to Hostname. This is very helpful while troubleshooting.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQHbQ5z5_2SVDQ/article-inline_image-shrink_1500_2232/0/1671205820503?e=1705536000&v=beta&t=ZWicbg9Th144eB_Ob924km9y6bZoduQ95txdy-Bxcuo align="left")

22\. **Curl:** Curl is a tool used for transferring data to or from a server, using various protocols, such as HTTP, HTTPS, FTP, and more. Basic example:

**Syntax:** curl &lt;url&gt;

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQEQYksUtrAH2w/article-inline_image-shrink_1500_2232/0/1671205856271?e=1705536000&v=beta&t=8a2h-wpDGhGBHzHe8DNwqwcBifw0DEurj-7xkrV0mIQ align="left")

**\-o:** It will save downloaded file on the local machine with the name provided in parameters.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQFX0jcVzHWJNg/article-inline_image-shrink_1500_2232/0/1671205883567?e=1705536000&v=beta&t=X-n1XTN3ixV_jiqtix_VlUkeF6p7JTRntk2Xw4Kz80o align="left")

23\. **Tr: Tr** stands for translation. This command is for translating or deleting characters.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQH-P1oRcfhllA/article-inline_image-shrink_1500_2232/0/1671205911156?e=1705536000&v=beta&t=lk7VLv8rfLY56e1GfLKQdMwJHqTYvoafRcRK-h9xB4Q align="left")

24\. **Apt-get:** This command is used to install, update, and remove packages, as well as to manage the package repository sources.

Here are some common apt-get commands:

* apt-get update: This updates the package index files from the package repositories listed in the /etc/apt/sources.list file. This is usually the first command you should run after adding a new repository or package to your system.
    
* apt-get upgrade: This installs newer versions of packages that are already installed on the system. It will also remove any packages that are no longer required.
    
* apt-get install: This installs one or more packages. For example, to install the nano text editor, you would run apt-get install nano.
    
* apt-get remove: This removes one or more packages, but it does not remove the configuration files for the package.
    
* apt-get purge: This removes one or more packages and their configuration files.
    
* apt-get autoremove: This removes packages that were installed as dependencies but are no longer needed.
    

25\. **Df, du:**

Df (disk free) command will have an account of available disk space, used by file system.

Du (disk usage) command reports the size of directory tree including all the content.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQFxznwXiml6Sw/article-inline_image-shrink_1500_2232/0/1671206007845?e=1705536000&v=beta&t=UM1h9urpX0TOhUQdIHnY2GZ1QlkMpKd0Uj05eWekGdw align="left")

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQGSGJyNklXrwg/article-inline_image-shrink_1500_2232/0/1671206017239?e=1705536000&v=beta&t=jVcrYsGUx4VOp6lYgX4YK61L8mPNMrosRN8t_MWWvtM align="left")

26\. **Htop:** This command is used to monitor the system’s resources and processes that are running in real time.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQHjNeyy4If5ow/article-inline_image-shrink_1500_2232/0/1671206041031?e=1705536000&v=beta&t=Avv1-5YjpVwaJpHrk8gSYqYeHFpiB1udAL8ig_EgEg0 align="left")

27\. **Ps:** We use ps command to check the unique id behind every process.

* **a** = show processes for all users
    
* **u** = display the process’s user/owner
    
* **x** = also show processes not attached to a terminal
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQEoqdd491CP0Q/article-inline_image-shrink_1500_2232/0/1671206093832?e=1705536000&v=beta&t=8k7928lVcQsLxiAPfv-GrCVqoHjRJ2QC9oYn3JoZU3U align="left")

28\. **Kill:** This command is used to terminate processes manually. This command basically, will send a signal that terminates it.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4E12AQFK0MfgkDHBbg/article-inline_image-shrink_1500_2232/0/1671206121830?e=1705536000&v=beta&t=pBQ22Vc1yERGu4pPFFgMy__1VP6ScgrBtSxIUxKThlc align="left")

29\. **TNC:** This is “Test Network Connection” command. Mostly used command while troubleshooting. It displays diagnostic information for a connection.

**Command:** tnc &lt;server\_name&gt; -port &lt;port&gt;