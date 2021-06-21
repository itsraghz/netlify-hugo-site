---
title: "Typescript Simplified for Loop"
date: 2021-06-22T01:06:18+05:30
draft: false
tags:
  - Technical
  - Typescript
toc: true
author: Raghs
---

In this blog post, we will see how can we use the *simplified* `for` loop in TypeScript.

<!--more-->

> This is part of the _Typescript Tutorial Series_, whose index / TOC is available here &rarr; [Typescript Tutorial Series](../typescript-tutorial-series/).

# Simplified For Loop 

## Syntax 

The syntax of the simplified for loop is as follows:

```ts
for (let <loop_var> of <array_var>) {
  // executable statement
}
```

## Usage 

```ts
let marks : number[] = [ 63, 88, 75, 45, 90, 66 ];

for (let mark of marks) {
  console.log(mark);
}
```

The above example uses the simplified for loop to print the elements in the `marks` array, one at a time using the loop variable `mark` which is *of* the same type as that of the array variable `marks`. 

> `Of` is a keyword that connects the *loop counter variable* with the *array* variable.

## Example 

*Source* : `simplified-for-loop.ts`

```ts
typescriptPractices > ls -l *simp*
-rw-rw-rw-  1 raghs 0 103 2021-06-22 01:09 simplified-for-loop.ts

typescriptPractices > cat simplified-for-loop.ts
let marks : number[] = [63, 88, 75, 45, 90, 66];

for(let mark of marks) {
    console.log(mark);
}
typescriptPractices > 
```

*Transpiling* and *Verifying* the genreated files : 

```ts
typescriptPractices > tsc simplified-for-loop.ts

typescriptPractices > ls -l *simp*
-rw-rw-rw-  1 raghs 0 159 2021-06-22 01:09 simplified-for-loop.js
-rw-rw-rw-  1 raghs 0 103 2021-06-22 01:09 simplified-for-loop.ts
```

*Execute* the generated the `.js` file via `node`

```ts
typescriptPractices > node simplified-for-loop.js
63
88
75
45
90
66

typescriptPractices >
```

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
22 Jun 2021 | Tue | 01:06:18 AM IST
