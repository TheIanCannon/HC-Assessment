## Content

### What is the difference between `git push`, `git pull`, and `git fetch`?

- `git push` sends changes from a local branch to a remote repo.
- `git fetch` brings changes from a remote repo into your tracking branch.
- `git pull` performs the same action as `git fetch`, and then merges the changes into a local branch.

`git push` checks your current branch to see if it is connected to a remote repository's tracking branch. If so, your changes are pushed from your branch to the remote branch. If all the commits from the remote branch are in your local branch, `git push` will succeed. If the remote branch has diverged from your local branch, you will receive an error message instead. Synchronize your local branch with the remote branch using `git pull`, or `git fetch` and `git merge`. Next, use `git push`. The remote repository will then match your branch.  

`git fetch` also checks to see if a remote repository's tracking branch is connected to your current branch. If so, it pulls any changes from the remote branch into your tracking branch. `git fetch` does not overwrite your local branch. To merge changes into your branch, use `git merge origin/master`. If your local branch is named differently, such as 'main' instead of 'master', use that name instead. Your local branch will then match the remote repository.

`git pull` and `git fetch` are often described as being equivalent. In actuality, `git pull` performs `git fetch` followed immediately by `git merge`. We prefer `git pull`, but you may use `git fetch` to ensure you understand the changes you are making to your branch before completing them using `git merge`. 