---
title: GitMigration
permalink: wiki/GitMigration
layout: wiki
---

Migration from CVS to Git
=========================

We are currently testing the benefits of migration to git distributed
version control.

Currently we have a git repository hosted at github.com:

<http://github.com/biopython/biopython/>

This is the official branch, it's synchronized with the main CVS trunk
every hour, so it should be up to date most of the time.

All developers and potential contributors are encouraged to try out this
repository.

Below you can find rudimentary instructions on how to develop biopython
with git.

Prerequisites
-------------

### Installing git

First, you need to have git installed on your computer.

Git (http://git-scm.com/) is now available for all major operating
systems, you can get it

-   Linux: Git is now packaged in all major linux distributions, you
    should find it in your package manager.
-   Mac OS X: <http://code.google.com/p/git-osx-installer/>
-   Windows: There are two options:
    \[\[MsysGit\][1](http://code.google.com/p/msysgit/)\] or running the
    compiled git under Cygwin. You can find more information in \[\[this
    github
    guide\][2](http://github.com/guides/using-git-and-github-for-the-windows-for-newbies)\]

Getting a github account (Optional)
-----------------------------------

Once you have git installed on your machine, you can get the code and
start developing, However, since the code is hosted at github, you can
use more features if you sign up for github account. This is completely
optional but if you do sign up all other developers will be able to see
(and review) the changes you have made.

If you dan't already have a github account:

-   create one here <http://github.com/plans> (the free plan is
    absolutely enough)
-   Upload an ssh public key by clicking on 'account' after having
    logged in

Getting the source
------------------

- go to the biopython repo:

[`http://github.com/biopython/biopython/tree/master`](http://github.com/biopython/biopython/tree/master)

and you will see a button named 'Fork': click on it. It will create a
fork of the official biopython repository your personal account. Here
the word 'fork' is not used in the common way it is, but just to
indicate that you are going to work on a modified version of the
official code, and it's not even a git command.

- now, install git on your computer, and execute the following commands:
$: git clone git@github.com:<your username>/biopython.git $: git remote
add official\_dist <git://github.com/biopython/biopython.git>

With the first command, you will download a copy of the repository on
your local computer, which will be the one you will modify (technically,
you are creating a new branch on your computer). With the second
command, you are adding a reference to the official biopython
repository, so in the future you will be able to easily import the
official code and compare it with yours.

Here it is an explanation on these two commands:
<http://github.com/guides/keeping-a-git-fork-in-sync-with-the-forked-repo>