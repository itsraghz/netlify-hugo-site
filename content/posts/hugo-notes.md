---
title: "Hugo Notes"
date: 2021-05-25T13:57:52+05:30
draft: false
tags:
  - Technical
  - Hugo
toc: true
weight: 2
author: Raghs
---

This post will contain the essentials of [_Hugo_](https://gohugo.io/) - Static Site Generator and the associated
tools and nuances.

I have primarily tested in Windows OS. Will subsequently test this in the
Linux OS (Cent OS) and add the appropriate notes in the due course of time.

<!--more-->

# Hugo Tutorials, Books, and Videos

- An excellent blog, by zwbetz (Zachary Wade Betz) - Author of the [_Cupper Theme_](https://github.com/zwbetz-gh/cupper-hugo-theme) &rarr; https://zwbetz.com/make-a-hugo-blog-from-scratch/
- https://www.sitepoint.com/premium/books/a-beginner-s-guide-to-creating-a-static-website-with-hugo/read/1
- https://thenewstack.io/tutorial-use-hugo-to-generate-a-static-website/
- https://medium.com/backticks-tildes/hugo101-getting-started-with-hugo-and-deploying-to-netlify-9a813fe23b94
- Mike Dane's excellent series of tutorials, which is even referred in the official website of [Hugo](https://gohugo.io)

  - His Channel &rarr; https://www.youtube.com/channel/UCvmINlrza7JHB1zkIOuXEbw
  - Introduction to Hugo | Hugo - Static Site Generator | Tutorial 1 &rarr; https://www.youtube.com/watch?v=qtIqKaDlqXo

- Chris Stayte's excellent series of short and sweet, to the point tutorials.
  - His Channel &rarr; https://www.youtube.com/channel/UC2NGv5afGSZXFHtNo_EJLdQ
  - Building A Website Using Hugo - YouTube Video Tutorial &rarr; https://www.youtube.com/watch?v=c7vpcqA6SEQ
  - Hosting your Website with GitHub and Netlify &rarr; https://www.youtube.com/watch?v=hBQlCtfRmqs

# Hugo Installation on Windows

The notes associated with the installation of Hugo in Windows 10 OS.

- Refer this guide for installing _Chocolatey_ in the desktop &rarr; https://docs.chocolatey.org/en-us/choco/setup

## Chocolatey

Chocolatey is installed in the following directory in Windows OS. &rarr; `C:\ProgramData\Chocolatey`

`choco list -lo` - lists down the list of packages installed and their versions

```
C:\raghs\prfsnl\hugoPractices\hugo-cupper-theme-test (master)
λ choco list -lo
Chocolatey v0.10.15
chocolatey 0.10.15
hugo 0.83.1
2 packages installed.
```

# Salient features (USP) of Hugo

## Live reloading of the changes

Hugo Server when it is running, will keep watching the changes if any being made to the content (any content - be it your posts, or the config files etc.,)
and it will reload the server with the latest changes as soon as you hit the _Save_ button on the editor where you made the changes.

It saves you a whole lot of efforts from stopping the server and restarting. It is called as _Hot Reloading_.

## Expiry Date for posts

It is really helpful for certain seasoned posts which are timebound.

> expiryDate

The datetime at which the content should no longer be published by Hugo; expired content will not be rendered unless the --buildExpired flag is passed to the hugo command.

> Reference : https://gohugo.io/content-management/front-matter/#predefined

## Inbuilt disqus integration

[Disqus](https://disqus.com) is a very famous, and simple comment management service. It can be very easily integrated
with Hugo as it has got an inbuilt support for it on most of the themes.

> Reference : https://gohugo.io/content-management/comments/

## Easy embedding of vidoes

Embedding a video is pretty easy in Hugo. For example, you need to copy the embedding text and paste it in the blog post (`xyz.md` file)
and the vidoe will be automatically made availabel with a medium size widget/canvas in the blog post.

In order to get the embeddable text, you click on the _Share_ option of a Video in YouTube and further click on `Embed'. It opens a window
with a few customizations, with the long text for you to copy it and paste it on your website.

_Example_: I paste the _Hugo Tutorials_ of Mike Dann here as follows.

```
<iframe width="560" height="315" src="https://www.youtube.com/embed/qtIqKaDlqXo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

_Video_

<iframe width="560" height="315" src="https://www.youtube.com/embed/qtIqKaDlqXo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Hugo Themes - References

## Blogs and Websites

### Tried and tested themes

- https://themes.gohugo.io/theme/hugo-theme-fuji/
- https://themes.gohugo.io/hugo-coder/

### Yet to try

- https://github.com/zwbetz-gh/cupper-hugo-theme | https://cupper-hugo-theme.netlify.app/
- https://themes.gohugo.io/doks/
- https://themes.gohugo.io//theme/simpleness/
- https://geekdocs.de/usage/getting-started/

## CV / Bio Related

- https://themes.gohugo.io/flex-bp-hugo-cv/
- https://themes.gohugo.io/theme/simple-resume/
- https://themes.gohugo.io//theme/hugo-theme-timeline/timeline

# Hugo How-To's

Certain imporant How-To aspects of Hugo are listed below, which will be very helpful for the beginners.

## How does a Hugo site's folder structure look like ?

Once you create a new site with Hugo, it certainly provides a minimal, friendly information on the console as follows. You

```
C:\raghs\prfsnl\hugoPractices
λ hugo new site brand-new-hugo-site
Congratulations! Your new Hugo site is created in C:\raghs\prfsnl\hugoPractices\brand-new-hugo-site.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>\<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.

C:\raghs\prfsnl\hugoPractices
λ
```

The hugo new site will look the following.

```
C:\raghs\prfsnl\hugoPractices\brand-new-hugo-site
λ tree
Folder PATH listing for volume Windows-SSD
Volume serial number is C0000100 3287:9D9D
C:.
├───archetypes
├───content
├───data
├───layouts
├───static
└───themes

C:\raghs\prfsnl\hugoPractices\brand-new-hugo-site
λ
```

## What is the `data` folder used for ?

The data folder can be used to store structured data in the form of YAML, TOML or JSON files that will be made available as global variable throughout the website.

## What is the folder `archetypes` used for?

The folder `archetypes` inside the main `site` folder is used to maintain the default setup for the new posts, acting as a blueprint or the template. It has the file called `default.md` to get all the format/structure of the new posts being created.

You can add / make any valid changes you would want them to be a part of the posts when created via `hugo new posts/<postName.md>`. Remember: Hugo compiles the front matter contents and upon finding any syntax errors, it will throw an error on the terminal or even the screen if you are gonna ask for that page on the browser.

> Any changes you make in this `default.md` file will reflect on the future posts you would be creating. It will _NOT_ have any impact on the existing posts though.

## What is the `content` folder used for ?

The `content` folder is used to have all your contents, preferably in the `markdown` file format. Mostly the posts (blog posts)
will go into the sub-folder called `posts` - Example : `<YOUR_SITE>\content\posts\my-first-post.md`.

You would have to type in the contents in the `Markdown` language using its syntax. You can refer to any of the following URLs to
learn quickly about the Markdown syntax.

- https://www.markdownguide.org/
- https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

## How do I set up a theme?

There are two ways you can do that.

- Direct download of theme - Headover to the [Hugo Themes](https://themes.gohugo.io) website and download the theme as a .zip file and extract the same into the `theme` sub directory of your `site`.
- Using Git - clone the `.git` file of the theme in the `theme` sub directory of the `site`.

Once you had downloaded, you need to do two main things.

1. Update the config file (`config.toml` - preferred or `config.yaml`) with the key-value pair as `theme = <Name-of-the-theme>`. Remember, you should get the theme as mentioned in the theme webpage, or mostly it should match with the directory name of the theme.
2. Make some other changes as appropriate in the `config.toml` file , and also on the `static` folder as it deems fit.

## Do I have a reference model of the theme I just downloaded?

Yes, most of the themes come with the `exampleSite` sub-directory inside it, which you can refer to it, or even copy the contents of the entire folder into the main `site` folder and change the values as appropriately in the `config.toml` file.

> Remember: You can create a new site with this theme and test the features explicitly before you make changes to your main `site`.

_Note:_ If you copy the contents from the `exampleSite` folder into your main `site` folder, you would always get the updated contents from the theme provider via `git` whenver you upgrade/update it. However, the changes in your main `site` folder will NOT be reflected on this, as you have just copied the contents from this `exampleSite` to the main `site`. So, it will always
be a good reference point to you.

## What is the difference between `tags` and `categories` ?

#TODO There are two seemingly similar terms on the blog posts - `tags` and `categories`. How do they actually differ?

## How do I add a background image for the blog post?

You can add an image of your choice into the `<YOUR_SITE>/static` directory and can refer the image by
its name in the corresponding blog post through the following key-value pairs of the
[_Front Matter_](https://gohugo.io/content-management/front-matter/).

_Example_: You have a picture by named `Sunflower.jpg` in the `static` directory.

```
FileName: my-firt-post.md

---
title: "My First Post"
...
image: "Sunflower.jpg"
---
```

> Note: You don't need to specify the `static` directory reference as long as you have the files available in the `static` directory directly. Hugo looks for images in the `static` directory by default.

> In case, you have a sub-directory inside the `static` folder, you must specify the path, otherwise Hugo will not be able
> to find the image and it will just show a blank box in place of the image on the post.

## How do I change the cover image of my blog?

The cover image is very important and it stays on the home page occuping a decent space on the top most portion of the page. You should be diligent on
choosing a nice, apt image that suits the types of contents you are posting.

You can change the cover image as follows in the `config.toml` file.

```
cover = "img/blog-cover.jpg"
```

## Can I get some cool pictures for free to be used on my blogs?

You can visit [Pexels](https://pexels.com) to get some nice images for free. The best part is they let you download the images in 5 different
resolutions (Original, Large, Medium, Small, Custom) for the best match of your needs.

> Remember: For the blog posts, you should better off keep the _Medium_ sized images for a better and faster rendering and loading of the pages.

## How do I a source snippet in the blog ?

Nothing to do with Hugo, but with the markup syntax, it is very easy. All you need to do is just add the source code snippets between the
pair of a single backtick (`synchronized`) or 3 continuous backticks (```).

The single backtick is used for a shorter snippets or any keywords, whereas the 3 backticks pair is used for a block of code. You can optionally
type the name of the language at the end of the 3rd backtick in the opening pair, just to give an easy identification to anyone who reads the source code and also to the Interpreter to pick up the right language for the syntax highlighting.

```python
num1 = 3 # 1st number
num2 = 5 # 2nd number
print (num1 + num2) # print the sum of these 2 numbers
```

## How do I add a comment into my blog post - via Disqus?

As I mentioned it a couple of other places, this is one of the USP (Unique Selling Points) of Hugo, according to me.
It has got an inbuilt support for the _Disqus_ tool with just a few configuration tweaks.

First and foremost, you need to set up the _disqusShortName_ property in the `config.toml` file of the site, as follows.

```
disqusShortname = "itsraghz"
```

## How do I deploy my website into a live server ?

- Choose a Repo in GitHub, make sure it is public, otherwise you need to pay for it.
- Choose a license - preferably _MIT License_.
- Use the GitHub Desktop for an easy and efficient management of files in the repo.
- Add a `.gitmodule` file with the predefined syntax to push the theme to remote repo, where it actually creates a symbolic link to the actual theme github repo to keep them in sync always.
- The `baseUrl` value has to be wiped off, with the theme `capser-two` as it deems fixing the troubles. #TODO
- Go to [_Netlify_](https://netlify.com) and create an account if you don't have one.

# Hugo Troubleshooting

## Links

- Official forum : https://discourse.gohugo.io/

## FAQs

## How do I resolve the `404 - Page not found` when I click on any link on the blog?

It so happens, when you just download a theme and set it up half baked, where the links do not have the right contents or the links to the
relevant pages to show. In such case, Hugo displays the famous `404 - page not found` on the browser.

_Fix_ :

You can check the config file `config.toml` file to look for the values given for the link. If it says a `tags` or `categories`,
you can add a `tags` or `category` element as a key-value pair in the relevant posts, so that they get displayed under that category or
tag whenever the link is clicked.

_Note_ :

1. It is `tags` and NOT `tag`. The plural form is the actual keyword.
2. The `tags` takes an array / list of values surrounded in a _square bracket_ whereas each value is given in double quotes and separated by a comma.

_Example:_

```
File: my-first-post.md

---
title: "My First Post"
...
...
tags: ["First", "Personal"]
---
```

Similarly, you can do it for the _Categories_ with the keyword `categories` in place of `tags`. It depends on how the URL has been configured
for the corresponding menu item in the `config.toml` file.

> Note: At times the hot reloading may not be effectively picking up this change as it is altering the structure of the whole site.
> In such case, stop and reload the Hugo Server again with the command `hugo server -D` (to publish the draft posts).

# Conclusion

If you have come this far, it truly shows that you had read all the contents of this blog post,
and I hope it was insightful and you had gained something out of it :)

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
25 May 2021 | Tue | 14 25 PM IST
