# maxmsp-git

A [Max/MSP](https://cycling74.com/products/max/) patch for integrating git directly into your patch.

*This patch is still very new and under development, use at your own risk!*
Please report issues and I will happily fix them :)

This currently implements only a few of the many powerful things you can do with git.

## init

`git init && git remote add origin <remote_repository_URL>`

Initialize your local directory to git url

## add

`git add .`

This will mark new files for addition into the git repository

## commit

`git commit -a -m "<your_message_here>"`

Make sure to include your git commit message so you know what change you made!

This will "commit" your changes, marking them as ready to push to your repository.

## push

`git push --rebase`

This will actually push your code up to your repository.  `--rebase` will safely ensure you don't mix up your commits with those of other people working on the code, or yourself working on another computer.

## status

`git status`

This will display the git status of your project.  It will show any files changed, current branch, commits ready to be pushed, etc.

## reset

`git reset --hard @{u}`

Reset to upstream branch (make it match what is on github)

## undo

`git reset --hard HEAD^`

Undo changes since the last commit

## log

`git log`

This will show you a list of recent commits, in chronological order, with the most recent at the top.

## Things not included, but hope to be included soon

`git checkout origin <branch_name>` and `git checkout -b origin <branch_name>`

- checkout branch and create new branch

`git config`

- setting all the git config options

`git stash save "<name>"`

- stashing changes to undo them, but save for later

### merging

I currently don't have any merging stuff in here, because:

1.  I haven't done it with a Max project yet
2.  I hear it's very tricky to merge because of the nature of the .maxpat files (Max apparently often reorganizes the inner code, which makes git think there's a lot more changes than there really are)
3.  I would like to create some sort of git diff tool for max (for examining changes from one version to the next)
