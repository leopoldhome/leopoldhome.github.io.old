---
layout: post
title: 求幂问题
categories: Algorithm
tags: 
  - sicp 
  - ch1
description: 详细分析了算法导论中的零钱兑换问题，从基本算法，递归优化以及迭代优化三个方面探讨了编程实现的方法。
date: 2019-11-27
---
# 求幂问题
给定的数计算乘幂的问题，这一过程会涉及到一个基数***b***和一个正整数***n***。过程计算出b^n 。
一般递归和迭代最大的区别在于:

| 递归 | 迭代 |
| --- | --- | --- |
|递归是函数自己调用自己，它通常是把一个大型复杂的问题转化为一个原问题相似的规模较小的问题来解决|利用变量的原值推算出新值，迭代就是A不断的调用B  |
一般的计算方法为:
$b^n$ = $b^{n-1}$  $\ast$ $b$
$b^0$ = 1
不同算法的选择直接影响问题的复杂度，如下所示:
Solution1:递归
```c
(define (expt b n)
  (if (= n 0)
      1
      (* b (expt b (- n 1)))))
```
这个递归算法过程需要时间和空间复杂度均为：$\omicron$$(n)$

$b^3$ = $b$ $\cdot$ $($ $b$ $\cdot$$($ $b$ $\cdot$$))$
验算：
$(expt$ $b$ $3)$ 
= $b$ $\cdot$ $(expt$ $b$ $2)$ 
= $b$ $\cdot$ $b$ $\cdot$ $(expt$ $b$ $1)$
= $b$ $\cdot$ $b$ $\cdot$ $b$ $\cdot$ $(expt$ $b$ $0)$
= $b$ $\cdot$ $b$ $\cdot$ $b$ $\cdot$ $1$
= $b$ $\cdot$ $b^2$
= $b^3$
纵向方式是运行的时间，而横向代表的是运行程序的空间。由此可以看出，目前时间和空间的运行复杂度都是正比于$n$。
Solution2：迭代

```text
(define (expt b n)
   (expt-iter b n 1))
  
(define (expt-iter b counter product)
  (if (= counter 0 )
      product
      (expt-iter b
                 (- counter 1)
                 ;从中间取出来的一个值就需要放在一个临时的变量中不断的进行迭代
                 (* b product))))
```
以上的这个方式只产生了一个临时空间，而且在不断的进行更新
$(expt$ $b$ $3)$ 
= $(expt$ $b$ $3$ $1$$)$
= $(expt$ $b$ $2$ $b$$)$
= $(expt$ $b$ $1$ $b^2$$)$
= $(expt$ $b$ $1$ $b^3$$)$
= $b^3$
从上面的盐酸可以看出计算的空间复杂度一直是$\omicron$$(1)$ ，而时间复杂度随着与$counter$成正比，所以时间复杂度为$\omicron$$(n)$ 。







