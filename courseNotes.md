# Configure git

These commands set git settings on the local computer

```sh
# Set name of user
git config --global user.name "Trevor Freeman"

# Set email
git config --global user.email "trevor.freeman@utexas.edu"

# Set default text editor
git config --global core.editor "vim"
```

# Setup repository

Create directory

```sh
mkdir planets
```

```sh
cd planets

git init
git status
```

Create file to add to repository

```sh
vim mars.txt
```

Add and commit to git
* Good commit messages should be short, descriptive, and useful

```sh
git add mars.txt
git commit -m "Start notes on Mars as a base"
```

Modify the example file

```sh
vim mars.txt

git status

# See which files have been changed
git diff

git add mars.txt
git commit -m "Add concerns about effects of Mars's moons on Wolfman"
```

## Best practice

Make changes in small chunks
* Atomic changes are easier to track changes for
* Uploading lots of changes at once will be hard to keep track of

## Make more changes

```sh
vim mars.txt

git diff
git add mars.txt

# Do we see a difference after adding?
git diff
# No
git diff --staged
# Yes

# Commit
git commit -m "Discuss concerns about Mars's climate for Mummy"

# View commitments
git log
```

# How does git handle directories?

```sh
mkdir spaceships

# Does git recognize a new directory?
git status
# No

git add spaceships/
```

Add files to new directory

```sh
touch spaceships/apollo-11 spaceships/sputnik-1
git add spaceships/apollo-11 spaceships/sputnik-1
git commit -m "Add some initial thoughts on spaceships"
```

Undo a change you didn't want to make

```sh
# Edit file
vim mars.txt

# See the change you made
git diff

# Undo the change
git checkout marx.txt
```

# Ignoring things with git

Create another directory and make some more files

```sh
mkdir results
touch a.dat b.dat c.dat
```

Create .gitignore file

```sh
vim .gitignore

git add .gitignore
git commit -m "Add gitignore file to ignore certain files"
```

# Add remote repository on github

1. Log into github account
2. Create New repository
3. Copy link from github
4. Link local repository to remote:
```sh
git remote add origin https://github.com/t-f-freeman/planets.git
```
5. Push local repository to remote:
```sh
git push origin master
```
```
