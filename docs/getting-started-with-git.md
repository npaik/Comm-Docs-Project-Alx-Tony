# Getting Started with Git

## Overview

Git is a handy tool that helps developers track code changes, collaborate with others, and manage multiple project versions. It simplifies teamwork and makes coding more enjoyable by keeping track of changes and ensuring smooth collaboration. In this section, we'll teach you the basic ideas and commands to help you start using Git with ease.

## Installation

### for Windows

Visit the following [Webpage](https://git-scm.com/download/win), download Git, follow the prompts from the installer and complete the Git installation procedure.

### for macOS

1. Open the terminal.
2. Run the following command.

```js
brew install git
```

!!! Success "Complete"

    Run the following command on terminal to check if the git is correctly installed.
    ```js
    git --version
    ```
    ![](https://www.howtogeek.com/wp-content/uploads/2021/10/Your-Git-version..png?trim=1,1&bg-color=000&pad=1,1)

### Register Github Account

GitHub lets you save and share code online; by signing up, you can collaborate, showcase projects, and access helpful tools to make coding easier.

Visit the following [Webpage](https://github.com/) to create an Github account.

Find the Sign Up button and follow the steps.

## First-Time Git Setup

### Setting Up Identity

Setting up your user name and email address. This is essential as every Git commit relies on this information. You can set your user name and email address by using the command:

Run the follwoing code to set the user name

```js
git config --global user.name "Your Name"
```

Run the follwoing code to set the email

```js
git config --global user.email "youremail@example.com"
```

!!! info

    You only need to do this once using the **--global** option, as Git will always use this information for any action you perform on the system. However, if you want to use a different name or email address for specific projects, you can run the command without the **--global** option when you're working on that project.

### Checking Git Configuration Settings

To view all of your Git configuration settings, you can use the command

```js
git config --list
```

This will display a list of all settings.

You can also check a specific setting looking at keys and values running following command

```js
git config <key>
```

!!! Success "Complete"

    ![](https://n9.dy.fi/wp-content/uploads/2014/01/Git-9.jpg)

### Setting Default Text Editor

After setting up your identity, you can configure the default text editor that Git will use when it needs you to type in a message. If you don't configure this, Git will use your system's default editor.

As an example, if you want to use VSCode as your default text editor, Run the following command:

```js
git config --global core.editor "code"
```
!!! Sucess "Complete"
    Run the following command on terminal to check if the default editor is set to VSCode.
    VSCode will show as "code"

    ```js
    git config core.editor
    ```

### Setting Default Branch Name

When you create a new repository with git init, Git will create a branch called "master" by default. However, from Git version 2.28 onwards, you can set a different name for the initial branch.

To set "main" as the default branch name, you can use the following command:

```js
git config --global init.defaultBranch main
```

!!! Success "Complete"

    This will ensure that any new repository you create with git init will have the branch name "main" instead of "master".

### Getting Help

To get help with Git, you can use run following command to see the list of helps you can get.

```js
git help
```

For instance, you can get help for the git config command by running

```js
git help config
```


!!! Success "Complete"

    Input "q" to exit from the help view

    ![](https://www.prodevelopertutorial.com/wp-content/uploads/2020/08/7_git_help-min.png)

These commands work offline so you can access them from anywhere.

If you need further assistance, you can join the #git, #github, or #gitlab channels on the Libera Chat IRC server at this [Webpage](https://libera.chat/). These channels are filled with experienced Git users who are often willing to help.

## Conclusion

- [x] Git: powerful version control system
- [x] Track changes, collaborate, manage multiple versions

- [x] Basics covered:

    - [x] Installation and Registration
    - [x] Setting up identity
    - [x] Checking Git configuration settings
    - [x] Default text editor
    - [x] Default branch name

- [x] Get Help