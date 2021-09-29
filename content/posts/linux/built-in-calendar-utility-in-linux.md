---
title: "Built in Calendar Utility in Linux"
date: 2021-09-29T23:40:41+05:30
draft: false
tags:
  - Linux
  - Tools
toc: true
author: Raghs
---

We will see how to use the built in Calendar utility in the Linux based Operating Systems.

<!--more-->

# Built in Utility 

Like the [`bc`](./how-to-use-the-bc-tool.md) tool, we have a built in Calendar utility in the `*nix Operating Systems. This

## Usage 

Like any other tool, you would use `cal` to invoke it in the `shell` or the `terminal`. In its simple usage, it shows the present month. 

*Syntax* : `cal`.

```sh
raghs@Raghs-LegionY540-TPIN:/mnt/c/WINDOWS/System32$ cal
   September 2021
Su Mo Tu We Th Fr Sa
          1  2  3  4
 5  6  7  8  9 10 11
12 13 14 15 16 17 18
19 20 21 22 23 24 25
26 27 28 29 30

raghs@Raghs-LegionY540-TPIN:/mnt/c/WINDOWS/System32$
```
> In an actual terminal output, the current date is highlighted! You can see it in the image below. 

### Screenshot 

<img src="https://www.raghsonline.com/tools/linux/cal/current-month-today-highlighted.jpg" alt="Present day highlighted in the current month view">

## How to get a custom date in the terminal 

You can pass an additional parameter for the month along with the `cal` as follows in the terminal. 

*Syntax* : `cal <Month> <Year>`.

> Remember, the year must be supplied after the month, otherwise the output may be unpredicted. 

In the following examples, we get the calendars in the following order. 

* Sep 2021 - Current Month
* Aug 2021 - Previous Month 
* Oct 2021 - Next Month 
  
```sh
raghs@Raghs-LegionY540-TPIN:/mnt/c/WINDOWS/System32$ cal 9 2021
   September 2021
Su Mo Tu We Th Fr Sa
          1  2  3  4
 5  6  7  8  9 10 11
12 13 14 15 16 17 18
19 20 21 22 23 24 25
26 27 28 29 30

raghs@Raghs-LegionY540-TPIN:/mnt/c/WINDOWS/System32$ cal 8 2021
    August 2021
Su Mo Tu We Th Fr Sa
 1  2  3  4  5  6  7
 8  9 10 11 12 13 14
15 16 17 18 19 20 21
22 23 24 25 26 27 28
29 30 31

raghs@Raghs-LegionY540-TPIN:/mnt/c/WINDOWS/System32$ cal 10 2021
    October 2021
Su Mo Tu We Th Fr Sa
                1  2
 3  4  5  6  7  8  9
10 11 12 13 14 15 16
17 18 19 20 21 22 23
24 25 26 27 28 29 30
31
raghs@Raghs-LegionY540-TPIN:/mnt/c/WINDOWS/System32$
```
> Again, here as well, in the actual terminal output, the current date is highlighted! You can see it in the image below. 

### Screenshot 

<img src="https://www.raghsonline.com/tools/linux/cal/custom-month-year-today-highlighted.jpg" alt="Custom Month of the year, with the present day highlighted">

## How to get a calendar view for an entire year 

You can just enter an additional input as a parameter to the `cal` utility in the terminal to get the calendar of that year. 

Example: `cal 2021` gets the calendar view of the entire year 2021 based on the locale set in the machine. 

*Syntax* : `cal <Year>`.

```sh
raghs@Raghs-LegionY540-TPIN:/mnt/c/WINDOWS/System32$ cal 2021
                            2021
      January               February               March
Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa
                1  2      1  2  3  4  5  6      1  2  3  4  5  6
 3  4  5  6  7  8  9   7  8  9 10 11 12 13   7  8  9 10 11 12 13
10 11 12 13 14 15 16  14 15 16 17 18 19 20  14 15 16 17 18 19 20
17 18 19 20 21 22 23  21 22 23 24 25 26 27  21 22 23 24 25 26 27
24 25 26 27 28 29 30  28                    28 29 30 31
31

       April                  May                   June
Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa
             1  2  3                     1         1  2  3  4  5
 4  5  6  7  8  9 10   2  3  4  5  6  7  8   6  7  8  9 10 11 12
11 12 13 14 15 16 17   9 10 11 12 13 14 15  13 14 15 16 17 18 19
18 19 20 21 22 23 24  16 17 18 19 20 21 22  20 21 22 23 24 25 26
25 26 27 28 29 30     23 24 25 26 27 28 29  27 28 29 30
                      30 31

        July                 August              September
Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa
             1  2  3   1  2  3  4  5  6  7            1  2  3  4
 4  5  6  7  8  9 10   8  9 10 11 12 13 14   5  6  7  8  9 10 11
11 12 13 14 15 16 17  15 16 17 18 19 20 21  12 13 14 15 16 17 18
18 19 20 21 22 23 24  22 23 24 25 26 27 28  19 20 21 22 23 24 25
25 26 27 28 29 30 31  29 30 31              26 27 28 29 30


      October               November              December
Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa
                1  2      1  2  3  4  5  6            1  2  3  4
 3  4  5  6  7  8  9   7  8  9 10 11 12 13   5  6  7  8  9 10 11
10 11 12 13 14 15 16  14 15 16 17 18 19 20  12 13 14 15 16 17 18
17 18 19 20 21 22 23  21 22 23 24 25 26 27  19 20 21 22 23 24 25
24 25 26 27 28 29 30  28 29 30              26 27 28 29 30 31
31
raghs@Raghs-LegionY540-TPIN:/mnt/c/WINDOWS/System32$
```

> Again, here as well, in the actual terminal output, the current date is highlighted! You can see it in the image below. 

### Screenshot 

<img src="https://www.raghsonline.com/tools/linux/cal/entire-year-today-highlighted.jpg" alt="Entire year, with the present day highlighted">

## Usage 

Whenver we want to work on a time bound activity and we prepare a calendar / plan, this utilty really helps you, as otherwise we need to look at other physical calendar, or keep clicking on the Calendar on the Desktop on the Operating System (Windows, or others).

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
29 Sep 2021 | Wed | 23:40:41 PM IST
