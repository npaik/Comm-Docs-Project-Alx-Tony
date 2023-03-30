# Git Basics

## Overview

In this section, we'll cover all the essential commands you need for the majority of tasks you'll perform with Git. By the end of this chapter, you should be able to set up and initialize a repository, start and cease tracking files, as well as stage and commit modifications. We will also guide you on configuring Git to exclude specific files and file patterns, demonstrate how to swiftly and effortlessly correct errors, explore your project's history and compare changes between commits, and instruct you on pushing and pulling from remote repositories.

### Getting a Git Repository

There are two methods to acquire a Git repository:

- Setting Up a Repository in an Existing Folder
- Cloning a Pre-existing Repository

!!!note
    In both cases, you'll have a Git repository on your local machine, ready for work.

#### Setting Up a Repository in an Existing Folder

If you want to use Git to manage a project folder that isn't under version control, first navigate to the project's folder. The process varies depending on your operating system:

Windows:

```js
cd C:/Users/user/my_project
```

macOS:

```js
cd / Users / user / my_project;
```

Then, run this command:

```js
git init
```

This command creates a new hidden .git subdirectory containing all the required repository files - a Git repository framework. At this stage, none of your project files are being tracked. Refer to Git Internals for more details on the .git directory's contents.

To begin version control for existing files, start tracking the files and make an initial commit. Use several git add commands to specify the files to track, followed by a git commit:

```js
git add *.c
git add LICENSE
git commit -m 'Initial project version'
```

At this point, your Git repository contains tracked files and an initial commit.

#### Cloning a Pre-existing Repository

If you want to copy an existing Git repository use the git clone command.
If you've used other VCSs like Subversion, you'll notice the command is "clone" rather than "checkout". This distinction is crucial because Git retrieves a complete copy of almost all server data, not just a working copy. By default, git clone pulls down the entire project history, including every file version.

To clone a repository, use git clone <url>. For example, to clone the Git linkable library libgit2:

```js
git clone https://github.com/libgit2/libgit2
```

This command creates a libgit2 folder, initializes a .git directory within, downloads all repository data, and checks out the latest working copy. Entering the newly created libgit2 directory, you'll find the project files, ready for use or modification.

To clone the repository into a differently-named directory, specify a new name as an additional argument:

```js
git clone https://github.com/libgit2/libgit2 mylibgit
```

This command behaves like the previous one, but the target directory is named mylibgit.

Git supports various transfer protocols, such as https://, git://, or user@server:path/to/repo.git (using the SSH transfer protocol). The "Getting Git on a Server" section will introduce all available options for server access to your Git repository and their respective advantages and disadvantages.

### Recording Changes to the Repository

Git enables modifying and committing tracked and untracked files. Changes since the last commit are identified and can be staged and committed again.

#### Assessing the Status of Your Files

The git status command is the primary tool you'll use to determine the state of your files.

```js
git status
```

#### Tracking New Files

To track a new file, use the git add command. For example, to track the README file, run:

```js
git add README
```

After running git status, you can see that README is now tracked and staged for commit:

```js
git status
```

```js
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
(use "git restore --staged <file>..." to unstage)
new file: README
```

The file is staged when listed under "Changes to be committed." The version of the file at the time of running git add will be in the subsequent snapshot if you commit at this point

#### Commiting changes

After staging your changes with git add, you can commit them with git commit.
The commit message can be entered in your editor or provided inline with the -m flag. The commit command creates a snapshot of your project that can be reverted to or compared to later. Any changes that weren't staged will remain as modified files.

```js
git commit -m "<message>"
```

#### Pushing to your Remotes

To share your project with others, you need to push it upstream using the command

```js
git push <remote> <branch>
```

For example, if you want to push the master branch to your origin server, you can run

```js
git push origin master
```

!note
However, this command only works if you cloned from a server to which you have write access and if no one else has pushed anything upstream. If someone else has pushed upstream, you need to **fetch** their work and incorporate it into yours before you can push your changes.

#### Fetching and Pulling from Your Remotes

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

## Conclusion

This section has covered the essential commands that you need to get started with Git, including setting up and initializing a repository, tracking files, staging and committing modifications, excluding specific files and patterns, correcting errors, exploring project history, and pushing and pulling from remote repositories. Whether you're working on a personal or collaborative project, Git provides a robust framework for managing your code changes and ensuring that your project remains organized and efficient. With these fundamental Git commands under your belt, you're well on your way to mastering version control and maximizing your productivity.
