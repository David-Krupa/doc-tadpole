<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

## Sources

*   Emails authored by Sam James
*   Existing BrainGu Confluence docs
    *   [https://braingu.atlassian.net/wiki/spaces/ENG/pages/444268550/Source+Control](https://braingu.atlassian.net/wiki/spaces/ENG/pages/444268550/Source+Control)
    *   [https://braingu.atlassian.net/wiki/spaces/BG/pages/66030898/Source+Control](https://braingu.atlassian.net/wiki/spaces/BG/pages/66030898/Source+Control)


## Goals

1. It should be easy to tie a change in the source code to a feature or bugfix request.
2. It should be easy to figure out what changed in the source code for a feature or bugfix.
3. The guidelines should protect the repository from common mistakes and bad practices.
4. The repository should be structured in a way to encourage good CI/CD practices.
5. All code should be excellently documented.


### Branching Model

The key takeaways for non-pair programming requirements are:

*   protected master branch
*   paired merge requests

### Master

*   Current state.
*   Branches should be made from master.
*   Merges should be made to master.
*   "Releases" should be tagged commits in the master branch.
*   The pipeline will publish artifacts for tagged commits only.
*   The tag should match the version number of the artifact (tag v0.1.5 should produce my-awesome-artifact-0.1.5.tar.gz).


### Feature/bugfix branches

Working copies of the repo should be branched from the current version of master. These branches can create artifacts, but not publish them. These branches should adhere to and pass any tests or code quality checks before being merged to master. Artifacts created by these branches should be versioned with the short commit id (my-awesome-artifact-0.1.5-a39e40e.tar.gz). Once a merge request has been accepted and the changes have been merged to master, the branch should be deleted.


## Steps

### Step 1: Fork the project

Every project has a central repo, which is the canonical source code repository.  You, as a developer, should not be able to push changes to the central repo without going through a merge request. In order for you to have a space to do your work, you will fork a personal repo of the project.

1. Go to the project page and click on the Fork button.
2. Make sure to select your personal group for the location of the fork.

All your development and commits happen on your forked repo.

### Step 2: Clone the repo

Make sure that you are cloning the fork to your personal repo, instead of cloning the central repo to your development environment.

```
$ git clone <url for your FORKED repo>
```

### Step 3: Create a working branch

Create a branch for your feature or bugfix, named after the ticket in Jira. For example, you are tasked with working on the BG-312 ticket, which is about adding a confirmation dialog.  You should name your branch as follows:


```
$ git checkout -b feature/BG-0066-improve-noms
```

Branch names should start with `feature`, `bugfix`, or `hotfix`, followed by a ticket label, followed by a short description. Examples:

```
    feature/BG-1023-add-for-help
    bugfix/QA-0612-fixed-screensize-bug
```

Try to avoid spaces or special characters in the branch name.


### Step 4: Do the work!

Make whatever changes are necessary to the source code and commit as often as you like.  It makes sense to push those changes back to your Personal Repo so that you can back it up and share it with others.

Use good coding and git practices here

*   `Commit all` is considered harmful: don't use `git commit -a`, since you will likely introduce artifacts and junk into the repo
*   Run a `git status` before commit: make sure everything looks correct
*   Use `gitignore`: this prevents you from adding object or project files such as pyc or Eclipse files
*   Run `git diff`: you should confirm that the changes you are adding are correct.


### Step 5: Commit locally

Commit your changes to your cloned repo and then push it to your forked repo:
```
$ git commit -m 'feature/BG-0066: Improved the noms for the flux capacitor'
$ git push -u origin feature/BG-0066-improve-noms
```

### Step 6: Prepare the Merge Request

Before making the merge request


1. Pull any changes to the branch from the central repo. See [Pulling from a Central Repo](https://docs.google.com/document/d/15HWFFtxtwu6-GPuvMOa7VmE8O9FG9CJiEMu1MoSTEaw/edit#heading=h.hle4ema7yjoh).

2. If there have been any changes to the branch, you will need to rebase your commits and resolve any conflicts. See Rebase below. A rebase can be as simple as:

 ```
$ git checkout my_really_cool_branch
$ git rebase master
```

3. The only complicated part is when there are merge conflicts.
4. Just because there are no merge conflicts, does not mean that everything will magically work.  A previous commit might have changed the behavior or removed a method you are using.  If you have to rebase, test your code again!
5. The final part is cleaning up your commits.  We recommend you squash them into a single commit and make sure the commit message is descriptive.  See the [Git](https://braingu.atlassian.net/wiki/spaces/ENG/pages/444399626/Git) page and [Squashing your commits](https://docs.google.com/document/d/15HWFFtxtwu6-GPuvMOa7VmE8O9FG9CJiEMu1MoSTEaw/edit#heading=h.tgcqk4sb9f1k).
A good format for your commit message is:

```
feature/STRUCT-123: added an option to allow foo to interact with bar when beef is set
```

### Step 7: Create the Merge Request
1. In GitLab, go to the project page for your personal repo. In the left column, click on Merge Requests then click on the New Merge Request button.
2. Select the proper source branch from your repo and the proper target branch (central) on the central repo. This varies depending on your source control tool (GitHub vs Bitbucket and so on).  The main points here are:
    1. Make a pull request from your FORKED repo
    2. The source branch should be your work branch you created initially
    3. The destination should be the CENTRAL repo
    4. The destination branch should be master
    5. Add appropriate reviewers
3. In the Description field, add plenty of information on what the changes are, how to test them, and links to anything the reviewers might need.
4. In the Assignee field, assign the merge request to the person responsible for approving them.
5. Notify your team members and request their help in reviewing the request.


### Step 8: Changes during the Merge Request

As your fellow team members review your merge request, you may need to make changes to your commit based on their feedback and suggestions.  If you need to do that, go back to your personal repo, commit and push your changes.  Gitlab will automatically update the merge request with the new changes.

If you end up adding a few commits due to feedback, don't forget to squash them again before they are merged into the branch!


### Step 9: Clean up your forked repo from your machine

```$ git checkout master
# you can't delete a branch if you are currently in it
$ git branch -d feature/BG-0066-improve-noms
# delete the branch on your CLONED repo
$ git push --delete origin feature/BG-0066-improve-noms
# delete the remote branch on your FORKED repo
```

### Step 10: Done

Once all the comments have been resolved, the merge request is approved and your task is complete.  Congratulations, you just contributed code to a project!


## General Git Practices


### Gitconfig

Here are some useful .gitconfig settings


```
[user]
    name = John Doe
    email = john.doe@braingu.com
[alias]
    hist = log --oneline --all --graph --decorate
    mr = !sh -c 'git fetch $1 merge-requests/$2/head:mr-$1-$2 && git checkout mr-$1-$2' -
[push]
    default = simple
[core]
    editor = vim
```



### Commit messages

*   [https://chris.beams.io/posts/git-commit/](https://chris.beams.io/posts/git-commit/)

Commit messages are important! The tl;dr on commit messages is this:

*   short and concise title.
*   Clear and detailed body.
*   No messages like "Added the thing" or "Reverted Changes".


### Rebase

*   [https://medium.com/@dirk.avery/the-definitive-git-rebase-guide-dbd7717f9437](https://medium.com/@dirk.avery/the-definitive-git-rebase-guide-dbd7717f9437)

If you run into problems with either your branch falling behind master or your commits being subpar you can always rebase!


### Merge requests

When doing a merge request,

1. Does the code follow the appropriate style guide?  Some examples:
    *   Python code (BrainGu's version of PEP8)
    *   YAML (use yamllint)
    *   Javascript (best practices)
2. Is the commit message in the right format? (eg - feature/BG-113: added password reset option)
3. Does the code introduce any security concerns?
4. Does the code have appropriate error handling?
5. Are the commits squashed?
6. Has the submitter tested the code end-to-end?
7. Have the appropriate quality tools been run and the reports attached to the Merge Request?  (eg - coverage, prospector, yamllint)
8. Have the UX changes been reviewed and approved by the User Representative?
9. Is the Merge Request pointing to the appropriate branch? (eg - is it to the integration branch?)


### Reviewing merge requests

If you are doing a code review in gitlab and would like to check out the merge request (assuming you have an alias for the mr command in your .gitconfig file as shown above), do the following:



1. Every merge request in gitlab has a number assigned to it.  You need to find this number before using the mr command.  If you go to the top of the Merge Request page in gitlab, you will see something like the following:

    ```
    sandbox > testrepo > Merge Requests > !42
    ```

    The number at the end, without the exclamation point, is the merge request number.  In this case, 42.

2. In the git repo directory, use the mr command as follows:

    ```
    $ git mr origin 42
    ```

3. That command will fetch the branch with the merge request commits and check it out.  The branch will be named mr-origin-42.
4. You can confirm that you are in the correct branch:

    ```
    $ git branch
      master
    * mr-origin-42

    ```

You can also pull any updates with the standard pull command:

```
    $ git pull
```

### Pulling from a central repo

When you fork a project, the central repo may get new commits that you need in your forked, personal repo.  Let's say you want to be able to pull them.  First, add the central repo as a remote repo in your repository.  Go to the central repo and copy the URL for the repo.  Then run the following commands:


```
$ git remote add central git@gitlab00.core.braingu.net:sandbox/testrepo.git
$ git remote -v
central git@gitlab00.core.braingu.net:sandbox/testrepo.git (fetch)
central git@gitlab00.core.braingu.net:sandbox/testrepo.git (push)
origin  git@gitlab00.core.braingu.net:gil/testrepo.git (fetch)
origin  git@gitlab00.core.braingu.net:gil/testrepo.git (push)
```

Get all the new commits from the central repo:

```
$ git fetch central
```

If you want to update your personal repo with the changes from central, first checkout the master branch:

```
$ git checkout origin master
```
Now merge in the changes from central:

```
$ git merge central/master
```

### Squashing your commits

If you have several commits that you would like to squash to a single commit, here is a simple strategy.  Assume you started on the master branch and you created a branch for your feature:

```
$ git checkout -b my_feature
```

Pretend you made a few commits and the git commit history now looks like this:


```
$ git hist
* 091b3b2 (HEAD -> my_feature) Improvements based on merge request comments
* ac0d439 Fixed a small typo
* e704cb5 Improved the README file
* 5b4289d (master) Initial commit
```

You want to squash the top three commits into a single commit with a sane commit message.  Run this command:

```
$ git rebase -i master
```
In this case, the command is running an interactive rebase from the HEAD commit to the master commit, not including the master commit.  An editor will pop up showing you all the commits that you are rebasing:


```
pick e704cb5 Improved the README file
pick ac0d439 Fixed a small typo
pick 091b3b2 Improvements based on merge request comments


# Rebase 5b4289d..fc9adc7 onto 5b4289d (3 commands)
#
# Commands:
# p, pick = use commit
# r, reword = use commit, but edit the commit message
# e, edit = use commit, but stop for amending
# s, squash = use commit, but meld into previous commit
# f, fixup = like "squash", but discard this commit's log message
# x, exec = run command (the rest of the line) using shell
# d, drop = remove commit
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
```


You need to make sure the first commit remains pick but change every subsequent pick to `squash`.  The file will look like this now:


```
pick e704cb5 Improved the README file
squash ac0d439 Fixed a small typo
squash 091b3b2 Improvements based on merge request comments


# Rebase 5b4289d..fc9adc7 onto 5b4289d (3 commands)
#
# Commands:
# p, pick = use commit
# r, reword = use commit, but edit the commit message
# e, edit = use commit, but stop for amending
# s, squash = use commit, but meld into previous commit
# f, fixup = like "squash", but discard this commit's log message
# x, exec = run command (the rest of the line) using shell
# d, drop = remove commit
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
```


Once you save the file and exit the editor, you will have the option to modify the commit message.  The editor will look something like this:

```
# This is a combination of 3 commits.
# This is the 1st commit message:


Improved the README file
# This is the commit message #2:
Fixed a small typo
# This is the commit message #3:

Improvements based on merge request comments

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# Date:  	Wed Jun 6 20:03:40 2018 +0000
#
# interactive rebase in progress; onto 5b4289d
# Last commands done (3 commands done):
#	squash 268d880 Fixed a small typo
#	squash 091b3b2 Improvements based on merge request comments
# No commands remaining.
# You are currently rebasing branch 'my_feature' on '5b4289d'.
#
# Changes to be committed:
#   	modified:   README.md
#
```

Change any line that is not commented out and make the new commit message.  Save the file and exit.  The git commit history will now look like this:

```
$ git hist
* 2234f74 (HEAD -> my_feature) Improved the README file
* 5b4289d (master) Initial commit
```


If you had previously pushed any of the other commits out to a remote repo, you will have to do a force push to correct the remote repo.  This is usually a bad idea if you are sharing this repo with other people.  If it is a personal repo or a forked repo that only you use, go for it:


```
$ git push -f
