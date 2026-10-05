---
aliases:
  - Lebesgue measurable set
  - 可测集
tags:
  - 实变函数
  - Lebesgue测度
  - 概念
---

# Lebesgue 可测集

Lebesgue 可测集是能够被开集或闭集在“相差零测度”的意义下任意精确逼近的集合。在这些集合上，[[外测度]]具有真正的可数可加性，从而成为 Lebesgue 测度。

## 1. 开集外逼近定义

集合 $E\subseteq\mathbb R^d$ 称为 **Lebesgue 可测集**，如果对任意 $\varepsilon>0$，都存在开集 $O\supseteq E$，使得

$$
m^*(O\setminus E)<\varepsilon.
$$

若 $E$ 可测，则定义其 Lebesgue 测度为

$$
m(E):=m^*(E).
$$

> [!tip] 直观理解
> 可测性表示：可以从集合外部套上一个开集，而且多出来的部分可以任意小。

## 2. Carathéodory 判别

集合 $E\subseteq\mathbb R^d$ 可测，当且仅当对任意 $A\subseteq\mathbb R^d$，

$$
m^*(A)
=m^*(A\cap E)+m^*(A\setminus E).
$$

由[[外测度]]的可数次可加性，总有

$$
m^*(A)
\leq m^*(A\cap E)+m^*(A\setminus E).
$$

因此判别条件的实质是证明反向不等式。可测集能够把任意集合 $A$ 分成两个部分，同时不产生额外的[[外测度]]损失。

## 3. 等价逼近条件

以下条件彼此等价：

1. $E$ 是 Lebesgue 可测集；
2. 对任意 $\varepsilon>0$，存在开集 $O\supseteq E$，使
   $$
   m^*(O\setminus E)<\varepsilon;
   $$
3. 对任意 $\varepsilon>0$，存在闭集 $F\subseteq E$，使
   $$
   m^*(E\setminus F)<\varepsilon;
   $$
4. 存在 $G_\delta$ 集 $G\supseteq E$，使
   $$
   m^*(G\setminus E)=0;
   $$
5. 存在 $F_\sigma$ 集 $F\subseteq E$，使
   $$
   m^*(E\setminus F)=0.
   $$

其中：

- $G_\delta$ 集是可数个开集的交；
- $F_\sigma$ 集是可数个闭集的并。

若 $m(E)<\infty$，还可以要求闭集 $F$ 为紧集 $K$。于是

$$
m(E)
=\inf_{O\supseteq E,\ O\text{ 开}}m(O)
=\sup_{K\subseteq E,\ K\text{ 紧}}m(K).
$$

这称为 Lebesgue 测度的正则性。

## 4. 基本例子

以下集合都是 Lebesgue 可测集：

1. 开集；
2. 闭集；
3. 区间、矩形和立方体；
4. 可数集；
5. [[Cantor 集]]；
6. [[Borel 集]]；
7. 零外测集的任意子集；
8. 由上述集合经过可数并、可数交和取补得到的集合。

## 5. 为什么开集可测

若 $E$ 本身是开集，在开集外逼近定义中直接取

$$
O=E.
$$

于是

$$
m^*(O\setminus E)=m^*(\varnothing)=0.
$$

所以所有开集均可测。

## 6. 为什么零外测集可测

若

$$
m^*(N)=0,
$$

则由[[外测度]]的开集外逼近，对任意 $\varepsilon>0$，存在开集 $O\supseteq N$，使

$$
m^*(O)<\varepsilon.
$$

因此

$$
m^*(O\setminus N)
\leq m^*(O)
<\varepsilon.
$$

故 $N$ 可测。若 $A\subseteq N$，由单调性 $m^*(A)=0$，所以 $A$ 也可测。

这就是 Lebesgue 测度的**完备性**。

## 7. 对集合运算的封闭性

所有 Lebesgue 可测集组成的集合族记作

$$
\mathcal M(\mathbb R^d).
$$

它满足：

### 7.1 对补集封闭

$$
E\in\mathcal M
\quad\Longrightarrow\quad
E^c\in\mathcal M.
$$

### 7.2 对可数并封闭

$$
E_n\in\mathcal M
\quad\Longrightarrow\quad
\bigcup_{n=1}^{\infty}E_n\in\mathcal M.
$$

### 7.3 对可数交封闭

由 De Morgan 律，

$$
\bigcap_{n=1}^{\infty}E_n
=\left(\bigcup_{n=1}^{\infty}E_n^c\right)^c
\in\mathcal M.
$$

因此 $\mathcal M(\mathbb R^d)$ 是一个 [[sigma-代数|$\sigma$-代数]]。

## 8. Lebesgue 测度的性质

### 8.1 可数可加性

若 $E_1,E_2,\dots$ 两两不交且均可测，则

$$
m\left(\bigcup_{n=1}^{\infty}E_n\right)
=\sum_{n=1}^{\infty}m(E_n).
$$

这是测度与一般[[外测度]]最关键的区别。

### 8.2 差集公式

若 $A\subseteq B$、$A,B$ 可测且 $m(B)<\infty$，则

$$
m(B\setminus A)=m(B)-m(A).
$$

有限测度条件不能随意删去，因为 $\infty-\infty$ 没有定义。

### 8.3 单调性

若 $A\subseteq B$，则

$$
m(A)\leq m(B).
$$

### 8.4 平移不变性

对任意 $x\in\mathbb R^d$，

$$
m(E+x)=m(E).
$$

### 8.5 缩放性质

对任意 $\lambda\in\mathbb R$，

$$
m(\lambda E)=|\lambda|^d m(E).
$$

## 9. 测度的连续性

### 9.1 从下连续

若

$$
E_1\subseteq E_2\subseteq\cdots,
$$

则

$$
m\left(\bigcup_{n=1}^{\infty}E_n\right)
=\lim_{n\to\infty}m(E_n).
$$

该结论不要求 $m(E_n)$ 有限。

### 9.2 从上连续

若

$$
E_1\supseteq E_2\supseteq\cdots
$$

且 $m(E_1)<\infty$，则

$$
m\left(\bigcap_{n=1}^{\infty}E_n\right)
=\lim_{n\to\infty}m(E_n).
$$

这里 $m(E_1)<\infty$ 是必要条件。

## 10. [[Borel 集]]与 Lebesgue 可测集

记：

- $\mathcal B(\mathbb R^d)$：由开集生成的 Borel $\sigma$-代数；
- $\mathcal M(\mathbb R^d)$：Lebesgue 可测集组成的 $\sigma$-代数；
- $\mathcal P(\mathbb R^d)$：$\mathbb R^d$ 的幂集。

它们满足

$$
\mathcal B(\mathbb R^d)
\subsetneq
\mathcal M(\mathbb R^d)
\subsetneq
\mathcal P(\mathbb R^d).
$$

Lebesgue $\sigma$-代数可看作 Borel $\sigma$-代数关于 Lebesgue 测度的完备化：它还包含所有 Borel 零测集的任意子集。

## 11. 不可测集

并非 $\mathbb R^d$ 的每个子集都可测。典型例子是利用选择公理构造的 Vitali 集。

不可测集的存在说明：虽然 [[外测度]] 可以赋给所有集合一个数值，但只有满足可测性判别的集合，才能与集合运算相容并具有可数可加性。

## 12. 常用判定策略

证明 $E$ 可测时，通常采用以下方法之一：

1. 证明 $E$ 是开集或闭集；
2. 把 $E$ 表示为已知可测集的可数并、可数交或补集；
3. 证明 $m^*(E)=0$；
4. 用开集从外部逼近；
5. 用闭集或紧集从内部逼近；
6. 验证 Carathéodory 判别式。

## 13. 相关内容

- [[外测度]]
- [[sigma-代数|$\sigma$-代数]]
- [[Cantor 集]]
- [[3. Lebesgue 可测集、测度的可数可加性与 sigma-代数]]
- [[Borel 集]]
- [[Vitali 集]]
