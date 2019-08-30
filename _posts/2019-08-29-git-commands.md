---
layout: post
title: Git commands I used to use
subtitle:
date: 2019-08-29 00:00:00 +0800
image:
bigimg: https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Git-logo.svg/512px-Git-logo.svg.png
bigimgdesc: Git Logo by Jason Long is licensed under the Creative Commons Attribution 3.0 Unported License.
excerpt: Tools for Git are great. I use VSCode with Git Graph and GitLens...
tag: [Git, Technology, Cheatsheets]
---

Tools for Git are great and help developers a lot. I use [VSCode](https://code.visualstudio.com/) with [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph) and [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) to do manage my Git projects.

They are not perfect, however. I still need to use commands directly very often. These are Git commands I used to use.

As I learn Git commands from time to time, this list here will be updated often.

## 0. Assumption

- Remote repository is called `origin`

## 1. Configuration

### Set VSCode as default editor

Use of editor is quite important for Git, however the default Git editor is not so friendly to Windows users like me. There are some good editors you can use like [Notepad++](https://notepad-plus-plus.org/) and [Sublime text](https://www.sublimetext.com/). Nevertheless, I eventually choose VSCode because VSCode is also the tool I use for Git projects.

Here is the command, given that you can call VSCode directly by running `code` in command line:

```shell
git config --global core.editor "code -w"
```

### Use editor to edit global config

```shell
git config --global -e
```

## 2. Branch

### Move a branch to target commit

_Note:_ If the branch name does not exist, it creates a new branch to the target instead.

```shell
git branch -f <branch-name> <target>
```

### Delete remote branch

```shell
git push origin --delete <branch-name>
```

### Push to a remote branch with a different branch name

```shell
git push origin <local-branch>:<remote-branch>
```

## 3. Rebase

### Rebase while keeping merge hierarchy

Usually I add `-i` flag as well.

```shell
git rebase -r <target>
```

## 4. Merge

### With message and keep hierarchy

Merge with message to be edited by the edior, and make sure that there will be a merge path hierarchy

```shell
git merge -e --no-ff <target>
```

## 5. Stash

### Stash with new files

Sometimes you just forgot to stash with new files as well.

```shell
git stash -u
```
