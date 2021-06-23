---
title: "VSCode Split Terminal"
date: 2021-06-23T20:50:51+05:30
draft: false
tags:
  - Technical
  - Tools
toc: true
author: Raghs
---

`Code` or `VSCode` or `Visual Studio Code` editor (should we better call it as an IDE? :)) has got a nice facility to boost our producvity especially when we work on the applications that demand a constant attention with the terminal. Example, Angular, Node applications or even with the static site generators like `Hugo` etc., 

<!--more-->

# New Terminal - Folder Selection

VS Code has got two icons on the Terminal window. On the top right, we get a "+" icon to add a new terminal, and depends on the folders added in the workspace it will ask you to choose a folder in which the terminal to be opened - yet another cool feature :) yeay! :)

<img src="https://raghsonline.com/tools/vscode/vscode-new-terminal-folder-selection.JPG" />

# Split Option in the existing terminal 

On an already opened terminal, when you hover the mouse over the terminal name, you get two icons in the small window as follows. 

* Window - To split the terminal
* Trash - To close/exit the terminal

Clicking on the `window` icon, the terminal is split on the horizontal side allowing you to operate in parallel on the two terminals easily, with just a mouse click for toggling. Earlier we had to manually select the terminals in the dropdwon appearing on the top and then resume the work. 

*Image* - The `+` icon 

<img src="https://raghsonline.com/tools/vscode/vscode-plus-icon-terminal.JPG" />

*Image* - The `split terminal` menu item 

<img src="https://raghsonline.com/tools/vscode/vscode-split-terminal-menu-item.JPG" />

*Image* - The icons of terminals after split

<img src="https://raghsonline.com/tools/vscode/vscode-terminals-status-after-split.JPG" />

*Icon Status* 

* First `cmd` - Normal Terminal Window (Command Prompt)
* Second `cmd` - split into two, where each of them are of type `Command Prompt` &rarr; `C:\>` indication

This is certainly a productivity booster I would say!

Try this and enjoy. 

## My Usage - Hugo

I use this for the static site generator `Hugo` where one window is used for creating a new posts - with `hugo new` binary, and the other window is to control the `hugo server` OR `hugo server -D` (for the drafts). As long as I actively work on Hugo, I have felt the need for these two windows to be operated in parallel. 

*Image* : The `split terminal` in effect 

<img src="https://raghsonline.com/tools/vscode/vscode-split-terminal-22Jun2021.JPG"/>

> Note: Of course, you can open as many windows as you want by clicking on the `window` icon. But I don't see any practical reasons to open more than 3 terminals at a time!

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
23 Jun 2021 | Wed | 20:50:51 PM IST
