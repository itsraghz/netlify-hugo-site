---
title: "Typescript Basics"
date: 2021-06-19T16:37:51+05:30
draft: false
tags: 
  - Technical
  - Typescript
toc: true
author: Raghs
---

# Typescript Basics

We will the basics of [*TypeScript*](http://www.typescriptlang.org) in this blog post.

<!--more-->

> This is part of the _Typescript Tutorial Series_, whose index / TOC is available here &rarr; [Typescript Tutorial Series](../typescript-tutorial-series/).

## What is TypeScript 

In short, `TypeScript` is a superset of `JavaScript` with increased programming features like `static type checking`, 
*OOP* Style programming such `Class`es, and `Interface`s etc., 

It is a new language created by Microsoft and has been widely used in the Frontend Technology like `Angular`. In fact Angular 2 Framework was entirey rewritten in Typescript, from its predecessor version `Angular JS` which was written in Javascript.

## Typescript Execution Flow

In simple terms, the execution flow of a Typescript program is described in 3 steps as follows. The

* Source &rarr; The Soure code is written in any compatible text editor or IDE with an extension `.ts`
* Transpile &rarr; The Source code is *Trans*formed and Com*piled* into a javascript file with an extension `.js`
* The Javascript file is executed in a browser or the Node runtime environment

### What you need to work with Typescript 

You need to have the following to work with Typescript.

|  Tool | Link | Description | 
| ----- | ---- | ----------- |
| `npm` | https://npmjs.org/ | *Node Package Manager* to install the typescript via `npm install -g tsc` to install globally (`-g` flag) to all the users |
| `tsc` | http://typescriptlang.org | *Typescript* to _transpile_ the program from the `.ts` to `.js` form. |
| `node`  | http://nodejs.org/ | *Node Runtime* to execute the converted the Javascript Program |

### Command Execution Example

If we have a Helloworld Program in TypeScript, the code execution goes like this.

```
# Source code written in `helloworld.ts`

# Transpile this program using the `tsc` - TypeScript compiler 
tsc helloworld.ts

# Run the `.js` version of the Program using the Node 
node helloworld.js
```

## Example 

*Source Code* &rarr; `helloworld.ts`

```javascript
typescriptPractices > type helloworld.ts 
console.log("Hello World!");
```

*Transpile* using `tsc`

```ts
typescriptPractices > tsc myhelloworld.ts 

typescriptPractices > ls -l
total 8
-rw-rw-rw-  1 raghs 0 30 2021-06-18 22:20 helloworld.js
-rw-rw-rw-  1 raghs 0 28 2021-06-18 22:18 helloworld.ts
```

*Execute* &rarr; using `node` of the `.js` file generated 

```js
typescriptPractices > node helloworld.js
Hello World!

typescriptPractices >
```

## References 

* https://www.typescriptlang.org/ 

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
19 Jun 2021 | Sat | 16 37 51 PM IST
