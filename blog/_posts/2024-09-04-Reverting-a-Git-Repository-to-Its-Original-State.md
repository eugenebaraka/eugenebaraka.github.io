---
layout: post
type: post
title: "Reverting a Git Repository to Its Original State"
date: 2024-09-04
author: EUGENE BARAKA
published: true
tags:
  - dev
header-img: 
description: "Resetting your git repository can be a risky move especially when the stakes are high. I got an opportunity to do it when they are low."
---

<span class="firstcharacter">I</span>'ve been _trying_ to blog consistently for a while now, and as I _hopefully_ declared [here](https://eugenebaraka.github.io/blog/2024/08/14/Another-Shot-at-Blogging.html), I’m back at it full steam (fingers crossed). But when I revisited my old blog—built two years ago with the [Minima Jekyll theme](https://github.com/jekyll/minima)—let’s just say I wasn't feeling the vibe anymore. That’s when the big question hit me: Can I revert the whole thing to its original, pristine state before any commits were made? Sure, I could’ve just re-cloned the Minima theme and started over, but where’s the fun in that when you can experiment, right?
## Why Reset a Repository?

Besides my curiosity and experimentation that led to this blog post, there are several reasons you might need to reset your Git repository: 
- You are the maintainer of a project but do not have permissions to creating a new repository. In this case, resetting the existing repo to its original state might be the only practical solution when you need to start fresh without setting up a new repo.
- You made a series of changes that didn’t work out. 
- You want to start fresh but keep a backup of your current progress.

No matter the reason, Git provides powerful commands to manage resets.

Here's a step-by-step guide to safely reset your repository while keeping your current work accessible for later reference in case you change your mind (again).
### Step 1: Stash or Backup Your Work (Optional)

If you want to save your current progress before resetting, it’s good practice to stash or create a new branch. This ensures that no work is lost if you need it later.

To stash changes:

```bash
git stash
```

Alternatively, you can create a backup branch:

```bash
git checkout -b backup-branch
```

### Step 2: Reset to the State Before the First Commit

If you want to completely reset the repository to the state before any commits were made (like starting fresh with a clean slate), use the following:


```bash
git update-ref -d HEAD
```

This deletes the reference to the current branch, allowing you to start over without any commits. All your files will remain in the working directory, but Git will treat them as untracked files.

### Step 3: Verify the Reset

Finally, you can confirm that the reset was successful by running:

```bash
git status
```

If you reset to the state before the first commit, the status should show all files as untracked, as if you're starting a new repository.


In my case, I also wanted to remove these files, so I removed them using the `git clean` command:

```bash
rm -rf .git  # removes all git history, including uncommitted changes
git clean -fd # cleans untracked files(-f) and directories (-d)
```

## Resetting the repository to the last commit 

There are cases where you might not need to reset all the changes made to the repository, rather just the reset it to its latest commit. In this case, run:

```bash
git reset --hard HEAD
```

This command will reset:

- **Working directory** (all modified files)
- **Staging area**
- **Current branch** to match the latest commit

Your project will revert to the state it was in at the last commit.

As always, if you're not sure about fully resetting your repository, stash or branch your work to avoid accidentally losing valuable changes!

