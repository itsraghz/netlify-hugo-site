---
title: "Reset Sudo Password Ubuntu 20.04 LTS in WLS"
date: 2021-06-09T22:32:44+05:30
draft: false
tags: ["Technical", "WLS", "Ubuntu", "Troubleshooting"]
toc: true
---

# Reset Sudo Password Ubuntu 20.0 LTS in WLS

This blog post explains the steps needed to reset the `sudo` password for the `Ubuntu 20.04 LTS` version 
in the *WLS* (Windows for Linux SubSystem) - *Windows 10*. 

<!--more-->

## WLS Vs Typical Linux Distros 

Once you configure Ubuntu LTS in the WLS, it does not ask for the password whenever you invoke the App in the Windows OS. As the Windows for Linux SubSystem, it automatically saves the username and password credentials in the cache. With which it automatically picks up the user and logs him/her in whenever you invoke the App. It is unlike the typical Ubuntu OS (or any other linux distro), where you would be asked for the password whenever you login. 

## Issue

Post logging in, if you had to do with any of the administrative commands, you may need to prefix it with `sudo` which will ask for the password once to ensure that you are the authenticated user and you are indeed clear on what you do. If you have forgotten the login password, you can't succeed in getting into the `sudo` mode.  

## Resolution - Easy way

A simple way to resolve the issue is to reset the password via `Command Line`. 

1. Open the Command Prompt
2. Type the command `ubuntu config --default-user root` to reset the user to login as root in the linux distro
3. Invoke the Linux distro - `ubuntu`.
4. You would be logged in with the *root* user now - as per the config we made in step #2. 
5. Verify the current user with the command `whoami` - to be very sure of it. 
6. Change the password for the user of your choice by giving `passwd <user>`
7. Enter the password of your choice to the user you wish to login. 
8. Enter the password again for confirmation. 
9. Exit the Linux distro by pressing `Ctrl+C` or `exit'.
10. Again, set the default user as `ubuntu config --default-user <user>`.
11. Enter the Ubuntu exe for the distro in the same terminal - `ubuntu`.
12. You would be logged in with your `user` now on the linux distro. 
13. Verify the password by issuing any command prefixed with `sudo` such as `sudo ls`. 
14. Enter the password you just created. 
15. A successful output confirms that your password reset is successful :) 

> Rememmber: You may need to replace the executable file with the right file name, in my case it is *Ubuntu2004.exe* instead of just *ubuntu* as that is how I have named it while installing it in my System. 

### Troubleshooting - How to find out the Linux distro exe file name?

You can run the distro first, and then to go the `Task Manager`, drill down to the `Ubuntu 20.04 LTS` app, right click on the correct executable file (.exe) and click on `Properties` to get to see the file name. 
   
> `Ubuntu2004.exe` is located in `C:\Program Files\WindowsApps\CanonicalGroupLimited.Ubuntu20.04onWindows_2004.2021.222.0_x64__79rhkp1fndgsc`

## Command Output

The following are the sequence of command output in the *Windows Command Prompt*. 

### Attempting to get the `ubuntu` but it was unsuccessful

```sh
Microsoft Windows [Version 10.0.19042.985]
(c) Microsoft Corporation. All rights reserved.

C:\Users\Raghavan Muthu>ubuntu
'ubuntu' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\Raghavan Muthu>ubuntu config --default-user root
'ubuntu' is not recognized as an internal or external command,
operable program or batch file.
```

### Attempt to invoke the `ubuntu` executable with the correct exe file name

```sh
C:\Users\Raghavan Muthu>ubuntu2004
raghs@Raghs-LegionY540-TPIN:~$ exit
logout
```

### Back to Windows Command Prompt, reset the default user to `root`

```sh
C:\Users\Raghavan Muthu>ubuntu2004 config --default-user root

C:\Users\Raghavan Muthu>
```

### Invoke the Linux Distro, and verify the User

```sh
C:\Users\Raghavan Muthu>ubuntu2004
Welcome to Ubuntu 20.04.1 LTS (GNU/Linux 4.4.0-19041-Microsoft x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Wed Jun  9 22:29:13 IST 2021

  System load:            0.52
  Usage of /home:         unknown
  Memory usage:           85%
  Swap usage:             1%
  Processes:              9
  Users logged in:        0
  IPv4 address for eth2:  192.168.85.1
  IPv4 address for eth3:  192.168.244.1
  IPv4 address for wifi0: 192.168.1.11
  IPv6 address for wifi0: 2401:4900:1f2a:39c2:1df7:1e21:2f36:49bd
  IPv6 address for wifi0: 2401:4900:1f2a:39c2:b916:7d3f:44e9:144

69 updates can be installed immediately.
18 of these updates are security updates.
To see these additional updates run: apt list --upgradable


The list of available updates is more than a week old.
To check for new updates run: sudo apt update


This message is shown once once a day. To disable it please create the
/root/.hushlogin file.
root@Raghs-LegionY540-TPIN:~#
```

### Verify the current user

```sh
root@Raghs-LegionY540-TPIN:~# whoami
root
```

### Reset the password to the user of your choice 

```sh
root@Raghs-LegionY540-TPIN:~# passwd raghs
New password:
Retype new password:
passwd: password updated successfully
```

### Exit and come back to Windows Command Prompt

```sh
root@Raghs-LegionY540-TPIN:~# exit
logout

C:\Users\Raghavan Muthu>
```

### Reset the default user back to the user of your choice to the linux distro

```sh
C:\Users\Raghavan Muthu>ubuntu2004 config --default-user raghs

C:\Users\Raghavan Muthu>
```

### Invoke the linux distro now to see it logs in with the right user of your choice

```sh
C:\Users\Raghavan Muthu>ubuntu2004
raghs@Raghs-LegionY540-TPIN:~$ 
```

### Verify the password change with any command prefixed with `sudo`

```sh
raghs@Raghs-LegionY540-TPIN:~$ sudo ls
[sudo] password for raghs:
prfsnl  study  userCreds.txt
raghs@Raghs-LegionY540-TPIN:~$
```

## Resolution - Alternate way 

You can go to the *Ubuntu 20.04 LTS* App in the Windows Programs, uninstall it and reinstall it from the *Windows Store*. 

> Please note that you may lose the data if any, you had it in the Linux distro. Be mindful of the fact. 


Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
09 Jun 2021 | Wed | 22 56 PM IST
