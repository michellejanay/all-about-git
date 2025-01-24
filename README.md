# All about Git <a name="all-about-git"></a>
![Git Cat](images/github-mark.png)

## Table of Contents
- [All About Git](#all-about-git)
    - [Useful Terminal Commands](#useful-terminal-commands)
    - [What is version control?](#what-is-version-control)
    - [What is Git?](#what-is-git)
    - [Installing Git](#installing-git)
    - [Account Setup](#account-setup)
    - [Creating a Repository](#creating-a-repo)
    - [Staging and Committing](#staging-and-commiting)
    - [Connecting Repositories](#connecting-repos)
    - [Personal Access Tokens](#pat)
    - [SSH](#recommended)
- [Collaborating With Git](#collaborating-with-git)
    - [Utilizing Branches](#utilizing-branches)
    - [Branch Rules](#branch-rules)
    - [Creating Branches](#creating-branches)
    - [Specify Default Branch](#specify-default-branch)
    - [Pull Requests](#pull-requests)

## Useful Terminal Commands <a name="useful-terminal-commands"></a>

| command | uses | 
|---------|---------|
| `git --version` | to check the version | 
| `pwd` | print working directory | 
| `ls` | list all files/folders | 
| `ls -al` | to see all files/folders including hidden with more detail | 
| `cd` | change directory | 
| `cd..` | move back one directory | 
| `mkdir` <folder-name> | create a new directory |
| `touch <file-name>`| to create a file |  
| `git init` | initialize a git repository | 
| `git status` | show state of working directory |  
| `git add <file-name>` | to add a single file |  
| `git add .` | to add all files |  
| `git commit -m"<commit message>"` | to commit files with a message |  
| `git diff` | compare working directory to staging area |  
| `git push` | to push files to remote repository |
| `git ls-files` | to see whether any files might contain sensitive information are in repo |
| `git clone <repo-link>` | to copy a remote repo locally |
| `git pull` | to get remote changes locally |
| `git branch` | to see a list of local branches |
| `git checkout -b <branch-name>` | to create and switch into a new branch |
| `git checkout <branch-name>` | to switch to another branch |
| `git push origin <branch-name>` | to push files into branch |
| `git fetch` | to get remote branches locally |
| `git branch -D <branch-name>` | to delete local branch |

### What is version control? <a name="what-is-version-control"></a>
**Version Control** is used for any situation where you are creating content. It assists in keeping track of all the changes to a document, allowing you to go back to earlier versions. It can provide an off-site copy of data and it supports collaboration. 

### What is Git? <a name="what-is-git"></a>
**Git** is a version control system. It is fast, modern and fully-featured, while also being open source and free. Git also allows for distribution, where you can have local and remote copies of files.

### Installing Git  <a name="installing-git"></a>
1. Go to the [Git Website](https://git-scm.com/)

2. Go to download link for your operating system
3. Follow the download instructions
4. Run the installer and follow the steps
    - Choose your default editor (I use VSCode)
5. Launch GitBash
6. Run `git --version` to check it has been successfully installed

_See [Documentation](https://git-scm.com/doc) for more details_

### Account setup <a name="account-setup"></a>
Go to [Github](https://github.com)
Click the 'Sign up' button in the top right corner
Follow the steps to set up your account

### Creating a Repository <a name="creating-a-repo"></a>

1. In the GitBash Terminal Print your working directory using <br>
`pwd`

    - You can use `ls` (list) to see what files/folders are in your current working directory and use `cd` (change directory) to move between folders.

    - If you are in the directory that you want to save your files to then make a new folder for your repository to live in using <br>
`mkdir folder-name`

2. Change into your working directory <br>
`cd folder-name`

3. To initialize the folder as a repository run <br>
`git init`

4. Use `ls -al` to see all the files in your initialized repository. (There should be a hidden .git file)

    - If you would like to add a gitignore file use <br>
`touch .gitignore` <br>
    This is for files that are part of your local repository that you do not want stored on your remote/public repository i.e. environment files.

### Staging and Committing <a name="staging-and-commiting"></a>
Git is a system based on an opt-in approach which is utilised by the staging area. 

1. To see what files are in your working directory use <br>
`git status`<br>
Files not added to the local repository will be highlighted in red.

2. To move files from working directory into the staging area you use <br>
`git add file-name`<br>
or <br>
`git add .` to add all files <br>
_be sure to check the files before using git add ._

3. Run `git status` again, and the files in your working repository should be highlighted in green

4. To move files from the staging area to a local repository you use <br>
`git commit -m "message about your commit"`<br>
It isn't necessary to use the -m flag, however Git will ask you for a commit message, so this is a way of including it as part of your commit. Be sure to write meaningful commit messages. 
See [this link](https://www.freecodecamp.org/news/how-to-write-better-git-commit-messages/) for more information

5. _Optional_: Use <br>
`git diff` <br>to show the difference between the latest commits.

### Connecting Repositories <a name="connecting-repos"></a>

1. Click on the + icon in the top right corner
2. From the dropdown select 'New Repository'
3. Give your repo a name 
4. Choose whether you want it to be public or private
5. Click the Create Repository button
6. Follow the quick setup guide using HTTPS by copying the HTTPS link
7. In the terminal type <br> 
`git remote add origin<link>` <br>
    - Make sure the link is the same (pasting the link will sometimes add additional characters)

Now your connection is set up <br>

8. Add your files 
9. Run <br>
`git push origin main`

*You will be prompted to Login or to Use a Token*

#### For a Personal Access Token <a name="pat"></a>
- Go into your menu by clicking on your profile in the top right corner
- Click on settings
- On the left, at the bottom, click on Developer Settings
- Click on Personal Access Tokens to expand the drop down
- Click on Tokens (classic)
- Generate a new token
- Specify what the token is for 
- Select repo for scopes
- Copy the token and save it! Git will not give you access again. 
- Use the Personal Access Token to establish a connection from your machine to your github account

10. Refresh your browser to see the changes in your remote repository 

### Recommended <a name="recommended"></a>
Set up SSH keys by following this [Documentation](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

## Collaborating with Git <a name="collaborating-with-git"></a>

### Initial Setup 
- Create a Repository that you wish to collaborate in 
- On the repo page, click settings
- In the left hand menu, click collaborators 
- Add collaborators by username, full name, or email
- Click invite collaborators 
_Collaborators must accept invite, they will be listed in the collaborators system_
- Clone repository using `git clone` with the HTTPS or SSH link in the terminal 
- `cd` into the repository

### Utilizing Branches <a name="utilizing-branches"></a>
Branches are used to manage parrallel working. 
The main branch is not intended to day-to-day development, but for production ready development. Instead we use a development branch alongside feature branches while building up a project.

#### We can set branch protection rules for main/development branch. <a name="branch-rules"></a>
- For the main/dev branch, in the repo, go to settings and click on Branches from the left side menu. 
- In Branch name pattern, type the name of the branch where you want to set rules. 
- Select require pull requests before merging and require approvals.

#### Creating New Branches <a name="creating-branches"></a>
To create a new branch use <br>
`git checkout -b <branch-name>`
This will create a new branch and move you into it.<br> 
Use <br>
`git push origin <branch-name>` to add branch to Remote repository

#### Specify the Default branch <a name="specify-default-branch"></a>
In Repository settings click on General
Change default branch to dev branch


### Pull Requests <a name="pull-requests"></a>
Pulll requests are used to merge the working branch into the main/developement branch

- On Github go into the branch by selecting the branch name in the dropdown of the repository
- Click on the highlighted notification that says '<#> commits ahead of main/dev'
- Click create Pull Request
- Assign reviewers on left hand side
- Once approved click 'Merge'
- Click 'confirm merge'
- Delete branch
- Switch to main/dev branch locally 
- run `git pull` in terminal 
- run `git branch -D <branch-name>` to delete branch locally

