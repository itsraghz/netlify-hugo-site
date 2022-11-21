---
title: "Bash Utility to Rename all files in a Folder"
date: 2022-11-21T23:42:37+05:30
draft: flse
tags:
  - Technical
  - Linux
  - Scripting
  - Utility
toc: true
author: Raghs
---

# Bash Utility to rename all the Files in a Folder

I wanted to rename all the files in a folder - from the extension `.jpeg` to `.jpg` and was looking to automate as there were roughly more than 20 files :) 

<!--more-->

The below script will help you rename all the files with an extension `.jpeg` to `.jpg` in the linux flavored terminal.

## Bash Script 

```bash
#!/bin/bash

for file in *.jpeg; do
    mv "$file" "$(basename "$file" .jpeg).jpg"
done
```

It is a simple for loop that is self explanatory - where it picks up all the files matching with the desired file extension (`.jpeg`). Inside the loop, it moves the file extension from `.jpeg` to `.jpg`. 

## Command Execution and Output

Verify the file extensions before executing the Bash script. 

```bash
RAGHS_BASH: ls
 00.jpeg   05.jpeg   10.jpeg   15.jpeg                   20_Receipt.jpeg
 01.jpeg   06.jpeg   11.jpeg   16.jpeg                   21.jpeg
 02.jpeg   07.jpeg   12.jpeg   17.jpeg                   22_RaghsPrsnlPHPExpenses_Summary.jpeg
 03.jpeg   08.jpeg   13.jpeg   18_Payment_Success.jpeg   changeExtn.sh
 04.jpeg   09.jpeg   14.jpeg   19.jpeg           
RAGHS_BASH:
```

Now verify the file contents once. 

```bash
RAGHS_BASH : bat changeExtn.sh
───────┬────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
       │ File: changeExtn.sh
───────┼────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1   │ #!/bin/bash
   2   │
   3   │ for file in *.jpeg; do
   4   │     mv "$file" "$(basename "$file" .jpeg).jpg"
   5   │ done
   6   │
───────┴────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
```
Execute the script and verify the file contents. 

```bash
RAGHS_BASH : ./changeExtn.sh
RAGHS_BASH : ls
 00.jpg   05.jpg   10.jpg   15.jpg                   20_Receipt.jpg
 01.jpg   06.jpg   11.jpg   16.jpg                   21.jpg
 02.jpg   07.jpg   12.jpg   17.jpg                   22_RaghsPrsnlPHPExpenses_Summary.jpg
 03.jpg   08.jpg   13.jpg   18_Payment_Success.jpg   changeExtn.sh
 04.jpg   09.jpg   14.jpg   19.jpg                  
RAGHS_BASH :
```

It only filtered all the files ending with the `.jpeg` extension, leaving the other files untouchedd - for example, `changeExtn.sh` - this file, and renamed all the matching files as desired. 

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
21 Nov 2022 | Mon | 23:42:37 PM IST
