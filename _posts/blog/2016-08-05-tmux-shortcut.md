---
layout: post
title: "Tmux shortcuts"
excerpt: "A note to myself"
categories: blog
tags: [Tips and Tricks]
date: 2016-08-05
---

To continue the advanture for my [new dev enviroment]({% post_url 2016-07-25-my-new-dev-env%}), I try to customize the configuration for `tmux`. This blog is a note to myself so that I can look them up in case I forget my configuration. I mainly follow awesome advice from [Ham](http://www.hamvocke.com/blog/a-guide-to-customizing-your-tmux-conf/).

First of all, the common thing you have to do is chaning the **prefix/ binding key** from `C-b` to `C-a` ( `C = Ctrl`, `M = Alt`)

| Action                     |  Shortcut / Command   |
|:---------------------------|:------------|
| split window horizontally  | `C-a`, `|`  |
| split window vertically 	 | `C-a`, `-`  |
| switch to left panel		 | `M-LeftArrow`| 
| switch to right panel		 | `M-RightArrow`| 
| switch to above panel		 | `M-UpArrow`| 
| switch to below panel		 | `M-DownArrow`| 
| close a panel 			 | `C-d` or `exit` |
| create new window 		 | `C-a`, `c` |
| move to previous window    | `C-a`, `p` |
| move to next window 		 | `C-a`, `n` |
| move to arbitrary	windown	 |  `C-a`, `<number>`| 
| detach a session		 | `C-a`, `d` |
| reattach to a session 		 | `tmux attach -t <number>` |
| list all sessions    | `tmux ls` |
| name a new session 		 | `tmux new -s <seesion-name>` |
| rename an existing session 		 | `tmux rename-session -t  0 <new-name>` |
| help 		 | `C-a`, `?` |
