# Using Git with a Local OneDrive Hosted Repository

A OneDrive folder can be used as a repository for storing a project to be managed by Git. If you are using your personal OneDrive folder, access to your projects will be limited to you. If you use another OneDrive folder, that is accessible to others, then that repository will be accessible by anyone who can access the OneDrive folder and who has it synchronized to their local machine.

_NOTE: If you are seeing unformatted text, it is because your viewer doesn't understand Markdown. To see this document formatted with headings and whatnot, install a Markdown Viewer extension in your web browser or view it using a viewer that understands Markdown coding. You will also want to make sure that you enable file-based URLs._ 

### Table of Contents
_These links won't work when accessed as a file-based URL_

- [Setup Your Development Environment](#Setup-Your-Development-Environment)
- [Install Git for Windows](#Install-Git-for-Windows)
- [Create a Working Code Folder](#Create-a-Working-Code-Folder)
- [Create a Git Base Repository](#Create-a-Git-Base-Repository)
- [Create a Top-Level Git Projects Folder](#Create-a-Top-Level-Git-Projects-Folder)
- [Working with the Development Environment](#Working-with-the-Development-Environment)
- [Create a Project Repository](#Create-a-Project-Repository)
- [Using a Project Repository](#Using-a-Project-Repository)
- [Adding Files to a Project Repository](#Adding-Files-to-a-Project-Repository)
- [Updating Files](#Updating-Files)
- [Reverting a file to the most recent version in the repository](#Reverting-a-file-to-the-most-recent-version-in-the-repository)

## Setup Your Development Environment

### Install Git for Windows
You only need to do these steps once on a computer where you will use git commands.

1. Go to https://git-scm.com/download/win
2. Download the 64-bit installer
3. Install it

### Create a Working Code Folder
This is the parent folder that you will check projects into and out of your Git repository, and where you will do your work on those projects. It will contain subfolders for each project (repository) you work with.

1. Open a Windows command prompt
2. Enter the following commands

```shell
mkdir %HOMEPATH%\source
```

## Create a Git Base Repository

### Create a Top-Level Git Projects Folder
You only need to do this one time. You will create Git repositories (your projects) in this parent folder.

```shell
mkdir %ONEDRIVE%\git-projects
```

## Working with the Development Environment

### Create a Project Repository
You will do this for each project you work on that you want to use Git commands. 

1. Open a Windows command prompt
2. Enter the following commands

```shell
cd %ONEDRIVE%\git-projects
mkdir projectname
cd projectname
git init --bare
```

### Using a Project Repository
The clone command shown will create a new folder in the current directory using th ename of the repository. If you want a different name, specify it as a separate argument after the repository URL.

1. Open a Windows command prompt
2. Enter the following commands

```shell
cd %HOMEPATH%\source
git clone "file:///%ONEDRIVE%/git-projects/projectname"
```

### Adding Files to a Project Repository
**Warning:** In the example given, the echo command will OVERWRITE without prompting, an existing readme.md file in the current folder.

The Git commands shown, ```git add```, ```git commit```, and ```git push``` of are used for any files you need to add. The push command is what causes any files specified in the git add command, and then committed, to be written to the repository.

1. Open a Windows command prompt
2. Enter the following commands

```shell
cd %HOMEPATH%\source\projectname
echo # Readme > readme.md
git add readme.md
git commit -m "Adding readme.md file to repository"
git push
```

### Updating Files
At some point after you have worked on files, you will want to update the version in the repository. Changes must be committed and then pushed to the repository to do that. The ```git add``` command is used to add files to the commit. The ```git push``` is what adds them to the repository.

1. Open a Windows command prompt
2. Enter the following commands

```shell
cd %HOMEPATH%\source\projectname
git status
git add readme.md
git commit -m "message about the changes"
git push
```

### Reverting a file to the most recent version in the repository
If you have a file that you want to revert to the version in the repository, you can do that with the checkout command. Doing this will cause any uncommitted changes to be lost. 

1. Open a Windows command prompt
2. Enter the following commands

```shell
cd %HOMEPATH%\source\projectname
git checkout readme.md
```
