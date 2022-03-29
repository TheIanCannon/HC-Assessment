## Content

### What is the difference between `git push`, `git pull`, and `git fetch`?

- `git push` sends changes from a local branch to a remote repo.
- `git fetch` brings changes from a remote repo into your tracking branch.
- `git pull` performs the same action as `git fetch`, and then merges the changes into a local branch.

`git push` takes our current branch, and checks to see whether or not there is a tracking branch for a remote repository connected to it. If so, our changes are taken from our branch and pushed to the remote branch. This is how code is shared with a remote repository, you can think of it as "make the remote branch resemble my local branch". This will fail if the remote branch has diverged from your local branch: if not all the commits in the remote branch are in your local branch. When this happens, your local branch needs to be synchronized with the remote branch with `git pull` or `git fetch` and `git merge`. 

`git fetch` again takes our current branch, and checks to see if there is a tracking branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch. To do that, you'll need to do `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".

`git fetch` and `git pull` are often described as being equivalent. In actuality, `git pull` does two things.  `git pull` simply does a `git fetch` followed immediately by `git merge`. This is often what we desire to do, but some people prefer to use `git fetch` followed by `git merge` to make sure they understand the changes they are merging into their branch before the merge happens.