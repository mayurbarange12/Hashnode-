---
title: "Day 9 - Advance Git & GitHub for DevOps Engineers"
datePublished: Sat Dec 02 2023 14:18:38 GMT+0000 (Coordinated Universal Time)
cuid: clpo52qkx000108l52lfs5ca5
slug: day-9-advance-git-github-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701526406100/1354a1d3-4b12-4b48-b9b3-3c286adfffaa.png
tags: github, git, devops, 90daysofdevops, shubhamlondhe, trainwithshubham, tws

---

## **Branching Strategies**

Branching in Git allows for divergent lines of development, enabling users to create separate paths to work on features or fixes without altering the main codebase. It facilitates parallel development and isolation of changes until they're ready to be merged back into the main branch.

* `git branch`**\--&gt;**  To list, create, or manipulate branches within a Git repository.
    
* `git checkout -b "BranchName"`**\--&gt;** Creates and switches to a new branch named 'BranchName' in Git.
    
* `git checkout <BranchName>`   **OR**   `git switch <BranchName>` --&gt; Switches to a different branch in Git.
    
* `git log --oneline` --&gt; This command displays a concise history of commits in a single line format, showing abbreviated commit IDs and commit messages.
    

## **<mark>Hotfix</mark>**

Hotfix in Git refers to an expedited corrective patch applied directly to a production branch to swiftly resolve critical issues or bugs.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701184056417/893a5d64-50c5-43f7-b1ad-4253bf780bac.png align="center")

**Jira:-** Jira is a powerful project management tool designed to streamline team collaboration, track tasks, and manage workflows efficiently.

## **<mark>Git Merge</mark>**

Integrates changes from different branches into one, combining their commit histories.

* `git merge <BranchName>`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701183725210/9fdddfe3-a40b-441e-8273-1179644af48b.png align="center")

## **<mark>Git Push</mark>**

"Git push" is a command that sends committed changes from your local Git repository to the remote repository, enabling synchronization and updating of the shared codebase.

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
    

## **<mark>Git Pull</mark>**

🚀 Fetches and merges changes from a remote repository into the local branch, ensuring the latest updates are applied to the local repository.

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

## **<mark>Git Rebase</mark>**

Rearranges commit history by incorporating changes from one branch onto another, creating a linear sequence of commits.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701198034091/b622a36d-77ff-4e16-9735-fddfaa44f61b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701199504231/649cd1df-c170-4e74-bcc5-8538507b97a7.png align="center")

* `git rebase <BranchName>`
    

## **<mark>Git Revert</mark>**

Creates a new commit that undoes the changes made by a specific commit, effectively reverting those changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701199032881/bec4bb0d-b44b-4b62-bd4d-0d7f190dd2ed.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701199199528/69f9126b-3acd-4bdc-98c3-8ace4e4a2576.png align="center")

* `git revert <CommitID>`
    

## **<mark>Git Reset</mark>**

Unstages files or moves the HEAD to a specific commit, altering the repository's state.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701199628207/3a32e5ba-9299-4651-aa3d-6891b52b1d03.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701199330917/80477504-606b-4c49-972b-ce96dd19a5ad.png align="center")

**Git reset has two types:-**

* `git reset --soft <CommitID>` --&gt;Moves HEAD to a new commit without modifying the working directory or staging area.
    
* `git reset --hard <CommitID>` --&gt;Moves HEAD to a new commit, resets the staging area to match that commit, and discards changes in the working directory.