---
title: "How to Add Author Info"
date: 2021-06-16T15:51:36+05:30
draft: false
tags: ["Technical", "Hugo"]
toc: true
author: Raghs
---

# How to Add Author Info

In this blog post, we will seee how can we add the *Author* Info into the blog posts  with *Fuji* Theme. 

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
  author = "Raghs" # You can also set author in post front matter individually
  ....
```

## Configuration in the `default.md` file 

The settings to be applied in the `<YOUR_SITE>\archetypes\default.md` file is as follows. 

```
author: {{ .Site.Params.author }}
```
> The `.Site.Params.author` specifies the nested hierarchy of the configuration parameters in the `config.toml` file. 

| Keyword | Meaning | 
| ------- | ------- |
| `.Site` | Global configuration for the site. |
| `.Params` | The `params` or `[params]` section of the config file `config.toml`. |
| `.author` | The specific / leaf level config key of the *params* section. `params -> author` |

## Configuration in the `post-meta.html` file 

The changes to be applied in the `<YOUR_SITE>\layouts\partials\post-meta.html` file are given below.

```
<span>
  <i class="iconfont icon-pricetags-sharp"></i>&nbsp;
  {{with .Params.author}} {{.}} {{end}}
</span>
```

> Note: I did not find any suitable icon for the Author. Just for the time being,I had reused the 
> *pricetag* icon which is used for the *tags*. I am exploring the further steps to properly inject
> the icon for the User/s for the Authors.

## Reference 

* https://github.com/gohugoio/hugo/issues/8037#issuecomment-742246717
* My own post in Discourse GoHugo site &rarr; [author-info-present-but-not-displayed](https://discourse.gohugo.io/t/hugo-fuji-theme-author-info-present-but-not-displayed/33389/2?u=itsraghz)

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
16 Jun 2021 | Wed | 15 51 36 PM IST
