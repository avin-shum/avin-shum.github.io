---
layout: post
title: Tips to Ignore Files Commited
subtitle:
date: 2021-01-18 00:00:00 +0800
image: https://source.unsplash.com/OHOU-5UVIYQ
bigimg: https://source.unsplash.com/OHOU-5UVIYQ
tag: [Git, Technology]
---

It has been a YEAR to add one more Git related article! I believe that means the previous tips are so good that doesn't need much update.

Sometimes we need to put some default configuration to a project, but everybody may have their own version due to their own environment, so that Git regards this as a change. However, such differences should not be pushed because one should not treat their own configuration as the standard of the others. We need a way to tell our local Git that the change should be left locally.

If you search from the web, you would probably know the `assume-unchanged` flag, but the command only accept a file. Sometimes we need to target the whole folder.

## 1. Tell Git not to track a folder

The solution is based on Stackoverflow: https://stackoverflow.com/questions/16346535/recursive-git-update-index-assume-unchanged

```shell
git ls-files -z myFolderToIgnore/ | xargs -0 git update-index --assume-unchanged
```

_(22 Feb 2021 Update)_
{: .red}

Note:

- To undo `assume-unchanged`, change it to `no-assume-unchanged` instead.
- `assume-unchanged` may not be the best solution. You may consider using `skip-worktree` instead.
  - See [https://stackoverflow.com/questions/13630849/git-difference-between-assume-unchanged-and-skip-worktree](https://stackoverflow.com/questions/13630849/git-difference-between-assume-unchanged-and-skip-worktree)
- For those files which you do not want it to be overwritten by actions like `checkout`, consider [Private Branch Pattern](https://avin-shum.github.io/2021-02-08-private-branch-pattern)
