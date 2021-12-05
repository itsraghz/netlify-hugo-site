---
title: "Scale Out vs Scale Up"
date: 2021-12-05T21:52:08+05:30
draft: false
tags:
  - Technical
  - BigData
  - Concepts
toc: true
author: Raghs
---

# Scale Out vs Scale Up - to be renamed accordingly

Let us discuss the terminologies `scale out` and the `scale up` in this article - in general and also on the context of Big Data. 

<!--more-->

Though these terminologies are mostly inclined with the *Big Data*, they are still applicable to the outside as well for the *Scaling*.

## Scaling

Generally, the term *Scaling* indicates the ability to accommodate the increased demands of serving the clients for the Software/Application or the Data. The scaling can be accomplished at various aspects of the System/Server - be it in terms of increased memory (RAM) , hard disk, additional machines / systems in the same network topology etc., depending on the _actual_ type of demand. 

## Types of Scaling Functions

We have heard the terms of 'Horizontal' and 'Vertical' scaling and they indicate the nature of scaling we perform. 

* *Horizontal Scaling* - indicates we add the capacity in the horizontal manner - to accommodate them in more number of parallel servers - which indeed forms a chained connectivity from one node to another - expanding in the horizontal direction (left to right).
* *Vertical Scaling* - indicates the ability to add the capacity in the same server - by adding on top of one another - thus forming a vertical stack. 

## Scale Out Vs Scale Up 

The terminologies *Scale Out* and *Scale Up* - by now you would have imagined/predicted that they are the interchangeable terms of the _Horizontal_ and _Vertical_ scaling respectivley. 

| Type | Description | 
| ---- | ----------- |
| Scale Out | Scaling the additonal server/capacity *out*side of one server - from left to right - a horizontal scaling. |
| Scale Up  | Scaling the additional capacity in the same server - on top of the existing - forming a bottom to top - vertical scaling. | 

## Big Data Context 

These terminologies fit well in the Big Data Context - where in Hadoop, the nodes (HDFS - Hadoop Distributed File Systems) - facilities more nodes to be added for processing more chunks of data in the series (*Scale Out*), thanks to the commodity hardware available nowadays at a very afforadable cost. Where needed, they can be added on the same physial server, on top one of another - where it is called as *Scale Up*. 

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
05 Dec 2021 | Sun | 21:52:08 PM IST
