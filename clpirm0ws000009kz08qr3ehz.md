---
title: "Day 8 - Git and GitHub Advanced"
datePublished: Tue Nov 28 2023 20:02:52 GMT+0000 (Coordinated Universal Time)
cuid: clpirm0ws000009kz08qr3ehz
slug: day-8-git-and-github-advanced
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701179766970/1f8c7bd0-675a-4e39-9644-35aa595574f2.png
tags: github, git, devops, 90daysofdevops, shubhamlondhe, trainwithshubham, tws

---

### **What is Git and why is it important?**

🚀 **Git:** Git is a distributed version control system (VCS) designed for tracking changes in source code during software development. It allows multiple developers to collaborate on projects and efficiently manage revisions, providing a snapshot of the project at any given time.

**Why Git is Important:**

* 🔄 **Version Tracking:** Keeps a comprehensive history of changes made to code, allowing easy retrieval of earlier versions.
    
* 👥 **Collaboration:** Enables seamless teamwork, allowing multiple developers to work on the same codebase simultaneously.
    
* 📝 **Branching & Merging:** Facilitates creating branches for features or fixes and merging them back into the main codebase.
    
* 🛡️ **Backup & Recovery:** Provides a robust backup system, minimizing the risk of data loss.
    
* 🚀 **Efficiency & Speed:** Streamlines development processes, improving productivity by providing a fast and efficient workflow.
    
* 🌐 **Remote Access:** Allows access to repositories hosted remotely, promoting accessibility and distributed work.
    
* 🔄 **Open Source:** Git is open-source, fostering a strong community contributing to its development and widespread adoption.
    
* 🛠️ **Versatility:** Used not only in software development but also for managing various types of files or content revisions.
    

### **What is difference Between Main Branch and Master Branch??**

🌟 **Main Branch vs. Master Branch:**

The difference between the "Main" branch and the "Master" branch primarily lies in their naming conventions and historical usage within version control systems like Git.

🌿 **Main Branch:**

* **Definition:** The "Main" branch represents the primary development branch in recent Git repository management practices.
    
* **Usage:** In response to evolving social considerations and inclusive language, some organizations and newer repositories have opted to use "Main" instead of "Master" as the default primary branch name.
    
* **Symbolism:** The term "Main" reflects inclusivity and neutrality, moving away from potentially loaded or historical connotations associated with the term "Master."
    

🔱 **Master Branch:**

* **Definition:** Historically, the "Master" branch has been the default name for the primary branch in Git repositories.
    
* **Usage:** Older repositories and established practices often use "Master" to denote the primary branch, encompassing the main body of work.
    
* **Symbolism:** While originally denoting the primary branch, "Master" was seen as the authoritative branch where other changes were merged or derived.
    

### **Can you explain the difference between Git and GitHub?**

**Git 🔄:**

* **Definition:** Git is a distributed version control system (VCS) that manages and tracks changes in source code during software development.
    
* **Functionality:** It tracks changes, creates branches, merges versions, and maintains a history of project modifications.
    
* **Local Tool:** Git operates as a command-line tool installed on a user's local machine.
    
* **Core Features:** Allows version control, branching, merging, and maintaining a local repository.
    

**GitHub 🐙:**

* **Definition:** GitHub is a web-based platform that provides hosting for Git repositories.
    
* **Functionality:** It hosts Git repositories in a collaborative environment, enabling multiple users to collaborate on projects.
    
* **Remote Repository Hosting:** Acts as a remote server for Git repositories, facilitating sharing and collaboration.
    
* **Additional Features:** Offers features like issue tracking, pull requests, wikis, and project management tools.
    

**Difference:**

* **Git:** Software for version control managed locally.
    
* **GitHub:** A web-based platform providing remote hosting and collaborative features for Git repositories.
    

### **How do you create a new repository on GitHub?**

* **In the upper-right corner of the GitHub page, Select +, then click New Repository**
    

![Screenshot of a GitHub dropdown menu showing options to create new items. The menu item "New repository" is outlined in dark orange.](https://docs.github.com/assets/cb-34248/images/help/repository/repo-create-global-nav-update.png align="left")

* **Type a short, memorable name for your repository. For example, "hello-world".**
    

![Screenshot of the first step in creating a GitHub repository. The "Repository name" field contains the text "hello-world" and is outlined in dark orange.](https://docs.github.com/assets/cb-61138/images/help/repository/create-repository-name.png align="left")

* **Optionally, add a description of your repository. For example, "My first repository on GitHub."**
    
* **Choose a repository visibility**
    
* Select **Initialize this repository with a README.**
    
* Click **Create repository**.
    

### **What is the difference between local & remote repository? How to connect local to remote?**

🏠 **Local Repository:**

* **Definition:** A local repository exists on your local machine and stores the project's complete version history.
    
* **Location:** It resides on your computer's hard drive or a network location accessible locally.
    
* **Access & Control:** Operated and managed by the user, enabling version control and tracking changes.
    
* **Git Operations:** Allows commits, branches, merges, and other Git operations locally.
    

🌐 **Remote Repository:**

* **Definition:** A remote repository is hosted on a server or a remote location, often on platforms like GitHub, GitLab, or Bitbucket.
    
* **Location:** Hosted on a remote server, accessible over the internet or a network.
    
* **Collaboration:** Facilitates collaboration and sharing among multiple users or teams.
    
* **Shared Storage:** Serves as a central storage for the project, enabling multiple contributors to access and contribute to the same codebase.
    

**Connecting Local to Remote Repository:** To connect a local repository to a remote repository:

1. **Create a Remote Repository:**
    
    * On GitHub, create a new repository
        
2. **Set Remote in Local Git:**
    
    * In your local repository's command line interface (CLI):
        
        ```bash
        git remote add origin <remote_repository_URL>
        ```
        
        Replace `<remote_repository_URL>` with the URL of your remote repository.
        
3. **Push Local Commits to Remote:**
    
    * Push your local repository's commits to the remote:
        
        ```bash
        git push -u origin master
        ```
        
        This command pushes your local "master" branch to the "origin" remote repository. The `-u` flag sets the upstream, linking the local and remote branches for future pushes and pulls.