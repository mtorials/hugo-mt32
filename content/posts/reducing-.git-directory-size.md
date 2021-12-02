---
title: "Reducing the size of your .git directory"
date: 2021-12-02
draft: false
description: "A few possible ways to reduce the .git directory size"
tags: ["git", ".git", "repository", "size", "declutter", "clean"]
author: "UniversumGames"
---

# The problem

Most of your probably don't work on a huge project with millions of files and especially not with large files. Most of those "professional" repositories that manage some large files use LFS. A way to integrate large Files with git and reducing the remote repository's size.
But, as I said, mostly "professional" repositories have that and LFS doesn't help with your personal repositories on your own remotes or without any remotes.

Even though Git was originally invented to manage and version control code projects, there exist occasion where you want to version control some not code related, like your college files, like I do. Especially in the time of online curriculum and corona professors might upload beautiful PDFs to visualize and explain a certain topic or upload an explanation video as an MP4 instead of a Zoom conference or an unlisted YouTube Video. Even at a crappy resolution and even worse audio, those files can reach a greater order of magnitude than any normal code repository could. Saving those files, because it's super easy, in an Git repository is no problem in itself, if you tweak your server a little bit and make sure that your commits aren't gigabytes in size, even uploading to a remote is comparable to any other repo.

But there comes a time where the easy way catches up to you. It's when your .git directory reaches, like mine, over 10GB in size (even though the raw data is only about 6GB) and your disk space is running low or you just want to declutter. So you are wondering: "Is there a way to manage this beast and reduce the disk usage?"

# Decluttering your .git directory

<small>All methods are tested by me/us and should have no impact on the version control nor the managed files themself. The list will be updated time to time</small>

-   `git gc` or `git gc --aggressive` (last can take quite some time)
    -   Runs a number of housekeeping tasks within the current repository, such as compressing file revisions (to reduce disk space and increase performance), removing unreachable objects which may have been created from prior invocations of git add, packing refs, pruning reflog, rerere metadata or stale working trees. May also update ancillary indexes such as the commit-graph. - [Git Documentation](https://git-scm.com/docs/git-gc)

### Sources

-   https://git-scm.com/docs/git-gc
-   https://stackoverflow.com/questions/2116778/reduce-git-repository-size
-
