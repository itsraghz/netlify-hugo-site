---
title: "Default Dark Theme"
date: 2021-06-16T00:57:13+05:30
draft: false
tags: ["Test", "Hugo"]
toc: true
author: Raghs
---

# Default Dark Theme

In this blog post, we will see how can we enforce the default theme to be *dark*, to save the energy :) 

<!--more-->

## Disclaimer

*Note:* I use the [*Fuji*](https://github.com/dsrkafuu/hugo-theme-fuji/) Theme for Hugo.

> I presume most of the configuration values should be common across all the themes. 
> However, it is better to check with the theme documentation for the right way to get the data 
> rendered and displayed correctly on the site, as the keywords used to display the data might be different in
> each theme. 

## Configuration in the `config.toml` file 

The settings to be applied in the `config.toml` file is given below.

```
[params]  
  ....
  defaultTheme = "dark" # default theme when first visit (auto|dark|light)
```

## References

* My own post in the [Discourse - GoHugo site](https://discourse.gohugo.io/t/issue-in-the-b-w-on-fuji-2-theme/33366)
* https://github.com/dsrkafuu/hugo-theme-fuji/blob/master/exampleSite/config.toml#L36

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
16 Jun 2021 | Wed | 00 57 13 AM IST
