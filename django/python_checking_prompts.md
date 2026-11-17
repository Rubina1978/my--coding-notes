## activate venv in Powershell

```bash
.venv\Scripts\activate.ps1

```

## check virtual environment exist

```bash
dir .venv\Scripts\python.exe

```

## choose python interpreter manually

```bash
.venv\Scripts\python.exe

```

## find version of python
```bash

python --version

```
## find pygame
```bash
python -m pip show pygame

```
## commands to merge other branch on git working with other's branches

```bash

git fetch origin  # checks the remote GitHub repository for new changes and downloads information about them
git switch main  # switches me for local 'main' branch, tells Git which branch i want to work on
git merge orgin/name-of-branch # Attempts to bring teammate's changes into the branch Im currently on

```
## checking status of git

```bash
git status # the most important. It tells which branch I'm on, if the files have changed, what i yet to be commited, if merge is already in progress, if there is any conflict
```

## What is the workflow - how the commands work together?

```bash

git fetch origin # check for teammate's updates
git switch main # move to mine main branch
git merge origin/name-of-the-branch # bring the teammate's branch work into main
git status # check whether everything worked and what is going on right now
git add
git commit
git push  # save and upload changes
git diff #check what got changed
git restore . # restore to state before change

#  NEVER USE AS IT DESTROYS WORK THAT WAS NOT SAVED!!!

git reset --hard
git clean -fd