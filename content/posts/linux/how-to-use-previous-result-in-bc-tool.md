---
title: "How to Use Previous Result in BC Tool"
date: 2021-09-29T23:15:38+05:30
draft: false
tags:
  - Linux
  - Tools
toc: true
author: Raghs
---

We will see how can use make use of the previous result (accumulated result) in the `bc` utility/tool in Linux.

<!--more-->


## How to make use of the previous result 

If you are working on a series of computations, and most likely you may need to make use of the sum accumulated in the previous step, which will be very difficult to copy and paste the value in the terminal. Luckily, we have an easy way to refer to the sum calculated so far, through the reserved word (keyword) called `last`. 

```sh
1 + 1
2
last + 1
3
```

You can clearly see that the use of word `last` referred to the calculated / accumulated result till the previous step, and that is now referred as `operand1`, for the next expression. The result is as expected in the next line, and it does not need any explanation. 


## See Also 

You can also read this post &rarr; [How to use the BC tool](./how-to-use-the-bc-tool.md)

## References

* [GNU Reference](https://www.gnu.org/software/bc/manual/html_mono/bc.html)

Cheers,\
RM...\
_Raghavan alias Saravanan Muthu_\
29 Sep 2021 | Wed | 23:15:38 PM IST
