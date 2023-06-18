---
title: "How to Switch the Default Browser in Mac OS X"
date: 2023-06-18T18:26:09+05:30
draft: false
tags:
  - Technical
  - MacOS
  - Utility
toc: true
author: Raghs
---

# How to Switch the Default Browsers in Mac OS X

I had to switch the default browsers in my Macbook Pro, for a better organized work - as I usually work in Safari Browser for all my official tasks, and Firefox for my personal works.

<!--more-->

I knew that the switching of the default browser is typically a manual work, where you should specify the browser of your choice in the list available in the "Default web browser" section under the "Desktop & Dock" menu item in the Settings Window of the Mac OS.

*Mac OS X - Settings Window - Desktop & Dock Menu*

We get the default browser what is set.

<img src="https://raghsonline.com/technical/macosx-default-browser/01_AppleMacOSX-DesktopBrowserSettings.png" alt="Apple Mac OS X - Desktop Browser Settings.png">

*Mac OS X - Settings Window - List of Browsers*

<img src="https://raghsonline.com/technical/macosx-default-browser/02_AppleMacOSX-BrowserList.png" alt="Apple Mac OS X - Browser List.png">

## `desktopbrowser` utility 

### Install the utility

We have a new utility called `desktopbrowser` which can be installed with the help of the `brew` command as follows.

```sh
brew install desktopbrowser
```

Once it gets successfully installed, you can verify the installed location through the `whereis` and `which` commands, which will tell you where the binary is located in the System if there is match.

```sh
➜  macosx-default-browser git:(master) ✗ whereis defaultbrowser
defaultbrowser: /opt/homebrew/bin/defaultbrowser
➜  macosx-default-browser git:(master) ✗ which defaultbrowser
/opt/homebrew/bin/defaultbrowser
➜  macosx-default-browser git:(master) ✗ 
```

### Invoke the utility

Executing or invoking the utility is very straightforward and simple. 

*Syntax*

```sh
defaultbrowser <nameOfBrowser>
```
*Example* To invoke the *Firefox* browser, you can specify.

```sh
defaultbrowser firefox
```
> *Note*: We can use `chrome`, `safari` etc., to supply as an argument to invoke the browser.

*DesktopBrowser Utility - Command with Argument*

I made a custom shell script with a meaningful name to keep the arguments saved.

<img src="https://raghsonline.com/technical/macosx-default-browser/03_AppleMacOSX-DefaultBrowser-Switch.png" alt="Apple Mac OS X -Default Browser - Switch">

A very nice thing is that it prompts the user to confirm the switch of the default browser, and it will get a quick confimation on the dialog box. 

However, no matter what your choice is, there is no further message to the user. It is silently registered. 

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
18 Jun 2023 | Sun | 18:26:09 PM IST