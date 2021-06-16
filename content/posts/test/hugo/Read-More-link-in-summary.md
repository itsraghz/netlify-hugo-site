---
title: "Read More Link in Summary"
date: 2021-06-15T09:59:02+05:30
draft: false
tags: ["Test", "Hugo"]
toc: true
author: Raghs
---

# Read More Link in Summary

Generally in the Summay page of blogs or articles, we just show an abstract or the few lines at the top with 
a linking text *Read More*.. or `Read More...` with a hyperlink to the article that is shown in entirety when
the link is clicked. 

<!--more-->

## How to enable it in Hugo

The theme I currently use for my Hugo site is [*fuji-theme*](https://github.com/dsrkafuu/hugo-theme-fuji/) which
does *NOT* have the `Read More...` text and link by default in the listing of posts. I had to enable this as follows.

The list seems to be defined by layouts/_default/list.html. We can overwrite template files as follows:

```sh
mkdir -p layouts/_default
cp themes/hugo-theme-fuji/layouts/_default/list.html layouts/_default/list.html
```

Then, edit `layouts/_default/list.html` file, and then add a new link “Read more” as follows after the line where it displays the *Summary* as `{{ .Summary }}`.

```sh
    {{ if .Truncated }}
      <a href="{{ .RelPermalink }}">Read More ...</a>
    {{ end }}
```

## Additional factor contributes to the conditional rendering of `Read More...` text

In addition to the template text in the `list.hml` inside `layouts\default` directory, each post has a specific 
keyword that supplements the conditional rendering of the `Read More...` text in Hugo. 

It is the `<!--more-->` clause that gives a hint that the post has some more text to be displayed further.

> Note: As part of the markdown when it gets broken, we can use the HTML escaped characters as `&lt;!&#45;&#45;more&#45;&#45;>`.

## Finished up code - in the relevant section

The content of the `<YOUR_SITE>\layouts\default\list.html` file looks like below. 

```sh
  <div class="post-item post-summary markdown-body">
    {{ .Summary }}    
    {{ if .Truncated }}
      <a href="{{ .RelPermalink }}">Read More ...</a>
    {{ end }}
  </div>
```

## Result - Screenshot 

The result - as on date - is given below. 

<img src="https://raghsonline.com/hugo-site-related/read-more-link/ReadMoreLink-15Jun2021.JPG" alt="Read More Link - Image - 15Jun2021"/>

*Update* 

The broken link is rectified via *escaping*. The reference URL for the fix is added in the `References` section below.

<img src="https://raghsonline.com/hugo-site-related/read-more-link/ReadMoreLink-Rectified-16Jun2021.JPG" alt="Read More Link - Rectified - 16Jun2021"/>

## References 

* My own post in [GoHugo Support Forum](https://discourse.gohugo.io/t/fuji2-theme-how-to-add-read-more/33367)
* How to avoid the `Read More...` in Hugo Summary &rarr; [Avoid the Read More link in Summary](/posts/test/hugo/read-more-link-avoided-in-summary/)
* My own post in [GoHugo Support Forum](https://discourse.gohugo.io/t/hugo-how-to-escape-the-html-characters-for-the-shortquote-like-more/33387/2?u=itsraghz)
  
> Have a look at [this layout](https://github.com/funkydan2/hugo-kiera/blob/master/layouts/index.html) - especially line 15.

> In your list.html inside the loop of the pages, you’ll can use `{{ .RelPermalink }}` or `{{ .Permalink }}` to link to the page (probably around [line 13 of your layout](https://github.com/dsrkafuu/hugo-theme-fuji/blob/v2.7.1/layouts/_default/list.html)).

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
15 Jun 2021 | Tue | 09 59 02 AM IST
