---
title: "Day 10 - Git and GitHub Advanced Concepts"
datePublished: Sat Dec 02 2023 14:57:15 GMT+0000 (Coordinated Universal Time)
cuid: clpo6gemt000608i5e8yq0uyr
slug: day-10-git-and-github-advanced-concepts
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701528865295/9e974725-2d89-4a68-8777-d77a6706a739.jpeg
tags: github, git, devops, 90daysofdevops, shubhamlondhe, trainwithshubham, tws

---

# Cherry Pick

**<mark>Cherry Pick</mark>:-** Cherry picking in Git refers to selecting and applying specific commits from one branch to another, allowing targeted integration of changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701200117738/d3ac3155-7f41-415f-acce-937bede5e349.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701200375865/bc3aa9e8-206c-4741-bd49-a2139da43334.png align="center")

`git cherry-pick <CommitID>`

`git cherry-pick --continue`

# Git Stash

**<mark>Git Stash</mark>:-** Allows you to temporarily store uncommitted changes, saving your work-in-progress without committing to the repository.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701200869910/02463543-f5b3-415a-9172-9db3968b1ab1.png align="center")

`git stash`

`git stash pop`

# Pull Request

**<mark>Pull Request</mark>:-** A pull request (PR) is a way to propose changes to a codebase. It is a feature of version control systems like Git, and it is used to facilitate collaboration and code review.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1701201473609/59b085e0-91b2-49e4-8631-7643afa80321.png align="center")

`git pull <remote> <branchname>`

`git pull origin master`