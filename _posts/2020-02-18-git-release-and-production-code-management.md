---
layout: post
title: Git release and production code management
subtitle:
date: 2020-02-18 00:00:00 +0800
image: https://source.unsplash.com/OHOU-5UVIYQ
bigimg: https://source.unsplash.com/OHOU-5UVIYQ
tag: [Git, Technology, Cheatsheets]
---

Assuming that you have a production branch, and you make release build often. Adding tags to the production branch seems not a very good idea, when you would like to trace at which where is the release produced.

Creating another branch for release may be a better idea. Here is how.

## 0. Create a release branch starting from the root

So that `release` and `production` have the same starting point.

## 1. Merging`production` to `release`

Makes the merge commit represents the checkpoint of the release.

```shell
git checkout release
git merge -e --no-ff production
```

* Then you may edit the merge commit comment for your reference (e.g. "version xx.xx").

## 2. Tie `release` back to `production`

So that `release` can continue tracing `production`.

```shell
git checkout production
git merge -e --no-ff release
```

* Then you may edit the merge commit comment for your reference as well.

## 3. Cherry-pick commits after `production`

If you have some other commits after `production` and would like to put them after `production`, use `cherry-pick`:

```shell
git cherry-pick <commit right before the commits to be cherry-picked>..<the last commit to be cherry-picked>
```