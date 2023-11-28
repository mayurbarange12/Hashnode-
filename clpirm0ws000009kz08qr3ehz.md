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
    

**GitHub:** A web-based platform providing remote hosting and collaborative features for Git repositories.

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
        

## **Branching Strategies:-**

Branching in Git allows for divergent lines of development, enabling users to create separate paths to work on features or fixes without altering the main codebase. It facilitates parallel development and isolation of changes until they're ready to be merged back into the main branch.

`git branch`**\--&gt;**  To list, create, or manipulate branches within a Git repository.

`git checkout -b "BranchName"`**\--&gt;** Creates and switches to a new branch named 'BranchName' in Git.

`git checkout <BranchName>`   **OR**   `git switch <BranchName>` --&gt; Switches to a different branch in Git.

`git log --oneline` --&gt; This command displays a concise history of commits in a single line format, showing abbreviated commit IDs and commit messages.

**<mark>Hotfix</mark>**:- Hotfix in Git refers to an expedited corrective patch applied directly to a production branch to swiftly resolve critical issues or bugs.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701184056417/893a5d64-50c5-43f7-b1ad-4253bf780bac.png align="center")

**Jira:-** Jira is a powerful project management tool designed to streamline team collaboration, track tasks, and manage workflows efficiently.

**<mark>Git Merge</mark>**:- Integrates changes from different branches into one, combining their commit histories.

`git merge <BranchName>`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701183725210/9fdddfe3-a40b-441e-8273-1179644af48b.png align="center")

**<mark>Git Push</mark>:**\- "Git push" is a command that sends committed changes from your local Git repository to the remote repository, enabling synchronization and updating of the shared codebase.

**How to push a <mark>repo</mark> from the Local Repository to the GitHub Remote Repository?**

* locate the specific location of the folder in the local system.
    
* `git init`
    
* `git remote add origin <git https url>`
    
* `git remote -v`  --&gt; Displays the URLs of the remote repositories associated with the local Git project, showing both fetch and push URLs.
    

origin [https://ghp\_aD5vtGbs1xUm20i5w1NUghR5IDVv9W1OfB0B@github.com/mayurbarange12/devops-batch-5.git](https://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@github.com/mayurbarange12/devops-batch-5.git) (<mark>fetch</mark>)

origin [https://ghp\_aD5vtGbs1xUm20i5w1NUghR5IDVv9W1OfB0B@github.com/mayurbarange12/devops-batch-5.git](https://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@github.com/mayurbarange12/devops-batch-5.git) (<mark>push</mark>)

* `git add --all`
    
* `git commit -m "your message"`
    
* `git push origin master`
    

Username:

Password:

(Above Authentication is required to push repo from local repo to remote repo)

**How to Authenticate your Local System Repo with GitHub account Repo?**

* **Type-1:-** Click on profile picture -&gt; Settings -&gt; **SSH and GPG keys.**
    
* **Type-2:-** Click on Profile Picture -&gt; Settings -&gt; Developer settings -&gt; **Personal Access Tokens** -&gt; Tokens (classic) -&gt; Generate new Token -&gt; Generate new token (classic) -&gt; Note-ubuntu-access-token(select repo) -&gt; Generate Token.
    

```bash
git remote set-url origin https://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@github.com/mayurbarange12/devops-batch-5.git
```

`git push origin master` --&gt; Repo pushed without asking Authentication.

**Difference between "<mark>Git pull</mark>" & "<mark>Git fetch</mark>"**

* **Git Pull:** Fetches remote changes and automatically merges them into the local branch.
    
* **Git Fetch:** "Git fetch" downloads changes from a remote repository to your local branch, allowing you to review them before merging.
    

**<mark>Git Pull</mark>**: 🚀 Fetches and merges changes from a remote repository into the local branch, ensuring the latest updates are applied to the local repository.

`git pull origin master`

**How to pull (<mark>staging</mark>) Branch from Remote Repository to Local Repository In GIT?**

Create a new Branch named as "staging" branch inside repository "devops-batch-5" in GitHub:-

* mayurbarange12/devops-batch-5 -&gt; Master -&gt; View all branches -&gt; New Branch -&gt; Name - staging -&gt; create new branch
    
* Select staging branch -&gt; Add file -&gt; Create new file -&gt; FileName = staging-feature.txt -&gt; Content = This is a staging feature -&gt; Commit Changes.
    
* `git pull origin master`  
    
* `git fetch`  
    
* `git branch`
    
* `git checkout staging` 
    
* `git branch`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701197779172/e55d573d-6fe6-47d9-a317-514889793196.png align="center")

**<mark>Git Rebase</mark>:-** Rearranges commit history by incorporating changes from one branch onto another, creating a linear sequence of commits.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701198034091/b622a36d-77ff-4e16-9735-fddfaa44f61b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701199504231/649cd1df-c170-4e74-bcc5-8538507b97a7.png align="center")

`git rebase <BranchName>`

**<mark>Git Revert</mark>:-** Creates a new commit that undoes the changes made by a specific commit, effectively reverting those changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701199032881/bec4bb0d-b44b-4b62-bd4d-0d7f190dd2ed.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701199199528/69f9126b-3acd-4bdc-98c3-8ace4e4a2576.png align="center")

`git revert <CommitID>`

**<mark>Git Reset</mark>:-** Unstages files or moves the HEAD to a specific commit, altering the repository's state.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701199628207/3a32e5ba-9299-4651-aa3d-6891b52b1d03.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701199330917/80477504-606b-4c49-972b-ce96dd19a5ad.png align="center")

**Git reset has two types:-**

* `git reset --soft <CommitID>` --&gt;Moves HEAD to a new commit without modifying the working directory or staging area.
    
* `git reset --hard <CommitID>` --&gt;Moves HEAD to a new commit, resets the staging area to match that commit, and discards changes in the working directory.
    

**<mark>Cherry Pick</mark>:-** Cherry picking in Git refers to selecting and applying specific commits from one branch to another, allowing targeted integration of changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701200117738/d3ac3155-7f41-415f-acce-937bede5e349.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701200375865/bc3aa9e8-206c-4741-bd49-a2139da43334.png align="center")

`git cherry-pick <CommitID>`

`git cherry-pick --continue`

**<mark>Git Stash</mark>:-** Allows you to temporarily store uncommitted changes, saving your work-in-progress without committing to the repository.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701200869910/02463543-f5b3-415a-9172-9db3968b1ab1.png align="center")

`git stash`

`git stash pop`

**<mark>Pull Request</mark>:-** A pull request (PR) is a way to propose changes to a codebase. It is a feature of version control systems like Git, and it is used to facilitate collaboration and code review.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701201473609/59b085e0-91b2-49e4-8631-7643afa80321.png align="center")

`git pull <remote> <branchname>`

`git pull origin master`