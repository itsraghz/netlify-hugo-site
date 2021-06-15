---
title: "Default Author Test"
date: 2021-06-16T00:48:15+05:30
draft: false
tags: ["Test", "Hugo", "TODO"]
toc: true
author: Raghs
---

# Default Author Test

Test page to verify the *default* `author` configured in the `config.toml` and the `default.md` file. But it does *NOT* display as intended. *_Need to inspect further!_*.

<!--more-->

## TODO 

Applied all the settings relevant to the author information. So far, the default `author` info gets added in the post `.md` file of the post, but it does not get rendered.  However, I guess, there needs to be some changes
done in the `layouts\partials\post-meta.html` file. 

Will check further as to how the *Author* Info will be displayed in the article content when gets displayed. 

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

## Reference 

* https://github.com/gohugoio/hugo/issues/8037#issuecomment-742246717

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
16 Jun 2021 | Wed | 00 48 15 AM IST
