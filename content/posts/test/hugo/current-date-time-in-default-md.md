---
title: "Current Date Time in default.md file"
date: 2021-06-14T12:52:12+05:30
draft: false
tags: ["Test", "Hugo"]
toc: true
---

# Current Date Time in the `default.md` file

In this blog post, we will explore the different formats available in `golang` to capture the current server 
date and time in the `default.md` file for an appropriate timestamp in any new posts created through `hugo new posts\xyz.md`.

<!--more-->

## Format in `golang` 

## Different settings and values/results 

| Sl # | Configuration  | Result  | 
| ---- | -------------- | ------- |
|  1   | {{ now.Format "2006" }}-{{ now.Format "02" }}-{{ now.Format "01" }} | 2021-14-06 | 
|  2   | {{ now.Format "2006-01-02 Mon" }} | 2021-06-14 Mon | 
|  3   | {{ now.Format "2006-Jan-02" }} | 2021-Jun-14 | 
|  4   | {{ now.Format "15 04 05 PM IST" }}| 12 52 12 PM IST | 

## A combined value of my choice 

The *Format* I have applied for my choice is : `{{ now.Format "02 Jan 2006" }} | {{ now.Format "Mon" }} | {{ now.Format "15 04 05 PM IST" }}`.

The *Result* is : `14 Jun 2021 | Mon | 12 52 12 PM IST`

## References 

The URLs will be of a good help for further explorations. 

* https://tecadmin.net/get-current-date-time-golang/
* https://www.golangprograms.com/get-current-date-and-time-in-various-format-in-golang.html

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
14 Jun 2021 | Mon | 12 52 12 PM IST

