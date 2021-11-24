---
title: "Typescript Variables"
date: 2021-06-19T21:50:25+05:30
draft: false
tags:
  - Technical
  - Typescript
toc: true
author: Raghs
---

In this blog post, we will see how can we work with the *variables* in Typescript. 

<!--more-->

> This is part of the _Typescript Tutorial Series_, whose index / TOC is available here &rarr; [Typescript Tutorial Series](../typescript-tutorial-series/).

## Defining variables

We use the `let` keyword to define a variable in *Typescript*. As indicated the value of the variable is NOT fixed (hence the name) and can be changed at any point in time. 

The fundamental difference between the Typescript, and its predecessor *Javascript* is, Typescript has a strict type checking to ensure there are no gaps on the potential values that can be assigned to variable of a type. For example, we can't assign a character/alphabet value to a variable which accepts/expects a numerical data - example `age`. 

## Advantage of type checking 

If such kind of data type mismatch errros are not caught earlier (during the compilation time), they may blow up during the execution of the source code in the runtime, which is certainly *NOT* recommended, as it will disappoint the actual users of the application. 

Hence, this static type checking is much preferred and worth in languages like *Typescript* which is not the case with *Javascript*, where the users are expected to be diligent enough at all the times. 

## Syntax 

The syntax to define a variable goes as follows. 

```
let <varName> : <dataType> = <initialValue>;
```

where

 * `let` is a keyword
 * `varName` is the name of the variable
 * `dataType` is one of the valid types that can be assigned to a variable in `Typescript`
 * `initialValue` is the potentially allowed values according to the `datatype`
 * `;` is a line terminator

> The Typescript datatypes are discussed in this post &rarr; [Typescript Datatypes](../typescript-datatypes/)

## Example 1 - Proper data assignment 

```ts
let age : number = 21;

console.log(age);
```

The above program is legally valid as it follows the norms, by assigning a numeric data to the variable `age` whose type is defined as `number`. 

## Example 2 - Invalid data assignment 

```ts
let age : number = 'A';

console.log(age);
```
First of you all, the IDE (VSCode, Eclipse, or any others which has got the `tsc` embedded) will show a warning in the source code with an icon  or bulb indicating that error. 

If you still go ahead and compile (transpile) the program, the `tsc` will throw an error, as follows. 

```ts
typescriptPractices > tsc variables.ts
variables.ts:1:5 - error TS2322: Type 'string' is not assignable to type 'number'.

1 let age : number = 'A';
      ~~~

Found 1 error.

typescriptPractices >
```

The error message is pretty clear and self-explanatory. 

> Note: There is a caveat in this step - as the `tsc` will still produce the `.ts` file despite the compiler errors. We discuss how to avoid this in the [post](../typescript-noemitonerror/).

## Example Program with a few different type of variables

The below program demonstrates the usage of the primitive type variables with the valid values. 

*Source* : `variables.ts`

```ts
let found : boolean = true;
let mark : number = 99.1; 
let firstName : string = 'Raghavan'; //surrounded by a pair of single quotes
let lastName : string = "Muthu";    //surrounded by a pair of double quotes

console.log(found);    
console.log(mark);    
console.log(firstName);
console.log(lastName); 
```

Let us verify the file status.
```ts
typescriptPractices > ls -l
total 4
-rw-rw-rw-  1 raghs 0 222 2021-06-19 21:48 variables.ts

typescriptPractices >
```

We transpile the program using `tsc`. The `ls` command confirms the availability of `.js` file as a result of transpilation by the Typescript Compiler `tsc`.

```ts
typescriptPractices > tsc variables.ts

typescriptPractices > ls -l
total 8
-rw-rw-rw-  1 raghs 0 183 2021-06-19 21:49 variables.js
-rw-rw-rw-  1 raghs 0 222 2021-06-19 21:48 variables.ts
```

Then, execute the program using the node runtime - `node` with the generated/transpiled `.js` file. 

```ts
typescriptPractices > node variables.js
true
99.1
Raghavan
Muthu
```

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
19 Jun 2021 | Sat | 21 50 25 PM IST
