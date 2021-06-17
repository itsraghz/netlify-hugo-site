---
title: "Text Portrait in CSS"
date: 2021-06-12T12:01:52+05:30
draft: false
tags: ["Web Design", "Portfolio", "Personal"]
toc: true
author: Raghs
---

# Text Portrait in CSS

A simple and interesting way to make a *Text Portrait* in CSS in a few simple steps. 

<!--more-->

## Steps 

1. Make a simple HTML with some *Lorem Ipsum* text in large quantity to fill the page
   
```html
<p id='text'>
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam cursus .....
</p>
```
2. Add a background color black and overflow hidden

```css
body {
  background: black;
  overflow: hidden;
}
```

3. Add a background image and apply the necessary properties

```css
background: url("Raghs.jpg");
background-attachment: fixed;
background-repeat: no-repeat;
background-position: center;
```

4. Add a web clipping property, that will do the wonders :) 

```css
-webkit-background-clip: text;
```

> Note: In case the property `-webkit-background-clip` does not work, you can try with the alternative `background-clip: text;`

## Result 

<img src='https://raghsonline.com/raghs-text-portrait.jpg' alt='Raghs - Text Portrait'/>

<img src='https://raghsonline.com/raghs-twitter-pic-portrait.jpg' alt='Raghs-Twitter Pic - Text Portrait'/>


## Reference 

* My Own : <a href='https://codepen.io/itsraghz/pen/qBrJYEx'>CodePen - Raghs</a>
* My Tweet link to Pratham: <a href='https://twitter.com/itsraghz/status/1403590677221363715'>Tweet</a>
* Actual Reference : <a href='https://codepen.io/prathkum/pen/xxgrXje'>CodePen - Pratham</a>

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
12 Jun 2021 | Sat | 11 50 AM IST
