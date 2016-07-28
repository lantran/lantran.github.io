---
layout: post
title: "My new development environment"
excerpt: "Ubuntu GNOME + zshell + tmux + vim + powerline = awesomeness"
categories: articles
tags: [linux, zshell, tmux, vim]
comments: false
share: false
---

I don't know what the reason is but once in a while I will try to pick up some new cool customized themes in Linux. This time, I think I find out the best video (so far) on [Youtube](https://www.youtube.com/watch?v=OGzmC6xeXFE) that I can follow and learn new things. I believe whenever I do this I learn something new in Linux. Actually, I learn a lot everytime.

Let me write it down so that I can remember.


## Ubuntu GNOME

Everyone knows Ubuntu is one the most popular Linux distro with the ease of use and I totally agree about that. So, what the heck is Ubuntu GNOME? It is a Ubuntu using GNOME desktop environment! Historically, Ubuntu uses Unity as its default desktop environment. You can find it from [here.](https://ubuntugnome.org/)

Tweak tool is your friend to customize your dekstop in GNOME! I use [Flattr icons](https://www.gnome-look.org/content/show.php/Flattr?content=161099) and [Paper theme](https://snwh.org/paper). And I actually love them.

## Z Shell

This is the first time ever I try a shell other than bash! Because I didn't actually know what a shell is! People always try to throw jargon words at you. So, what is a Linux shell? 

Computers understand the language of 0's and 1's called binary language.

In early days of computing, instructions are provided using binary language, which is difficult for all of us, to read and write. So in OSes there is a special program called Shell. Shell accepts your instructions or commands in English (mostly) and if it's a valid command, it is passed to kernel.

Shell is a user program or it's environment provided for user interaction. Shell is an command language interpreter that executes commands read from the standard input device (keyboard) or from a file.

Shell is not part of system kernel, but uses the system kernel to execute programs, create files etc.

Note that each shell does the same job, but each understand a different command syntax and provides different built-in functions.

Some common shells are BASH (Bourne-Again SHell), CSH (C SHell), KSH, TCSH...and ZSH (Z SHell). [Here](http://fendrich.se/blog/2012/09/28/no/) is some reasons why you should use zsh instead of bash.

Then what is Terminal (GNOME terminal) (the default one you use in GNOME), Terminator, Guake (used to be my favorite), Konsole? They are terminal emulators! My two cents is they are applications that you download. They are independent with shells. You can use a GNOME terminal running bash or zsh or csh. They are more about the look, shells are more about functionalities.      

## Tmux

Tmux is a terminal emulator that runs inside of other terminals. Actually, tmux is a terminal multiplexer. People love tmux because of so many [reasons.](http://dominik.honnef.co/posts/2010/10/tmux-vs-screen/) It can create mutilple sessions inside a single terminal window or remote terminal session.

## Vim

I am a Vim lover (sorry Emacs fan). It works great with tmux. I haven't customized Vim yet.

Besides that, all the cool kids know how to use [Powerline](https://github.com/powerline/powerline) to customize tmux and vim.  

To conclude the article, I attach here some screeshots of my development environment! 

<figure class="third">
	<a href="/images/my-dev-1.png"><img src="/images/my-dev-1.png" alt="image"></a>
	<a href="/images/my-dev-2.png"><img src="/images/my-dev-2.png" alt="image"></a>
	<a href="/images/my-dev-3.png"><img src="/images/my-dev-3.png" alt="image"></a>
</figure>
