## Content

### What is the difference between push, pull, and fetch?

This page describes how to use the push, pull, and fetch Git commands to make changes to a shared repository.  

- `git push` - Publishes changes from a local repository to a remote repository. These changes update the remote repository to resemble your local branch. 
- `git fetch` - Safely downloads committed files and references from a remote repository into your local repo. It is considered safe because files must be checked out using the git checkout command before changes can be made, and it does not automatically merge them with your local repository.
- `git pull` - Fetches and merges the remote repository to your local file. This action can overwrite local changes that have yet to be committed.

`git push` takes our current branch, and checks to see whether or not there is a tracking branch for a remote repository connected to it. If so, our changes are taken from our branch and pushed to the remote branch. This is how code is shared with a remote repository, you can think of it as "make the remote branch resemble my local branch". This will fail if the remote branch has diverged from your local branch: if not all the commits in the remote branch are in your local branch. When this happens, your local branch needs to be synchronized with the remote branch with git pull or git fetch and git merge.`git fetch` again takes our current branch, and checks to see if there is a tracking branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch. To do that, you'll need to do `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".`git pull` simply does a `git fetch` followed immediately by `git merge`. This is often what we desire to do, but some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.
