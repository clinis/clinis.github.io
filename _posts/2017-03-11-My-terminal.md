---
layout: post
title: My Bash Prompt
---

![My Terminal](/images/posts/my-terminal.png)

I always wanted to costumize my bash prompt.

Searching the web, I liked [mathiasbynens/dotfiles](https://github.com/mathiasbynens/dotfiles), so I grabbed his [.bash_prompt](https://github.com/mathiasbynens/dotfiles/blob/master/.bash_prompt) file.
![mathiasbynens dotfiles](https://camo.githubusercontent.com/aee78cb21c998db42192ff2bfa6af7018e5bfacf/68747470733a2f2f692e696d6775722e636f6d2f456b45747068432e706e67)

But I don't think the "user at machine" part is needed because I know **I** am using **my computer** (I don't `ssh`that much on my personal machine). So I edited it out.

Another thing I wanted was to more easily recognise diferent comands I have entered on a long terminal session. One of the ways to do that is to print text on the left of the window.


http://nongraphical.com/2013/03/decimal-time-in-your-bash-prompt/

http://stackoverflow.com/questions/16938153/how-to-printf-in-bash-with-multiple-arguments

http://stackoverflow.com/questions/21957568/how-to-show-time-next-to-the-command-line-in-terminal-console

https://www.cyberciti.biz/faq/unix-linux-bash-get-time/



Another *trick* was setting alias for my most used commands.

When I want to quickly edit some projects, I usually open [Atom](https://atom.io) (my text editor) and [GitUp](http://gitup.co/) (a visual Git client). So, I defined an alias `atomit` that opens the current directory both on Atom and on GitUp.


Another *trick* was installing [AutoJump](https://github.com/wting/autojump), after reading ["cd is Wasting Your Time"](https://olivierlacan.com/posts/cd-is-wasting-your-time/).
