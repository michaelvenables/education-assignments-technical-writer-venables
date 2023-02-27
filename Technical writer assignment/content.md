---

## Content

### What's the difference between git push, git pull, and git fetch commands?

In a typical git workflow, you update Markdown code with requests from a local (tracking) branch to a remote (origin) branch—your fork from the original (upstream) repo.

- `git push` - sends changes from a local tracking branch to a remote (origin) branch, your fork.
- `git pull` - retrieves changes from a remote (origin) branch into your local tracking branch and merges them into your local tracking branch, but without letting you review them first.
- `git fetch` -  retrieves changes from a remote (origin) branch that doesntn't exist in your local tracking branch, but doesn't merge them.

Users often conflate `git pull` and `git push` commands as performing the same function. The `git push` command takes your current branch and checks if your local tracking branch is connected to your remote (origin) branch. If so, changes you make on your local tracking branch are pushed to your remote (origin) branch—and the code shared with your remote (origin) repository. You're updating your remote (origin) branch to the current state of your local tracking branch.  

The `git push` command will fail if your local branch falls behind and doesn't contain all the commits in your remote (origin) branch. In this case, your local tracking branch needs to be synchronized with the remote (origin) branch. Use the commands `git pull` (refer to guidance below on the `git pull` command) or `git fetch` and `git merge` to perform this sync action. 

The `git fetch` command checks your local tracking branch's connection to your remote (origin) branch—searches for changes—gathers them into the tracking branch without merging them. This is useful if you want to update your local tracking branch but aren't yet ready to merge changes. To merge your changed files, use the `git merge origin/main` command (for the `main` branch) to merge changes into your local tracking branch. 

You may prefer to use the `git pull` command. Remember that it performs a `git fetch` operation followed by a `git merge`, and after fetching your commits, automatically merges them into your active tracking branch without letting you review them first. You may run into conflicts if you don't follow best practices for branch management.