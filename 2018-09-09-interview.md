---
layout: post
title:  "小米面试题"
date:   2018-09-09 11:03:05
categories: Algorithm
tags: Algorithm interview 小米
---

* content
{:toc}

## 问题

小米面试题目: 一副从1到n的牌，每次从牌堆顶取一张放桌子上，再取一张放牌堆底，

直到手中没牌，最后桌子上的牌是从1到n有序，设计程序，输入n，输出牌堆的顺序数组

## 解题思路:

取一个1～n的数组，这里为了说明取n=5。按照题目中的规则变换，得到数组：[1 3 5 4 2]，

将该数组下标与值互换得到[1 5 2 4 3]，即为答案。解释：[1 3 5 4 2]的意义是，经过变换，

原数组中3号位置的数字现在2号槽，原数组中5号位置的数字现在3号槽... 现在已知变换后的

槽存放的是1～n，故只要将下标与值互换就可得到待求数组。

然后由[1 3 5 4 2]看出，左边为奇数顺序排列，右边为偶数逆序排列，所以有代码如下：

```
public class poker {
	public static void main(String[] args) {
		int n = 5;
		int[] a = new int[n];
		int[] b = new int[n];
		for (int i = 0; i < (n+1) / 2; i++) {
			a[i] = 2 * i + 1;
		}
		for (int j = n - 1; j >=(n+1) / 2; j--) {
			a[j] = 2 * (n - j);
		}
		for (int i = 0; i < n; i++) {
			b[a[i] - 1] = i +1;
		}
		for (int k = 0; k < n; k++) {
			System.out.print(b[k] + " ");
		}
	}
}
```

## 小插曲

因为对数组不熟练，在
```
for (int i = 0; i < n; i++) {
			b[a[i] - 1] = i +1;
		}
```
这一步曾经写成a[a[i] - 1] = i +1;导致a[i]一直动态变化而得到错误答案。

然后发现问题后再定义新数组b[i]就解决了。
