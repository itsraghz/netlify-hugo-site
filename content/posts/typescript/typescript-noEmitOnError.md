---
title: "Typescript NoEmitOnError"
date: 2021-06-19T16:46:20+05:30
draft: false
tags: 
  - Technical
  - Typescript
toc: true
author: Raghs
---

Generally the `tsc` program will produce the output in a `.js` format even though there are compile time errors during the *transpilation*, which may confuse the developers at time. We have a way to avoid the `.js` file generation in case of any errors.

<!--more-->

> This is part of the _Typescript Tutorial Series_, whose index / TOC is available here &rarr; [Typescript Tutorial Series](../typescript-tutorial-series/).

## Typical flow of `tsc` when there is a compilation error

*variables-with-errors.ts*

```ts
let isCaught : boolean = 1; // can have either a true or false, not anything else
```

```ts
typescriptPractices > tsc variables-with-errors.ts
variables-with-errors.ts:1:5 - error TS2322: Type 'number' is not assignable to type 'boolean'.

1 let isCaught : boolean = 1;
      ~~~~~~~~


Found 1 error.


typescriptPractices >
```

> Note: For certain valid and legitimate reasons, you can use the different datatype `any` instead of `boolean` to avoid the compiler error. 
> 
> However it is *_not_* generally recommended, until and otherwise you have a very strong reason, since it will defeat the purpose of Tyepscript due to the fact the `any` type will NOT perform the *type checking*.

Though the compiler generates an error in the console, the `tsc` still produces the output file `variables-with-errors.js`.

```ts
typescriptPractices > ls -l
total 24
-rw-rw-rw-  1 raghs 0 71 2021-06-19 23:43 any-demo.js
-rw-rw-rw-  1 raghs 0 75 2021-06-19 23:43 any-demo.ts
-rw-rw-rw-  1 raghs 0 58 2021-06-19 23:54 variables-with-errors.js
-rw-rw-rw-  1 raghs 0 68 2021-06-19 23:53 variables-with-errors.ts
-rw-rw-rw-  1 raghs 0 56 2021-06-19 23:41 variables.js
-rw-rw-rw-  1 raghs 0 67 2021-06-19 23:41 variables.ts

typescriptPractices > cat variables-with-errors.js
var isCaught = 1;
console.log("isFound : " + isCaught);
```

You can see that there is an output file generated `variables-with-errors.js` despite there was a compiler error. 

## Avoid the .js file generation

Now, let us see how can we avoid or control behavior in such a way that we do NOT want any `.js` file if there are any errors during the compilation/transpilation.

We can add a runtime flag `-noEmitOnError` during the invocation of the `tsc` to stop the generation of the output file with a `.js` extension.


```ts
typescriptPractices > rm variables-with-errors.js 

typescriptPractices > ls -l *.js
-rw-rw-rw-  1 raghs 0 71 2021-06-19 23:43 any-demo.js
-rw-rw-rw-  1 raghs 0 56 2021-06-19 23:41 variables.js

typescriptPractices > tsc -noEmitOnError variables-with-errors.ts
variables-with-errors.ts:1:5 - error TS2322: Type 'number' is not assignable to type 'boolean'.

1 let isCaught : boolean = 1;
      ~~~~~~~~

Found 1 error.

typescriptPractices > ls -l
total 20
-rw-rw-rw-  1 raghs 0 71 2021-06-19 23:43 any-demo.js
-rw-rw-rw-  1 raghs 0 75 2021-06-19 23:43 any-demo.ts
-rw-rw-rw-  1 raghs 0 68 2021-06-19 23:53 variables-with-errors.ts
-rw-rw-rw-  1 raghs 0 56 2021-06-19 23:41 variables.js
-rw-rw-rw-  1 raghs 0 67 2021-06-19 23:41 variables.ts

typescriptPractices >
```

The sequence of operations were carried out as below. 

* We have first deleted the `variables-with-errors.js` file
* Executed the `tsc` with the necessary `-noEmitOnError` flag as an argument. 
* This time there was no output file generated as there was a compiler error. 
* The output was verified with the listing at the end through `ls -l` command. 


Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
19 Jun 2021 | Sat | 22:11:29 PM IST
