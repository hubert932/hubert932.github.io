---
layout: post
title:  "Algorithm part1 Order-of-Growth"
date:   2018-09-05 21:19:05
categories: Algorithm
tags: Algorithm binary search
---

* content
{:toc}

#Binary Search
Too big, go left
Too small, go right
Equal, found


find 8

    mid     mid
1 3 5 6 8 9 13 15 18 23 26 28

```
public static int binarySearch(int a[], int key)
{
  int lo = 0, hi = a.length-1;
  while(lo <= hi)
  {
   int mid = lo+(hi-lo)/2;
   if      (key<a[mid]) hi = mid-1;
   else if (key>a[mid]) lo = mid+1;
   else return mid;
  }
  return -1;
}
```

