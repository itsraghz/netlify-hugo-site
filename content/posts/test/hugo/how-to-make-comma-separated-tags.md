---
title: "How to Make Comma Separated Tags"
date: 2021-06-16T19:18:48+05:30
draft: false
tags: ["Hugo", "Test"]
toc: true
author: Raghs
---

In this blog post, we will see how to customize the tags when displayed in the *Hugo* site, especially with the *Fuji* theme.

<!--more-->

## Disclaimer

*Note:* I use the [*Fuji*](https://github.com/dsrkafuu/hugo-theme-fuji/) Theme for Hugo.

> I presume most of the configuration values should be common across all the themes. 
> However, it is better to check with the theme documentation for the right way to get the data 
> rendered and displayed correctly on the site, as the keywords used to display the data might be different in
> each theme. 

## Config changes to be done in the `post-meta.html` file

The layout for the tags should be modified appropriately in the `<YOUR_SITE>\layouts\partials\post-meta.html` file, as follows. 

> Note: The predefined set up has more or less the same thing, but no comma in it. I tried adding a comma in the default listing - after every individual tag element in displayed, however it adds a tag for all the elements uncontionally, which does not look good for the last element. Hence, made use of the [snippet/gist from the sample github link](https://github.com/funkydan2/hugo-kiera/blob/fcefa5e5997948e6ef7dbcb57e793259ba33036d/layouts/partials/aside.html#L26-L29), to add the comma for all but the last goes as listed above. 

```
{{ if .Params.tags }}
    <span>
        <i class="iconfont icon-pricetags-sharp"></i>&nbsp;
        <em>
            {{ range $i, $t := .Params.tags }}
                {{ if $i }}, {{ end }}
                <a href="{{ relLangURL ( printf "tags/%s" ( $t | urlize ) ) }}">{{ $t}}</a>
            {{ end }}
        </em>
    </span>
{{ end }}
```

## References 

* My own post in Discourse GoHugo website &rarr; [fuji2-theme-how-to-add-read-more](https://discourse.gohugo.io/t/fuji2-theme-how-to-add-read-more/33367/14). Asked 2 Qns in the same thread - one for `Read More...` text and other for the *comma separated tags*
* https://github.com/dsrkafuu/hugo-theme-fuji/blob/50317aec4ac3884d46fefac5812b8ad8e1e15a46/layouts/partials/post-meta.html#L5
* https://github.com/funkydan2/hugo-kiera/blob/fcefa5e5997948e6ef7dbcb57e793259ba33036d/layouts/partials/aside.html#L26-L29

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
16 Jun 2021 | Wed | 19 18 48 PM IST
