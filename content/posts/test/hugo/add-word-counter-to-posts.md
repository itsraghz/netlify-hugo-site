---
title: "Add Word Counter to Posts"
date: 2021-06-16T01:30:20+05:30
draft: false
tags: ["Test", "Hugo"]
toc: true
author: Raghs
---

# Add Word Counter to Posts

In this post, we will see how can we get the statistics on the *Word Counter* for every blog post in Hugo - both in the *Summary* and the *detailed* page.

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
  # true|false are the allowed and recommended values
  showWordCounter = true
```

*Note:* 
* The lines starting with a pound symbol `#` is a comment and generally used for the humans for better understanding.
* Remember the string `showWordCounter` is a keyword and should be used *as it is*.
* The configuration should be specified under the `[params]` section, for it to be effectively used in the rendering.

## References

* https://github.com/dsrkafuu/hugo-theme-fuji/blob/master/exampleSite/config.toml#L36


Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
16 Jun 2021 | Wed | 01 30 20 AM IST
