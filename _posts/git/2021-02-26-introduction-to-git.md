---
layout: post
title: Introduction to Git
subtitle:
date: 2021-02-26 00:00:00 +0800
image: https://source.unsplash.com/842ofHC6MaI
bigimg: https://source.unsplash.com/842ofHC6MaI
tag: [Git, Technology]
---

This is part of Git Tutorial Series.

[Table of Content](https://avin-shum.github.io/2021-02-26-git-tutorial-series/)

## What is Git?

Git is a source control application. It is used to keep track of the source code change, and also facilitate source code distribution. See [https://en.wikipedia.org/wiki/Git](https://en.wikipedia.org/wiki/Git)

It is a **distributed version control** system, which means,

- You keep the **whole** change history locally
- You can retrieve any version in the tree without accessing any server, and it is fast because the data are stored locally
- You can copy the **whole** change history to another server easily

**_Note: It is a bit complicated for Git LFS. See [https://www.atlassian.com/git/tutorials/git-lfs](https://www.atlassian.com/git/tutorials/git-lfs)_**

I use Git not just because it is common among developers, but also it is so easy to manage the change history using Git.

Let's get your enviornment ready and start working with Git.

## Environment Setup (Windows)

This section we will go through some software to use Git and their installation procedure. We are going to install,

- Git
- VSCode
- Git Graph

Even though there may be some Git tools to help you to do Git operations, it is highly recommended to learn the command line interface, which to give you the highest flexibility to manipulate the repository.

The installation guide below is Windows based and focuses on portable installation, because it can be very complicated to use installers in Windows system, which often requires admin right.

### Git

Of course you need to install Git to use Git.

#### Installation

1. Download the portable version here: [https://git-scm.com/download/win](https://git-scm.com/download/win)
2. Unzip to a folder for git. e.g. `C:\application\git`
3. Put the path to Git's `\bin` into the `PATH` environment variable
4. Type `git` in command line console to check whether it works

#### Configuration

1. Run `git config --global core.editor "code -w"` to use VSCode (mentioned below) as the editor for Git
2. If you are behind corporate proxy, you may need to set up proxy like,
   ```
   [http]
     proxy = "<proxy server:port>"
   ```
3. If you need to access Git server with self-signed certificate or even no certificate at all, you may need to set like,
   ```
   [http <server path>]
     sslVerify = false
   ```

### Visual Studio Code (VSCode) and Git Graph

VSCode is a very powerful text editor. It support Git (with some basic functions) and Terminal inside, while Git Graph is a very powerful VSCode extension. With both of them, you can manage your code with Git easily.

#### Installation

1. Download VSCode here: [https://code.visualstudio.com/docs/editor/portable](https://code.visualstudio.com/docs/editor/portable)
2. Unzip to a folder for VSCode. e.g. `C:\application\vscode`
3. Put the path to into the `PATH` environment variable
4. Type `code` in command line console to check whether it works
5. Go to `Extension` UI by `View > Extension` or `Ctrl+Shift+X
6. Search for `Git Graph`
7. Click `Install`

---

Now you are good to go for Git projects.
