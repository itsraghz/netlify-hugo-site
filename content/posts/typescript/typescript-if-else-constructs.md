---
title: "Typescript If Else Constructs"
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

An `else` clause is used to provide an alternate to the `if` statement, when the condition is *not* evaluated to `true`. 

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

typescriptPractices > cat if-statement.js
var age = 39;
if (age > 40) {
    console.log("Welcome Adult");
}
console.log("Your age is : " + age);

typescriptPractices > tsc if-statement.ts

typescriptPractices > node if-statement.js
Your age is : 39
```

You can see that the program did *NOT* print the greeting (*Welcome* statement) as the condition did not evaluate to true &rarr; `39 is not greater than 40`. Instead it just printed the age at the end of the program which was unconditionally executed, meaning the statement was not bound to any condition.

```ts

// Make changes to the source code to change the value from 39 to 41
typescriptPractices > cat if-statement.js
var age = 41;
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

You can see that the program did print the greeting (*Welcome* statement) as the condition was evaluated to true &rarr; `41 is greater than 40`. 

It also printed the age at the end of the program which was unconditionally executed, meaning the statement was not bound to any condition.

### Example - if-else statements

Now, we will see a sample program with the `if-else` constructs to have two different / alternate behaviors.

*Source* : `if-else.ts` 

```ts
typescriptPractices > ls -l *if-e*
-rw-rw-rw-  1 raghs 0 174 2021-06-22 01:26 if-else.ts

typescriptPractices > cat if-else.ts
let myAge : number = 39;

if( myAge > 40 ) {
    console.log("Welcome Adult");
} else {
    console.log("Welcome Youngster");
}

console.log("Your age is : " + myAge);

typescriptPractices > 
```

*Transpile* and *Verify* : 

```ts
typescriptPractices > tsc if-else.ts

typescriptPractices > ls -l *if-el*
-rw-rw-rw-  1 raghs 0 163 2021-06-22 01:29 if-else.js
-rw-rw-rw-  1 raghs 0 174 2021-06-22 01:26 if-else.ts

typescriptPractices > 
```

*Execute* : 

```ts
typescriptPractices > node if-else.js
Welcome Youngster
Your age is : 39
```

You can see that the program printed the output in the `else` clause as the condition was not evaluated to true &rarr; `Age 39 is NOT less than 40` and it has also printed the age as part of the last line which is an unconditional execution. 

## References 

 * [Typescript basics](../typescript-basics/)
  
Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
22 Jun 2021 | Tue | 01:17:28 AM IST
