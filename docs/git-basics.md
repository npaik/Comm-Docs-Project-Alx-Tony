# Git Basics

## Overview

In this section, we'll teach you the main commands you'll use with Git most of the time. By the end, you'll learn how to create a project, track files, and save changes. We'll also show you how to tell Git to ignore certain files, quickly fix mistakes, look at your project's history, and see what's different between saved changes. Plus, we'll teach you how to share your work with others online.

## Getting a Git Repository

There are two ways to get a Git repository:

- Setting Up a Repository in an Existing Folder
- Cloning a Pre-existing Repository

!!! info

    In both cases, you'll have a Git repository on your local machine, ready for work.

### Setting Up a Repository in an Existing Folder

If you want to use Git to manage a project folder that isn't under version control, first navigate to the project's folder. The process varies depending on your operating system:

- Navigate to the project folder.

  Windows:

```js
cd C:/Users/user/my_project
```

  macOS:

```js
cd / Users / user / my_project;
```

Run the following command:
  ```js
  git init
  ```
This command creates a new hidden .git subdirectory containing all the required repository files - a Git repository framework. At this stage, none of your project files are being tracked. Refer to Git Internals for more details on the .git directory's contents.

To begin version control for existing files, start tracking the files and make an initial commit. Use several git add commands to specify the files to track, followed by a git commit:

```js
git add .
```

```js
git add LICENSE
```

```js
git add README.md
```

At this point, your Git repository contains tracked files.

### Recording Changes to the Repository

Git enables modifying and committing tracked and untracked files. Changes since the last commit are identified and can be staged and committed again.

#### Assessing the Status of Your Files

The git status command is the primary tool you'll use to determine the state of your files.

```js
git status
```

!!! Success "Complete"

    ![](https://static.javatpoint.com/tutorial/git/images/git-status2.png)


#### Commiting changes

After staging your changes with git add, you can commit them with git commit.
The commit message can be entered in your editor or provided inline with the -m flag. The commit command creates a snapshot of your project that can be reverted to or compared to later. Any changes that weren't staged will remain as modified files.

```js
git commit -m "<message>"
```





#### Pushing to your Remotes

```js
git branch -M main
```
The command git branch -M main renames the current branch to "main," forcing the change even if the new branch name already exists.

Next command adds a new remote named "origin" to your local Git repository, pointing to the specified URL.
```js
git remote add origin "http://github.com/testrepository.git
```

The command git push -u origin main uploads your main branch to the remote repository called "origin" and sets it up for easy syncing in the future.
```js
git push -u origin main
```

### Tracking New Files

To track a new file, use the git add command. For example, to track the TEST file, run:

```js
git add TEST
```

After running git status, you can see that TEST is now tracked and staged for commit:

```js
git status
```

The file is staged when listed under "Changes to be committed." The version of the file at the time of running git add will be in the subsequent snapshot if you commit at this point

### Fetching and Pulling from Your Remotes

When you want to get data from a remote project, use the command

```js
git fetch <remote>
```

This will pull down all the data from the remote that you don't have yet. The git fetch command only downloads the data to your local repository and doesn't modify any of your current work.

If your current branch is set up to track a remote branch, you can use the command

```js
git pull
```

to automatically fetch and merge the remote branch into your current branch. By default, git clone sets up your local master branch to track the remote master branch. However, from git version 2.27 onwards, git pull will give a warning if the pull.rebase variable is not set. You can set this variable to true if you want to rebase when pulling.

!!! info

    However, this command only works if you cloned from a server to which you have write access and if no one else has pushed anything upstream. If someone else has pushed upstream, you need to **fetch** their work and incorporate it into yours before you can push your changes.


### Cloning a Pre-existing Repository

If you want to make a copy of a Git project that already exists, use the **git clone** command. Unlike some other systems like Subversion, Git uses **clone** instead of **checkout**. This is important because Git gets a full copy of the project, including its whole history and every version of each file, not just the current files. So, when you use **git clone**, you'll have everything you need from the original project.

To clone a repository, use git clone <url>. For example, to clone the Git linkable markdown:

```js
git clone https://github.com/npaik/Comm-Docs-Project-Alx-Tony
```

This command makes a new folder, sets up a ".git" folder inside it, gets all the project data, and gives you the newest version of the files. When you go into the new folder, you'll see the project files, all set for you to use or change as you like.

To clone the repository into a differently-named directory, specify a new name as an additional argument:

```js
git clone https://github.com/npaik/Comm-Docs-Project-Alx-Tony gitproject
```

This command behaves like the previous one, but the target directory is named gitproject.

!!! Success "Complete"

    ![](https://cdn.ttgtmedia.com/rms/onlineImages/ServerSide_git-clone-02.jpg)

Git supports various transfer protocols, such as https://, git://, or user@server:path/to/repo.git (using the SSH transfer protocol). The "Getting Git on a Server" section will introduce all available options for server access to your Git repository and their respective advantages and disadvantages.

## Conclusion

- [x] Essential Git commands covered:

  - [x] Setup and initialize repository
  - [x] Recording changes
    - [x] Accessing the status of the files
    - [x] Commiting changes
    - [x] Pushing to repository
  - [x] Tracking New files
  - [x] Fetching and Pulling from your remotes
  - [x] Cloning a pre-exsisting repository