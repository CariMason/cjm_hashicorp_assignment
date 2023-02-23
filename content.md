## Content

### What is the difference between push, pull, and fetch?

This page describes how to use the push, pull, and fetch Git commands to make changes to a shared repository.  

- `git push` - Publishes changes from a local repository to a remote repository. These changes update the remote repository to resemble your local branch. 
- `git fetch` - Safely downloads committed files and references from a remote repository into your local repo. It is considered safe because files must be checked out using the git checkout command before changes can be made, and it does not automatically merge them with your local repository.
- `git pull` - Fetches and merges the remote repository to your local file. This action can overwrite local changes that have yet to be committed.

`git push` verifies if there is a tracking branch for a remote repository connected to the current branch. If so, the changes are pushed to the remote branch. This is how you share code with a remote repository. Think of it as "make the remote branch resemble my local branch." 

If the remote branch has diverged from your local branch, the git push command will fail with the following message:  “error: Your local changes to the following files would be overwritten by merge.” 

**NOTE**: The `git status` command safely displays differences between the local and remote branches. 

If your `git push` command fails, you can overwrite your local changes using a `git pull` or preserve your local changes using the following workflow example:

- `git fetch` - Brings the diverged changes to your local branch without merging them.
- `git stash` - Saves your local changes.
- `git merge origin/master` - Integrates the changes from the remote and local branches. 
- `git stash pop` - Brings your local changes back and removes the stash commit.


`git fetch` verifies if there is a tracking branch for a remote repository connected to the current branch. If so, it looks for changes in the remote branch and pulls them into the tracking branch, and does not change your local branch. 
