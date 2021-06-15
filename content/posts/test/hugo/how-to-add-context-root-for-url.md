---
title: "How to add the Context Root for URL"
date: 2021-06-16T00:23:11+05:30
draft: false
tags: ["Test", "Hugo"]
toc: true
---

# How to add the Context Root for the relative URLs

In this blog post, we will see how we can add the *Context Root* for the URLs in the posts in the *Hugo Site*. 

If we need to specify a link to a different post, we would better keep it short as a relative URL so that we don't
mess up with the configuration hassles (local, external etc.,) as it would certainly take the current context - wherever it is deployed. 

<!--more-->

## Way to specify the URL relative to the host

A simple and easy way to specify the URL relative to the context/host is to just prefix it with a forward slash `/`
and specify the URL from the `posts` directory.

Example: 

```
[Title of the Link](/posts/<location_of_the_post_or_resource>/)
```

The below text will take to the relevant post without any explicit context root being mentioned. 

Read here &rarr; [Avoid the Read More link in Summary](/posts/test/hugo/read-more-link-avoided-in-summary/)

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
16 Jun 2021 | Wed | 00 23 11 AM IST
