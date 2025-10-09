## Git Hidden folder 

There is a hidden folder called `.git` which tells you that your project is a git repo.

If we wanted to cerate a git repo in a new project we create the folder and then initialize that repo using `git init`

```sh
mkdir /workspaces/tmp/new-project
cd /workspaces/tmp/new-project
git init
touch Readme.md
open Readme.md
git add Readme.md
# make changes to Readme.md
git commit -a -m "add readme file"
```

## Clone

We can clone three ways: HTTPS, SSH, GitHub CLI

Since we are using GitHub Codespaces we`ll a create temporarty directory in our workspace
```sh
mkdir /workspace/tmp
cd /workspace/tmp
```

### HTTPS
```sh
git clone https://github.com/1ByteBuster1/GitHub-Examples.git
cd GitHub-Examples
```

> You`ll need to generate a Personal Access Token (PAT)
You will use PAT as you password when you login

### SSH

```sh
git clone git@github.com:1ByteBuster1/GitHub-Examples.git
cd GitHubExamples
```

We will need to create our own SSH rsa key pair

```sh
sshe-keygen -t rsa git@gitchub.com
```

For WSL users and if you create a non default key you might to add it 

```sh
eval 'ssh-agent'
ssh-add /home/user/.ssh/alt-github_id_rsa
```

We can test our connection here:

```ssh
ssh -T git@github.com
```

### GitHub CLI

Install the CLI

eg. Ubuntu
```sh
(type -p wget >/dev/null || (sudo apt update && sudo apt install wget -y)) \
	&& sudo mkdir -p -m 755 /etc/apt/keyrings \
	&& out=$(mktemp) && wget -nv -O$out https://cli.github.com/packages/githubcli-archive-keyring.gpg \
	&& cat $out | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
	&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
	&& sudo mkdir -p -m 755 /etc/apt/sources.list.d \
	&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
	&& sudo apt update \
	&& sudo apt install gh -y
```

```sh
gh auth ogin
gh repo clone 1ByteBuster1/GitHub-Examples
```

## Commits

When we want to commit code we can write git commit which will open up the commit edit message in the editor of choice.

```sh
git commit 
```

Set the global editor 
```sh
git config --global core.editor emacs
```

Make a commit and commit message without opening an editor
```sh
git commit -m "add !!"
```

## Branches

List of branches

```sh
git branch 
```

Create a new branch

```sh
git branch branch-name
```

checkout the branch

```sh
git chekout dev
```

## Remotes

## Stashing

## merging

## ADD

When we want to stage file we use git add

```sh
git add Readme.md
git add .
```

## Reset

Reset allows you to move staged changes to be unstaged
This is useful when you want to revert all files not to be commited

```sh
git add .
git reset
```

> git reset will revert a git add.

## Status

Git Status show you what files will or will not be commited.

```sh
git status
```

## Gitconfig file

The gitconfig file is what stores your gloabal configuration for git such as email, name, editor and more.

Showing the contents of our .gitconfig file
```sh
git config --list 
```

When you first install Git on your machine you are suppose to set up your name and email
```sh
git config --global user.name "John Doe"
git config --global user.mail johndoe@example.com
```

## Log
git log will show recent git commits to the git tree

## Push

When we want to push a repo to our remote origin

```sh
git push
```