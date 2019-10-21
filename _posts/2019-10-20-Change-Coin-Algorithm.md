---
layout: post
title: Change coin Algorithm
categories: Algorithm
tags: 
  - dynamic programming 
  - sicp
description: 详细分析了算法导论中的零钱兑换问题，从基本算法，递归优化以及迭代优化三个方面探讨了编程实现的方法。
date: 2019-10-21
---
### 问题描述与分析
$\vec{x}$到$\vec{\mu}$的欧氏距离
下面的几道题可能会用到如下的程序：

- 写一个程序产生服从$d$维正态分布$N(\vec{\mu},\Sigma)$的随机样本
- 写一个程序计算一给定正态分布及先验概率$P(\omega_i)$的判别函数（式(49)中所给的形式）。
- 写一个程序计算任意两个点间的欧式距离。
- 在给定协方差矩阵$\Sigma$的情况条件下，写一个程序计算任意一点$\vec{x}$到均值$\vec{\mu}$间的Mahalanobis距离。
