# Getting Started with Git

## Overview

Git is a version control system that allows developers to track changes in their code, collaborate with others, and manage multiple versions of a project. It is an essential tool for developers that ensure efficient collaboration. It also have a feature to maintain a history of changes of your code. This section will introduce you to the fundamental concepts and commands needed to begin using Git effectively.

## Installation

### for Windows

Visit the following Webpage and download Git:

[https://git-scm.com/download/win](https://git-scm.com/download/win)

### for macOS

Run the following command on terminal.

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

Visit the following webpage to create an Github account

[https://github.com/](https://github.com/)

## First-Time Git Setup

### Customizing Git Environtment

Once you have installed Git and have the account created, you can customize your Git environment using the git config tool. Git configuration variables control how Git looks and operates. These variables can be stored in three different places:

- The system-wide configuration file (**/etc/gitconfig**): stores values that apply to every user on the system and all their repositories.
  To access this file, use the **--system** option with git config.
  !!! note "note: Administrative or superuser privileges are required to modify this file."

- The user-specific configuration file (**~/.gitconfig** or **~/.config/git/config**) contains settings that are specific to you.
  You can make Git read and write to this file by using the **--global** option, which affects all the repositories you work with on your system.

- The repository-specific configuration file (**.git/config**) stores settings that are specific to the current repository.
  You can make Git read from and write to this file by using the **--local** option.

!!! Success
    You can view all of your settings and where they are coming using following command
    ```js
    git config --list --show-origin
    ```

### Setting Up Identity

Setting up your user name and email address. This is essential as every Git commit relies on this information. You can set your user name and email address by using the command:

```js
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

!!! note

    You only need to do this once using the **--global** option, as Git will always use this information for any action you perform on the system. However, if you want to use a different name or email address for specific projects, you can run the command without the **--global** option when you're working on that project.

### Setting Default Text Editor

After setting up your identity, you can configure the default text editor that Git will use when it needs you to type in a message. If you don't configure this, Git will use your system's default editor.

To specify a different text editor, you can use the following command:

```js
git config --global core.editor <editor_name>
```

For instance, if you want to use VSCode as your default text editor, you can use this command:

```js
git config --global core.editor "code --wait"
```

!!! note
    This sets the code command as the editor, with the --wait option allowing Git to wait for you to close the editor before continuing.

### Setting Default Branch Name

When you create a new repository with git init, Git will create a branch called "master" by default. However, from Git version 2.28 onwards, you can set a different name for the initial branch.

To set "main" as the default branch name, you can use the following command:

```js
git config --global init.defaultBranch main
```

This will ensure that any new repository you create with git init will have the branch name "main" instead of "master".

### Checking Git Configuration Settings

To view all of your Git configuration settings, you can use the command

```js
git config --list
```

This will display a list of all settings.

You can also check a specific key’s value by

```js
git config <key>
```

### Getting Help

To get help with Git, you can use any of the following commands.

```js
git help <verb>
git <verb> --help
man git-<verb>
```

For instance, you can get help for the git config command by running

```js
git help config
```

These commands work offline so you can access them from anywhere.

If you need further assistance, you can join the #git, #github, or #gitlab channels on the Libera Chat IRC server at [https://libera.chat/](https://libera.chat/) These channels are filled with experienced Git users who are often willing to help.

## Conclusion

Git is a powerful version control system that provides developers with the ability to track changes, collaborate with others, and manage multiple versions of a project efficiently. In this section, we have covered the fundamental concepts and commands required to get started with Git, including installation, customization of Git environment, setting up identity, default text editor, default branch name, and checking Git configuration settings. Additionally, we have provided ways to access comprehensive help for any Git command, either online or offline. With this knowledge, developers can use Git effectively and streamline their workflow.