---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: true
tags:
  - TODO
toc: true
author: {{ .Site.Params.author }}
---

# {{ replace .Name "-" " " | title }} - to be renamed accordingly

The content for the blog post with the title &rarr; "{{ replace .Name "-" " " | title }}" will go here.

<!--more-->

> This is part of the _Typescript Tutorial Series_, whose index / TOC is available here &rarr; [Typescript Tutorial Series](../typescript-tutorial-series/).


Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
{{ now.Format "02 Jan 2006" }} | {{ now.Format "Mon" }} | {{ now.Format "15:04:05 PM IST" }}
