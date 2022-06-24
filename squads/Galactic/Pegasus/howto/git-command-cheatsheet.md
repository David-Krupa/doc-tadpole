# Git commands cheat sheet for non-engineers

## Reviewing a copy of a branch

1. I want to check out the latest copy of a branch and review the work

- First, open two terminals to each point to the root of the project on both frontend (react) and backend (python) sides.

###### Frontend side:
- `git fetch` - pull down all new and updated branches from the repo.
- `git checkout {branch_name}` - switch to a different branch
- `npm install` - optional. If you see an error after `npm start` 9 out of 10 times you will have to install dependencies again to resolve this.
- `npm start` - this will start up the react app

###### Backend side on master branch:
- `./start-dev.sh` - start up db and backend environment
- Go to localhost:3000 on browser. Should be able to see running app
- Go to localhost:8000/admin to go to the admin portal and edit any data

2. I want to switch to a branch but there is a change in code that is preventing me from doing so

- `git stash` - stashes away the changes for later use

OR

- `git reset --hard head` - deletes the existing changes

## Making changes

1. I want to make a new branch and switch to the branch
- git branch {branch_name} then git checkout {branch_name}

OR

- git checkout -b {branch_name}


2. I want to make changes to an existing branch, make changes, then update the branch

- `git fetch`
- `git checkout {branch_name}`
- Make your changes
- `git status` - optional. Shows branch info and existing new changes
- `git diff` - optional. Shows differences between last commit and after changes
- `git add .` - stages all file changes to be committed
- `git commit -m "{commit_message_here}"` - makes a commit with a commit message
- `git push origin {branch_name}` - push up your changes to the repo
- Go to gitlab to make your merge request

