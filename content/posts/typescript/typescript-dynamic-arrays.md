---
title: "Typescript Dynamic Arrays"
date: 2021-06-22T01:45:23+05:30
draft: false
tags:
  - Technical
  - Typescript
toc: true
author: Raghs
---

In this blog post, we will see how can we make use of the dynamically growing nature of the *Arrays* in Typescript.

<!--more-->

> This is part of the _Typescript Tutorial Series_, whose index / TOC is available here &rarr; [Typescript Tutorial Series](../typescript-tutorial-series/).

# Dynamic Arrays 

In Typescript, the *array* datatype is actually a Data Structure that has the capacity to grow automatically, as and when there are new elements added to it, after it is once intialized, similar to the other Programming langauge like *Java*. 

It is not the case with the languages like `C`, where we need to programatically allocate space for accommodating the new elements in the same container (data structure).

We can easily add the elements into an array via `push()` method which takes the `value to be inserted` as an argument, and the `push` method adds the elements in the last position of the array.

## Syntax 

```ts
let values : string[] = ['Yes'];

values.push('No');
```

## Example 

*Source* : `dynamic-arrays.ts`

```ts
typescriptPractices > ls *dyna*
dynamic-arrays.ts

typescriptPractices > cat dynamic-arrays.ts
let subjects : string[] = ["C", "C++", "Java"];

subjects.push("Python");
subjects.push("AWS");

for(let subject of subjects) {
    console.log(subject);
}

typescriptPractices > 
```

*Transpile* and *Verify* : 
```ts
typescriptPractices > tsc dynamic-arrays.ts

typescriptPractices > ls -l *dyna* 
-rw-rw-rw-  1 raghs 0 225 2021-06-22 01:44 dynamic-arrays.js
-rw-rw-rw-  1 raghs 0 162 2021-06-22 01:44 dynamic-arrays.ts

typescriptPractices > 
```

*Execute* : 

```ts
typescriptPractices > node dynamic-arrays.js
C
C++
Java
Python
AWS
```

As you see, the array has conveniently grown automatically with the elements being added at the end, and we are able to retrieve the element in the same order they were inserted. 

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
22 Jun 2021 | Tue | 01:45:23 AM IST
