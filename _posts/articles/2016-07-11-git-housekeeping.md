---
layout: post
title: "Houskeeping with Git"
excerpt: "I think me and Git are closer now."
categories: articles
tags: [git]
comments: false
share: false
---

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

```bash
for branch in `git branch -r --merged | grep -v HEAD`; do echo -e `git show --format="%ci %cr %an" $branch | head -n 1` \\t$branch; done | sort -r
```
Finally, after reviewing, you can delete a branch you want by

```
git push origin --delete your-branch-name
```


