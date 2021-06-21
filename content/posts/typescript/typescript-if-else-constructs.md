---
title: "Typescript if Else Constructs"
date: 2021-06-22T01:17:28+05:30
draft: false
tags:
  - Technical
  - Typescript
toc: true
author: Raghs
---

In this blog post, we will see how can we use the `if` and `else` constructs in the Typescript program.

<!--more-->

> This is part of the _Typescript Tutorial Series_, whose index / TOC is available here &rarr; [Typescript Tutorial Series](../typescript-tutorial-series/).

# If construct 

```ts
if(`<expression>`) {
  //executable statement
}
```

In the above snippet, the `executable statement` gets executed, *ONLY* if the `expression` evaluates to `true`. 

# If-Else construct 

An `else` clause is used to provide an alternate to the `if` statement, when the condition is *not* evaluates to `true`. 

```ts
if(`<expression>`) {
  //executable statement 1
} else {
   //executable statement 2
}
```
In the above snippet, if the `expression` evaluates to `true`, the `executable statement 1` gets executed. Otherwise,  the `executable statement 2` gets executed.

## Example 

### Example - if statement 

```ts
typescriptPractices > ls if-st*
if-statement.ts

typescriptPractices > tsc if-statement.ts

typescriptPractices > node if-statement.js
Your age is : 39

typescriptPractices > cat if-statement.js
var age = 39;
if (age > 40) {
    console.log("Welcome Adult");
}
console.log("Your age is : " + age);

typescriptPractices > tsc if-statement.ts  

typescriptPractices > node if-statement.js
Welcome Adult
Your age is : 41

typescriptPractices >
```

### Example - if-else statements

```ts
typescriptPractices > ls -l *if-e*
-rw-rw-rw-  1 raghs 0 174 2021-06-22 01:26 if-else.ts

typescriptPractices > cat if-else.ts
let myAge : number = 39;

if( myAge > 40 ) {
    console.log("Welcome Adult");
} else {
    console.log("Welcome Younster");
}

console.log("Your age is : " + myAge);
typescriptPractices > tsc if-else.ts

typescriptPractices > ls -l *if-el*
-rw-rw-rw-  1 raghs 0 163 2021-06-22 01:29 if-else.js
-rw-rw-rw-  1 raghs 0 174 2021-06-22 01:26 if-else.ts

typescriptPractices > node if-else.js
Welcome Younster
Your age is : 39
```

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
22 Jun 2021 | Tue | 01:17:28 AM IST
