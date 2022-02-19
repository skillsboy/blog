---
title: "Push Folders Content to Another Git Branch"
date: 2022-02-19T13:18:07Z
draft: false
---

Here I'm going to show you how to push all the content of a folder from the main branch to another branch called gh-pages.  
Usefull for deploying specific files and not the whole project on github pages.

![Git Branch final result](/images/push-folders-content-to-another-git-branch-final-result.png#center)

### Commands

These commands are all run from the main branch.

**1. Add**

```bash
git add .
```

**2. Commit**

```bash
git commit -m "commit message"
```

**3. Subtree**

```bash
git subtree push -P public origin gh-pages
```

* ``-P`` (prefix) flag is the folders content that will be pushed, in this case the ``public``.
* ``origin`` will be the main branch where the ``public`` folder is.
* ``gh-pages`` is the branch where the ``public`` folders contents will be pushed to.

Basically this will push everything inside the ``public`` folder from the main branch (origin) to the ``gh-pages`` branch.