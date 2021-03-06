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
# 数学分析
## 增长趋势
$n\to+\infty,\forall p,q>0,a>1,{(\ln n)}^q\ll n^p\ll a^n\ll n!\ll n^n$
## 积分表
反读可得导数表，此处略。
$\int k\,\mathrm{d}x=kx+C$
$\int x^a\,dx=\frac{x^{a+1} }{a+1}+C$
$\int\frac{1}{x}\,dx=\ln|x|+C$
$\int e^x\,dx=e^x + C$
$\int a^x\,dx=\frac{a^x}{\ln a}+C$
$\int\cos x\,dx=\sin x+C$
$\int\sin x\,dx=-\cos x+C$
$\int\frac{1}{cos^2x}\,dx=\int\sec^2 x\,dx=\tan x+C$
$\int\frac{1}{sin^2x}\,dx=\int\csc^2 x\,dx=-\cot x+C$
$\int\frac{1}{\sqrt{1-x^2} }\,dx=\arcsin x+C=-\arccos x + C$
$\int\frac{1}{1+x^2}\,dx=\arctan x+C=-arccot\,x+C$
$\int\sec x\tan x\,dx=\sec x+C$
$\int\csc x\cot x\,dx=-\csc x+C$
$\int\tan x\,dx=-\ln|\cos x|+C$
$\int\cot x\,dx=\ln|\sin x|+C$
$\int\sec x\,dx=\ln|\sec x+\tan x|+C$
$\int\csc x\,dx=\ln|\csc x-\cot x|+C$
$\int sh\,x\,dx=ch\,x+C$
$\int ch\,x\,dx=sh\,x+C$
$\int\frac{1}{x^2+a^2}\,dx=\frac{1}{a}\arctan\frac{x}{a}+C$
$\int\frac{1}{x^2-a^2}\,dx=\frac{1}{2a}\ln|\frac{x-a}{x+a}| + C$
$\int\frac{1}{\sqrt{a^2-x^2} }\,dx=\arcsin\frac{x}{a}+C$
$\int\frac{1}{\sqrt{x^2-a^2} }\,dx=\ln|x+\sqrt{x^2-a^2}|+C$
$\int\frac{1}{\sqrt{x^2+a^2} }\,dx=\ln|x+\sqrt{x^2+a^2}|+C$

## test
```mermaid
graph TD
A[Christmas] -->|Get money| B(Go shopping)
B --> C{Let me think}
C -->|One| D[Laptop]
C -->|Two| E[iPhone]
C -->|Three| F[Car]
```
