---
title: "Typescript Datatypes"
date: 2021-06-19T23:25:23+05:30
draft: false
tags: 
  - Technical
  - Typescript
toc: true
author: Raghs
---

We will see the list of available *datatypes* in Typescript language.

<!--more-->

> This is part of the _Typescript Tutorial Series_, whose index / TOC is available here &rarr; [Typescript Tutorial Series](../typescript-tutorial-series/).

## Data types in Typescript 

The available data types in Typescript is given below.

### Primitive data types

* `number` - any numeral values - both the whole numbers (`9`) and fractions (`3.14`).
* `string`. Remember, the lowercase `s`, as opposed to the rest of the languages like Java where it is `String`. The value can be specified within either a pair of *single quotes* or *double quotes*.
* `boolean`

### Arrays

Arrays are used to specify the list of values of the same type, say for example, list of marks obtained by a student in a semester. All of them are marks but they are carried together as an array. 

```
let marks : number[] = [45, 67, 81, 55, 90];
```

### Any 

`any` is a special data type in Typescript used as a safer type to have any possible data, without any restrictions. 

* `any` - a general, wider data type to accept the value of any type, similar to the `var` in Javascript

#### Example - `any`

*Source*: `any-demo.ts`

```ts
let obj : any = 9;
console.log(obj);

obj = 'Raghavan'; // no restrictions
console.log(obj);
```

Executing the `.js` file produced by the transpiler `tsc`, we get the following output.

```ts
typescriptPractices > tsc any-demo.ts

typescriptPractices > node any-demo.js
9
Raghavan

typescriptPractices >
```

> Remember: `any` is not a typechecked, similar to the other data types. So be *careful* and *diligent* on the values being assigned to the variables of type `any`.


Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
19 Jun 2021 | Sat | 23:25:23 PM IST
