---
title: "How to Use the BC Tool"
date: 2021-09-29T23:20:37+05:30
draft: false
tags:
  - Linux
  - Tools
toc: true
author: Raghs
---

We will see how to use the `bc` tool (Basic Calculator) in this post.

<!--more-->

# BC tool

`bc` is a standard utiilty in most of the \*nix Operating Systems. It stands for [*Basic Calculator*. ](https://www.gnu.org/software/bc/manual/html_mono/bc.html)

## Invoke the utility 

Just type `bc` in the terminal/shell to bring up the calculator. 

```sh
raghs@Raghs-LegionY540-TPIN:/mnt/c/WINDOWS/System32$ bc
bc 1.07.1
Copyright 1991-1994, 1997, 1998, 2000, 2004, 2006, 2008, 2012-2017 Free Software Foundation, Inc.
This is free software with ABSOLUTELY NO WARRANTY.
For details type `warranty'.

```

> The utility waits for your input without prompt, unlike other interpreters. You can directly type your inputs. 

## Usage 

We can type the numbers and the operators like what we do in the typical calculator, for the `bc` utility to calculate the result of the expression and print it in the next line. 

Example:  If you simply type a number and press the `Enter` key, the `bc` tool will return the same number.

```sh
1
1
```

Example 2: Do a simple math. 

```sh
1 + 1 
2
```

Nothing special here. The expression was evaluated and the result was printed on the next line. 

> The spaces around the operator is just for the convenience of the human readers, and it does not have make any difference. 

## Caution 

Please be aware of the fact it is a *basic* calculator, and hence the operands should _NOT_ ne specified with any separators, in such case, it will throw an error. 

```sh 
raghs@Raghs-LegionY540-TPIN:~$ bc
bc 1.07.1
Copyright 1991-1994, 1997, 1998, 2000, 2004, 2006, 2008, 2012-2017 Free Software Foundation, Inc.
This is free software with ABSOLUTELY NO WARRANTY.
For details type `warranty'.
1 + 1
2
last + 1000
1002
last + 1,000
(standard_in) 3: syntax error
```

From the above example, it is clearly evident that the 2nd expression works well when the 2nd operand is specified without any separator (`1000`), whereas the 3rd expression failed as the `operand` was supplied with a *separator* (`1,000`). 

## Exit from the tool 

To exit from the `bc` tool, you simply type the `quit` and press `Enter` key to come out of the tool in the terminal. 

```sh 
1 + 1
2
quit
raghs@Raghs-LegionY540-TPIN:/mnt/c/WINDOWS/System32$ 
```
> You can press `Ctrl+C` similar to other tools but this `bc` tool will prompt with you the right hint to use `quit`. 

```sh 
raghs@Raghs-LegionY540-TPIN:~$ bc
bc 1.07.1
Copyright 1991-1994, 1997, 1998, 2000, 2004, 2006, 2008, 2012-2017 Free Software Foundation, Inc.
This is free software with ABSOLUTELY NO WARRANTY.
For details type `warranty'.
^C
(interrupt) use quit to exit.
quit
raghs@Raghs-LegionY540-TPIN:~$
```

## See Also 

You can also read this post &rarr; [How to use the previous result in bc tool](./how-to-use-previous-result-in-bc-tool.md)

## References

* [GNU Reference](https://www.gnu.org/software/bc/manual/html_mono/bc.html)
  
Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
29 Sep 2021 | Wed | 23:20:37 PM IST
