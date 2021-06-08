### Git Refresh exercise

1.  Please fork this repository and clone it in two places in order to simulate multiple people working on the same repository - let's call the two places as `directory1` and `directory2`.
2.  From `directory1`, please try swithcing to different branches available from cmd line and try to figure out which branch is the latest one based on number of commits and other information
3.  Let's create a new branch called `feature1` with base branch as `release`
4.  Let's add 2 commits with commit messages "feature 1 - commit 1" and "feature 1 - commit 2", first commit adding the line "feature 1 - commit 1" in line 4 and second commit adding "feature 1 - commit 2" in line 5 in contents.txt.  Once you commit it, try to change the git commit message.
5.  Now let's merge these changes to `release` branch.  Switch to `release` branch, if you do git log here, you should see 3 commits.
6.  Try merging the `feature1` branch changes to this branch, initially merge it without squashing the commits.
7.  Now git log should return us 5 commits, 2 from `feature1` branch, delete the commits that came from feature branch alone.
8.  Let's try merging again, but this time squash the 2 commits of feature1 branch to 1 commit while merging, so that in release branch when you finally do `git log` you should only see 4 commits. (1 for readme, 2 for relase branch, 1 from feature1 branch)
9.  Usually at this point, we'll push the changes to the remote repository and that is straight forward, so let's skip that.  In most real life scenarious before we try to push to the base branch, it would've advanced forward, so let's try to recreate the scenario now.
10.  Switch to `directory2`, that we cloned in step1.  Let's switch to `release` branch.  Now let's merge the changes of `feature2` to `release` branch, but instead of using `git merge`, let's `cherry-pick` the commits one by one from `feature2`.  First pick the commit with message "feature 2 - commit 1", for the second commit with commit message "feature 2 - commit 2" use the `-n` option of cherry-pick to fix the issue in line 5 of contents.txt in `feature2`.  Once you are done experimenting with `cherry-pick` to merge the changes, push the release branch to remote.
11.  Let's go back to `directory1`.  Now the case is, we have some changes in release branch of `directory1`, but there are some new changes in the remote release branch that we just pushed from `directory2`.
12.  Our objective here is to merge the local release branch and remote release branch without losing any contents - please experiment with just git pull, git pull with rebase, git fetch and git merge, and for each type, check the `git log` to check the order of commits.  You will get merge conflict while merging it, resolve and push it.


### Note
Except for step 10, all the other steps are done from `directory1`.


### Other things to try out
1. Different ways to reset local changes
2. Renaming branch
3. Check remote tracking branch
4. `git stash`
