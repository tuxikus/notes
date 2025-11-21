# Git Worktrees
Worktrees fixes the problem of stashing by keeping different versions of the repo in different directories.

## Basic Commands
```shell
  $ git worktree list
  $ git worktree add
  $ git worktree remove
```

## Working with worktrees the clean way
### Using an existing repo
```shell
  $ mkdir project
  $ cd project
  $ git clone --bare https://github.com/user/repo.git .bare
  $ echo "gitdir: ./.bare" > .git
  $ git config remote.origin.fetch "+refs/heads/*:refs/remotes/origin/*"
  $ git worktree add feature-branch
```

### New repo
```shell
  $ mkdir project temp-project
  $ cd temp-project
  $ echo "# Project" > README.md
  $ git commit -m "initial commit"
  $ cd ../project
  $ git clone --bare ../temp-project .bare
  $ echo "gitdir: ./.bare" > .git
  $ git config remote.origin.fetch "+refs/heads/*:refs/remotes/origin/*"
  $ git worktree add feature-branch
```
