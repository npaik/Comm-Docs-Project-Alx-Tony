# Git Branching

## Overview

This section will guide you on how to use the git branch command and will explain overall Git branching model. You will also see how to create, delete and merge branches.

Branching means you diverge from the main line of development and continue to do work without messing with that main line. The flowchart below shows the basic workflow while using the branches with GIT.
``` mermaid
graph LR
    A[Main] --> B[Main] 
    B --> C[Main]
    C --> |Main branch remains functional| D[Main]
    C --> E[new Feature]
    E --> F[new Feature]
    F --> G[new Feature]
    G --> |Test the feature and merge with main| D
```
 This is useful when you want to work on a new feature or fix a bug without affecting the stability of the main branch.
 
!!! info "Branching in GIT"
    Git encourages workflows that branch and merge often, even multiple times in a day. Understanding and mastering this feature gives you a powerful and unique tool and can entirely change the way that you develop.

## Creating Branches Locally

Let’s say you previously initialized the git repository on your computer and you want to create a new branch called ```test```.
To create this branch locally you need to follow the next steps:

1. Open the command line interface(CLI) on your machine (Command Prompt on Windows, Terminal on MacOS, Bash or Zsh on Linux).

2. Navigate to the directory of the Git repository where you want to create the branch.
  ```
  cd path/to/repo
  ```

3. Create a new branch using the git branch command followed by the name of the new branch.
 ```
 git branch new-branch
 ```
This will create a new branch called new-branch at the current HEAD (the most recent commit).

4. Switch to the new branch using the git checkout command followed by the name of the new branch.
 ```
 git checkout new-branch
 ```
 This will switch the working directory to the new branch so that any changes you make will be committed to that branch instead of the main branch.

5. Make changes to the files in the working directory and commit the changes using the git add and git commit commands as described in previous section.
!!! info "Check or Switch Branch"
    To check which branch you are currently on in Git, you can use the git branch command with the -a (all) and -v (verbose) flags:
    ```
    git branch -av
    ```
    This will list all local and remote branches along with the current branch, which is marked with an asterisk *. The current branch will also be highlighted in green.

    Once you've created a branch, you can switch to it using the git checkout command followed by the name of the branch. For example, to switch to the "feature-branch", you can use the following command:
    ```
    git checkout feature-branch
    ```

## Creating Branches Remotely on GitHub

 At this point you shoud already have a GitHub account with a new remote repository created.
!!! info "Remote Repository"
    A remote repository is not necessarily a copy of a local repository, it is rather a separate repository that can be accessed by multiple users and machines. But typically local repository linked to a remote repository.

 You can create a new remote branch in GitHub using the command line. To do so, follow the next steps:

1. Clone the repository to your local machine using the git clone command.
 ```
 git clone https://github.com/your-username/your-repository.git
 ```
2. Navigate to the cloned repository using the cd command.
 ```
 cd your-repository
 ```
3. Create a new branch and switch to that branch by using the git command followed by the name of the new branch.
 ```
 git checkout -b new-branch-name
 ```
4. Make changes to the files in the working directory and commit the changes using the git add and git commit commands as describes in the previous section Git Basics.
5. Push the new branch to GitHub using the git push command with the --set-upstream flag to link the local and remote branches.
 ```
 git push --set-upstream origin new-branch
 ```
This will push the new branch to GitHub and create a new remote branch with the same name.

## Merging Branches
To merge changes from one branch to another, you can use the git merge command. For example, to merge changes from "feature-branch" into "main" branch, you can use the following command:
 ```
 git checkout main
 git merge feature-branch
 ```
!!! warning
    Merging branches can cause conflicts if changes were made to the same lines of code on both branches. Make sure to review and resolve any conflicts that arise during a merge.

## Deleting Branches
To delete a branch after you're done with it, you can use the git branch -d command followed by the name of the branch. For example, to delete the "feature-branch", you can use the following command:
 ```
 git branch -d feature-branch
 ```
!!! warning
    Only delete branches that are no longer needed, as deleting a branch will delete all of the commits and changes made on that branch.

## Conclusion

By the end of this section, you will have successfully learned the following:

- [x] How the GIT branching model works
- [x] How to create a new branch in local and remote repository
- [x] How to switch and check the current branch
- [x] How to merge and delete the branch in GIT

Great job 🤗. You can go ahead and find the solutions to the most common issues that you might encounter while working with GIT: