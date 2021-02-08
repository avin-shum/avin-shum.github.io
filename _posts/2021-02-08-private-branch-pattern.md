---
layout: post
title: Private Branch Pattern
subtitle:
date: 2021-02-08 00:00:00 +0800
image: https://source.unsplash.com/842ofHC6MaI
bigimg: https://source.unsplash.com/842ofHC6MaI
tag: [Git, Technology]
---

My [previous Git article](https://avin-shum.github.io/2021-01-18-tips-to-ignore-files-commited/) may not be a perfect solution to handle local configuration problem. Especially if you checkout / reset often, chances are your local configuration may be overwritten, or you cannot checkout / reset because Git knows you have indeeed changed something. 

## Private Branch Pattern

You may try **Private Branch Pattern** instead. See the details below.

### 0. Set Up

You are now working on your **master** branch. You would like to add your local configuration. So you create a branch (say, **local-config**) for it.

> <code>git checkout -b <i>local-config</i></code>

Then you commit your configuration and also create your **feature** branch at **local-config** branch for your new changes (by `git checkout -b`).

The tree now looks like:

<pre>
M (master)
 \
  L (<span style="color: blue">HEAD -> feature</span>, local-config)
</pre>

### 1. Make changes

Then you make changes and commit them. The tree now looks like:

<pre>
M (master)
 \
  L (local-config)
   \
    A---B---C (<span style="color: blue">HEAD -> feature</span>)
</pre>

### 2. Rebase to **master**

Now you want to add your change to **master** branch, but you realized that your changes are based on your local config ***(L)***.

So you would like to move your changes to **master** branch but leaving **local-config** behind. You may run:

> <code>git rebase --onto <i>master</i> <i>local-config</i></code>

Then the tree becomes:

<pre>
M (master)
|\
| A'---B'---C' (<span style="color: blue">HEAD -> feature</span>)
 \
  L (local-config)
</pre>

### 3. Wrap things up

Now you can set **master** to **feature**, or `merge` the branches, so that your **master** branch has the feature changes with no local changes.

Then you can tidy up the 3 branches (e.g. `rebase` **local-config** to **master** branch) to continue your development.

---

***Reference***:
* [http://blog.ericwoodruff.me/2013/02/git-private-branch-pattern.html](http://blog.ericwoodruff.me/2013/02/git-private-branch-pattern.html)
* [https://womanonrails.com/git-rebase-onto](https://womanonrails.com/git-rebase-onto)
