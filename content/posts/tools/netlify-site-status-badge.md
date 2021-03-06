---
title: "Netlify Site Status Badge"
date: 2021-06-26T17:17:50+05:30
draft: false
tags:
  - Technical
  - Tools
  - Netlify
toc: true
author: Raghs
weight: 1
---

In this blog post, we will see how to add the status badge of the latest *Netlify* build of your site. 

## Badge for my website 

[![Netlify Status](https://api.netlify.com/api/v1/badges/e18a01a4-94a8-4185-aa55-887cc1984c14/deploy-status)](https://app.netlify.com/sites/raghsonline/deploys)

<!--more-->

## How to do

* Go to [Netlify site](https://netlify.com)
* Click on [Settings](https://app.netlify.com/sites/raghsonline/settings/general) `https://app.netlify.com/sites/<YourSiteName>/settings/general`
* Click on [*Status Badges*](https://app.netlify.com/sites/raghsonline/settings/general#status-badges) section
* Copy the snippet given below (the snippet has your App Id of your site embedded)
* Paste it anywhere you like - `README` of your website, `header` file of the site etc., to reflect the latest build status of your site with *Netlify*

## Images 

## Being Published - `Building`

### Badge status in the Website Blog post (localhost)

<img src="https://raghsonline.com/hugo-site-related/netlify/netlify-deployment-badge-buildling.JPG" alt="Changes are being built - Building" />

### Badge status in the Netlify site 

<img src="https://raghsonline.com/hugo-site-related/netlify/netlify-deployment-status-starting-up.JPG" alt="Deployment is starting up - Starting Up" />

### Badge status in the GitHub README file 

<img src="https://raghsonline.com/hugo-site-related/netlify/github-project-README-status-building.JPG" alt="GitHub README status - Building" />

## Completed - `Success`

### Badge status in the Website Blog Post (localhost)

<img src="https://raghsonline.com/hugo-site-related/netlify/netlify-deployment-badge-success.JPG" alt="Changes are successfully deployed - Success" />

### Badge status in the Netlify site

<img src="https://raghsonline.com/hugo-site-related/netlify/netlify-deployment-status-Published.JPG" alt="Netlify Site Status - Published" />

### Badge status in the GitHub README file

<img src="https://raghsonline.com/hugo-site-related/netlify/github-project-README-status-success.JPG" alt="GitHub README status - Success" />

# References 

* https://docs.netlify.com/monitor-sites/status-badges/
  
Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
26 Jun 2021 | Sat | 17:17:50 PM IST
