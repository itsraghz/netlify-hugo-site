---
title: "Where Clause vs Having Clause in SQL"
date: 2021-06-21T23:01:55+05:30
draft: false
tags:
  - Database
  - Technical
toc: true
author: Raghs
---

In this blog post, we will see the differences between the condition applied in the `where` clause and the `having` clause. 

<!--more-->

## Where Clause

The condition in the `where` clause is applied on the resulting rows fetching from the table before any grouping is formed. It can be used on any other SQL statement like `INSERT`, `UPDATE`, or `DELETE`, not just necessarily on `SELECT` alone. 

## Having Clause

The condition in the `having` clause is applied on the results, after the groups are formed. It works only with the `GROUP BY` clause, and *ONLY* on the `SELECT` statements.

> Need to explore the performance implications if any between the two. 

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
21 Jun 2021 | Mon | 23:01:55 PM IST
