## Git Hidden Folder

There is a hidden folder, called `.git` which tells you that our project is a git repo.

If we want to create a git repo in a new project we'd create the folder and then initialise that repo using `git init`.
```sh
mkdir /workspaces/tmp/new-project
cd /workspaces/tmp/new-project
git init
touch Readme.md
code Readme.md
git status
git add Readme.md
# makes changes to readme.md
git commit -a -m "add readme file"
```

## Cloning

We can clone three ways: HTTPS, SSH, GitHub CLI

Since we are using GitHub Codespaces, we'll create a temporary directory in our workspace.

```sh
mkdir /workspace/tmp
cd /workspace/tmp
```


### HTTPS
```sh
git clone https://github.com/Matt-Olson-UC/GitHub-Examples.git
cd GitHub-Examples
```

> You'll need to Personal Access Token (PAT) 
https://github.com/settings/token

You will use the PAT as your password when you log in, from VS Code.

### SSH

```sh 
git clone git@github.com:Matt-Olson-UC/GitHub-Examples.git
```

We will need to create our own SSH rsa key pair
```sh
ssh-keygen -t rsa
```

We can test our connection here:
```sh
ssh -T git@github.com
```

For WSL users and if you create a non default key you might also need to add it
```sh
eval `ssh-agent`
ssh-add /home/andrew/.ssh/alt-github_id_rsa
```

### GitHub CLI
Install it via homebrew on Mac - https://cli.github.com/
```
brew install gh
```

```
gh login 
gh repo clone Matt-Olson-UC/GitHub-Examples
```

## Commits

When we want to commit code we can write `git commit` which will open the commit edit message in the editor of choice.

```sh
git commit
```

Set the global editor (emacs for example)
```sh
git config --global code.editor emacs
```

Make a commit and commit message without opening editor
```sh
git commit -m "Add Message Here"
```

## Branching

List of branches
```
git branch
```

Create a new branch (with the name dev for example)
```
git branch dev
```

Checkout the branch
```
git checkout dev
```


## Remotes

## Staching

## Merging

## Add

When we want to stage changes that will be included in the commit. We can use the . to add all possible files

```sh
git add Readme.md
git add .
```

## Reset

Reset allows you to move staged changes to be unstaged. This is useful when you want to revert all files not to be committed.

```sh
git add .
git reset
```

> git reset will rever a git add.

## Status

Git status shows you what files will or will not be committed.

```sh
git status
```

## Gitconfig file

The gitconfig file is what stores your global configurations for git such as email, name, editor and more.

Show the contents of the .gitconfig file
```sh
git config --list
```

When you first install Git on a machine, you are supposed to setup your name and email.

```sh
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

## Log
git log will show recent git commits to the git tree

```sh
git log
```

## Push

When we want to push a repo to our remote origin

```sh
git push
```