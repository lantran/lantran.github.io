---
layout: post
title: "Houskeeping with Git"
excerpt: "I think me and Git are closer now."
categories: articles
tags: [git]
comments: false
share: false
---

**UPDATE 1 (08/28/2016)**: One of my cowokrer didn't satisfy with what I proposed to clean up remote merged branches. Finally, I created 3 git commands to make him happy:

* **git-open-merged**: display all remote branches which were merged but still open (no RC branches)

{% gist 955235f669e6de1a71dd23615bc402f4 %}

* **git-old-branches**:  display all remote branches (both merged and no-merged) which were created long time ago (2 weeks ago, 3 months ago,...I will explain more about this later.)The default value is `2 months ago`

{% gist d771f7a56c115c6ae83b5c1f463055dd %}

* **git-delete-branches**: delete both local and remote branches from a file. You must supply an input file. If not, the command will do nothing

{% gist 3eafad062519b10109620dd9f1926ec8 %}


The idea is after running `git open-merged` or `git old-branches [<sincetime>]`, we pipe them into a text file, review them manually and then call `git delete-branches [filename]` to delete those branches both on local and remote server.

To install those customized commands, you have to download those files to `/libexec/git-core` in your Git folder.

**NOTICE**: 
<span style="color: red">To make sure you have latest infor in your local **BEFORE** running those commands, run `git remote update --prune` to clean all stale data.</span> 

----

Recently, my boss asked me to clean up the remote branches which were merged but still open for my company project. It sounds interesting but also scary because I don't know what will happend if I accidently delete some branches which other developers still work on. Fortunately, I try to Google and find out exactly what I need. I really like [post](http://railsware.com/blog/2014/08/11/git-housekeeping-tutorial-clean-up-outdated-branches-in-local-and-remote-repositories/).

In this post, I will try to summarize what I learn from that post because I think I understand more about Git. There are 3 kinds of branches you have to care about:

* Your local branches
* References to remote branches (i.e origin/xyz in your local remote, this is the part I don't know)
* Remote branches on the server

### Local branches
First, display all merged branches:

```
git branch --merged
```
Then delete local branches:

```
git branch -d your-local-branch-name
```

If you really know what you are doing, you can do

```
git branch -D your-local-branch-name
```

### References to remote branches

Now where the money is, you usually use
```
git fetch
```
but you miss an important one
```
git fetch -p origin
```
to clean all the stale referencees. A ```fetch``` without an option never deletes any branches which already merged in remote repo, it only adds more and more references to your local origin! Adding ```-p``` option syncs the list of remote branches.

### Remote braches

First, you should do
```
git checkout master
git branch -r --merged
```
to showed all merged braches (connected to HEAD) in your ```local remote``` (doing ```git fetch -p origin``` helps you an accurate list)

Then you can run the following script (only works on a Mac!) to view some infomation before you actually delete a branch

{% gist 3841a531e9dce519dffae0ab0406416e %}

Finally, after reviewing, you can delete a branch you want by

```
git push origin --delete your-branch-name
```

