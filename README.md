# Common Git Commands

This repository holds common Git commands that are sometimes hard to remember. Please feel
free to contribute to this by forking the repository, updating, and submitting a 
pull request.

## Commands

### Delete a remote branch

There are two different ways of doing this. I find the first a little more intuitive and easier to remember.

```bash
$ git push origin --delete <branch>
$ git push origin :<branch>
```


### Delete local reference to a remote branch

```bash
$ git remote remove <branch>
```


### Force push to a remote branch

This command is useful with a git reset to make a quick fix to a previous commit.

```bash
$ git push <remote_repo> +<branch>
```


### Push a specific local branch to remote branch 

```bash
$ git push <remote_repo> <local_branch>:<remote_branch>
```
For example:

```bash
$ git push origin my-branch:master
```

### Revert to the last commit LOSING ALL CHANGES

This command is a dangerous one if not used properly. It is recoverable though (so long as you don't wait more than a few days).

```bash
$ git reset --hard HEAD^
```

If run accidentally, your repository could be recovered using a <code>git reflog</code> and using this this command with the specific hex value for the commit you'd like to return to. See [this](http://stackoverflow.com/questions/5473/undoing-a-git-reset-hard-head1) link.


### Undo a previous commit without losing any local changes

Take care when using this as not to force push your repository to github once others have added it to their local repository.

```bash
$ git reset --soft HEAD^
```


### Create a new branch and switch to it

```bash
$ git checkout -b <new_branch>
```

### Keep a forked branch up to date

```bash
$ git remote add upstream https://github.com/username/original-repo.git
$ git fetch upstream
$ git merge upstream/master
$ git push origin master
```
