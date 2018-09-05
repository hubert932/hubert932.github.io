---
layout: post
title:  "Algorithm part1 Mathmatical Model"
date:   2018-09-05 20:57:05
categories: Algorithm
tags: Algorithm exercises
---

* content
{:toc}

How many array accesses does the following code fragment make as a function of nn?
(Assume the compiler does not optimize away any array accesses in the innermost loop.)

```
int sum = 0;
for (int i = 0; i < n; i++)
    for (int j = i+1; j < n; j++)
        for (int k = 1; k < n; k = k*2)
            if (a[i] + a[j] >= a[k]) sum++;
 ```
 
∼3n^2     <font color='red'>~3n^2lgn/2</font>    ~3n^3/2     ~3n^3


## 思路

Not all triple loops have cubic running times. For a given value of ii and jj, the kk-loop 
requires only 3lgn array access: the body is executed lgn times and each time involves 3 array 
accesses. As in the 2-SUM and 3-SUM analysis, the number of times the k-loop is executed is 
nC2 ~ n^2/2
