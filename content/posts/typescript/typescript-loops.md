---
title: "Typescript Loops"
date: 2021-06-22T00:24:22+05:30
draft: false
tags: ["Technical", "Typescript"]
toc: true
author: Raghs
---

In this blog post, we will see how can we create and execute a simple loop in *Typescript*.

<!--more-->

> This is part of the _Typescript Tutorial Series_, whose index / TOC is available here &rarr; [Typescript Tutorial Series](../typescript-tutorial-series/).

# Simple For Loop

The simplest loop to start with is the `for` loop which takes the following sytax. This

```ts
for(let <loop_var>=<initialValue>; <var_condition> ; <post_operation>) {
  // any executable statement 
}
```

The above syntax basically tells that you take a loop iteration/counter variable `loop_var` and check for the `var_condition` to see whether it evaluates to `true`. If so, proceed with the `executable statement` below, and
then the `post_operation` - which is usually increment or decrement the `loop_var` but it is not restricted only with
them, instead it can be any other legal operation in Typescript. 

> The semicolon `;` is a part of the syntax, to separate the different portions of the loop.

## Simple For Loop - Example

```
for(let i = 0; i < 5; i++) {
  console.log(i);
}
```

The above program does the following: 

- Step 1 : Initialize the *loop variable* `i` to `0`.
- Step 2 : Checks for the condition - which is `i < 5` and that evaluates to true now. 
- Step 3 : Performs the operation in the executable statement - which is printing the value of `i` in the console. 
- Step 4 : Performs the `post operation` - which is incrementing the loop counter variable `i`. That makes `i = 0 + 1` equals `1` now.
- Step 5 : Repeat Step 2, until the condition evaluates to false. 

With the above algorithm, the program prints the value of `i` from `0` to `4`. 

## Simple For Loop - Execution 

*Source* : `loops.ts` 

```ts
typescriptPractices > ls -l
total 4
-rw-rw-rw-  1 raghs 0 53 2021-06-22 00:22 loops.ts
```

*Verify the file content* : 

```ts
typescriptPractices > cat loops.ts
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

*Transpile the Source* , and *Verify* : 

```ts
typescriptPractices > tsc loops.ts

typescriptPractices > ls -l
total 8
-rw-rw-rw-  1 raghs 0 55 2021-06-22 00:33 loops.js
-rw-rw-rw-  1 raghs 0 53 2021-06-22 00:22 loops.ts
```

*Execute* : 

```ts
typescriptPractices > node loops.js
0
1
2
3
4

typescriptPractices >
```

# For Loop with an Array of numbers 

Similar to the [_simple for loop_](#simple-for-loop), the for loop with array goes with the iteration of an array of values. 

The syntax looks as below.

```ts
let <varName> : <dataType>[] = ['<val_1>', '<val_2>', '<val_3>',....];
```

*Example*

```ts
let reviews: number[] = [5, 5, 3.14, 7, 6];
```

The above line of code declares an *array of numbers* named `reviews` along with the initial values of the array mentioned within the square brackets, each separated with a comma. 

The datatype `number` is associated with a pair of empty square brackets to denote that the accompanying variable `reviews` is an *array* of *number*s.


```ts
for(let <loop_var>=<initialValue>; <var_condition_on_array> ; <post_operation>) {
  // any executable statement 
}
```

Generally, the `var_condition_on_array` will be checking the array length by means of the property `length` on the array variable with a *dot* (`.`). See the example below for more details.

Using the for loop with an array in the same fashion, except that we check the `<array_var>.length` property to check whether the loop counter variable `i` has reached upto the last element of the array, starting from 0. 

```ts
for (let i = 0; i < reviews.length; i++) {
    console.log(reviews[i]);
}
```

> Remember, like any other Programming Language, *TypeScript* also starts the arrays with Zero (`0`). Hence the last item in the array will have the index as `n-1` where n is the number of elements.
 

```ts
typescriptPractices > ls -l        
total 16
-rw-rw-rw-  1 raghs 0 124 2021-06-22 00:40 reviews.ts

typescriptPractices > cat reviews.ts
let reviews: number[] = [5, 5, 3.14, 7, 6];

for (let i = 0; i < reviews.length; i++) {
    console.log(reviews[i]);
}

typescriptPractices > tsc reviews.ts 

typescriptPractices > ls -l
total 16
-rw-rw-rw-  1 raghs 0 112 2021-06-22 00:41 reviews.js
-rw-rw-rw-  1 raghs 0 124 2021-06-22 00:40 reviews.ts

typescriptPractices > node reviews.js
5
5
3.14
7
6

typescriptPractices >
```

# A complete example - for loop with arrays and an arithmetic operation 

```ts
typescriptPractices > cat reviews.ts
let reviews: number[] = [5, 5, 3.14, 7, 6];

let total : number = 0;

for (let i = 0; i < reviews.length; i++) {
    console.log(reviews[i]);
    total += reviews[i];
}

let average : number = total / reviews.length;
console.log("Average review : " + average);

typescriptPractices > 
```

```ts
typescriptPractices > tsc reviews.ts 

typescriptPractices > ls -l
total 16
-rw-rw-rw-  1 raghs 0  55 2021-06-22 00:33 loops.js
-rw-rw-rw-  1 raghs 0  53 2021-06-22 00:22 loops.ts
-rw-rw-rw-  1 raghs 0 238 2021-06-22 00:57 reviews.js
-rw-rw-rw-  1 raghs 0 272 2021-06-22 00:56 reviews.ts
```

```ts
typescriptPractices > node reviews.js
5
5
3.14
7
6
Average review : 5.228

typescriptPractices >
```

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
22 Jun 2021 | Tue | 00:24:22 AM IST
