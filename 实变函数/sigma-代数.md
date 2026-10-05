---
aliases:
  - σ-代数
  - sigma algebra
  - σ-field
tags:
  - 实变函数
  - 测度论
  - 概念
---

# $\sigma$-代数

$\sigma$-代数规定了哪些集合可以被一致地赋予测度。它对补集和可数集合运算封闭，是测度论与概率论的基本结构。

## 1. 定义

设 $X$ 是一个非空集合。若集合族

$$
\mathcal A\subseteq\mathcal P(X)
$$

满足：

1. $X\in\mathcal A$；
2. 若 $A\in\mathcal A$，则
   $$
   A^c=X\setminus A\in\mathcal A;
   $$
3. 若 $A_1,A_2,\dots\in\mathcal A$，则
   $$
   \bigcup_{n=1}^{\infty}A_n\in\mathcal A,
   $$

则称 $\mathcal A$ 是 $X$ 上的一个 $\sigma$-代数。

二元组

$$
(X,\mathcal A)
$$

称为可测空间，$\mathcal A$ 中的元素称为[[Lebesgue 可测集|可测集]]。

## 2. 可由定义推出的性质

### 2.1 空集属于 $\mathcal A$

因为 $X\in\mathcal A$ 且对补集封闭，

$$
\varnothing=X^c\in\mathcal A.
$$

### 2.2 对可数交封闭

由 De Morgan 律，

$$
\bigcap_{n=1}^{\infty}A_n
=\left(\bigcup_{n=1}^{\infty}A_n^c\right)^c
\in\mathcal A.
$$

### 2.3 对有限并和有限交封闭

在可数并中令其余集合为空集，即得有限并封闭；再结合 De Morgan 律得到有限交封闭。

### 2.4 对差集封闭

若 $A,B\in\mathcal A$，则

$$
A\setminus B=A\cap B^c\in\mathcal A.
$$

### 2.5 对对称差封闭

$$
A\triangle B
=(A\setminus B)\cup(B\setminus A)
\in\mathcal A.
$$

## 3. 基本例子

### 3.1 平凡 $\sigma$-代数

$$
\{\varnothing,X\}
$$

是 $X$ 上最小的 $\sigma$-代数。它只能区分“不发生”和“发生整个空间”两种情况。

### 3.2 幂集

$$
\mathcal P(X)
$$

是 $X$ 上最大的 $\sigma$-代数。

### 3.3 由一个子集生成的 $\sigma$-代数

给定 $A\subseteq X$，若 $A\neq\varnothing,X$，则

$$
\sigma(\{A\})
=\{\varnothing,A,A^c,X\}.
$$

### 3.4 可数或余可数 $\sigma$-代数

若 $X$ 不可数，则

$$
\mathcal A
=\{A\subseteq X:A\text{ 可数，或 }A^c\text{ 可数}\}
$$

是一个 $\sigma$-代数。

### 3.5 Borel $\sigma$-代数

在拓扑空间 $X$ 上，由所有开集生成的 $\sigma$-代数称为 Borel $\sigma$-代数，记为

$$
\mathcal B(X).
$$

在 $\mathbb R$ 上，下列集合族生成同一个 Borel $\sigma$-代数：

$$
\{\text{所有开集}\},
\quad
\{(a,b):a<b\},
\quad
\{(-\infty,a):a\in\mathbb R\},
$$

甚至只使用有理端点的开区间也足够。

### 3.6 Lebesgue $\sigma$-代数

所有 [[Lebesgue 可测集]] 构成的集合族记作

$$
\mathcal M(\mathbb R^d).
$$

它是一个 $\sigma$-代数，并且

$$
\mathcal B(\mathbb R^d)
\subsetneq
\mathcal M(\mathbb R^d)
\subsetneq
\mathcal P(\mathbb R^d).
$$

## 4. 生成的 $\sigma$-代数

给定集合族

$$
\mathcal C\subseteq\mathcal P(X),
$$

包含 $\mathcal C$ 的最小 $\sigma$-代数称为由 $\mathcal C$ 生成的 $\sigma$-代数，记作

$$
\sigma(\mathcal C).
$$

严格定义为

$$
\sigma(\mathcal C)
=\bigcap\{\mathcal A:\mathcal A\text{ 是 }X\text{ 上的 }\sigma\text{-代数且 }\mathcal C\subseteq\mathcal A\}.
$$

任意多个 $\sigma$-代数的交仍是 $\sigma$-代数，因此上述定义合理。

> [!warning] 并通常不是 $\sigma$-代数
> 两个 $\sigma$-代数 $\mathcal A_1,\mathcal A_2$ 的并
> $$
> \mathcal A_1\cup\mathcal A_2
> $$
> 一般不对集合运算封闭。若要同时包含二者，应取
> $$
> \sigma(\mathcal A_1\cup\mathcal A_2).
> $$

## 5. 有限集合上的例子

设

$$
X=\{1,2,3,4\},
$$

并把 $X$ 分成两个原子

$$
B_1=\{1,2\},
\qquad
B_2=\{3,4\}.
$$

则

$$
\mathcal A
=\{\varnothing,B_1,B_2,X\}
$$

是一个 $\sigma$-代数。它能判断一个点属于哪个分块，却不能区分同一分块中的两个点。

一般地，有限集合上的 $\sigma$-代数对应于对 $X$ 的一个划分：[[Lebesgue 可测集|可测集]]恰好是若干划分块的并。

## 6. $\sigma$-代数与测度

给定可测空间 $(X,\mathcal A)$，若函数

$$
\mu:\mathcal A\to[0,+\infty]
$$

满足

$$
\mu(\varnothing)=0
$$

以及对任意两两不交的 $A_1,A_2,\dots\in\mathcal A$，

$$
\mu\left(\bigcup_{n=1}^{\infty}A_n\right)
=\sum_{n=1}^{\infty}\mu(A_n),
$$

则称 $\mu$ 是 $(X,\mathcal A)$ 上的测度，三元组

$$
(X,\mathcal A,\mu)
$$

称为测度空间。

对 Lebesgue 测度，测度空间为

$$
(\mathbb R^d,\mathcal M(\mathbb R^d),m).
$$

## 7. $\sigma$-代数与可测函数

设 $(X,\mathcal A)$、$(Y,\mathcal B)$ 是可测空间。函数

$$
f:X\to Y
$$

称为可测函数，如果对每个 $B\in\mathcal B$，都有

$$
f^{-1}(B)\in\mathcal A.
$$

注意使用的是**原像**而不是像，因为原像与补集、可数并和可数交相容：

$$
f^{-1}(B^c)=f^{-1}(B)^c,
$$

$$
f^{-1}\left(\bigcup_nB_n\right)
=\bigcup_nf^{-1}(B_n).
$$

若 $f:\mathbb R^d\to\mathbb R$，通常只需验证

$$
\{x:f(x)>a\}
$$

对每个 $a\in\mathbb R$ 可测，即可推出 $f$ 是 Lebesgue 可测函数。

## 8. 为什么要求“可数”封闭

测度需要处理极限过程。例如

$$
E_n\uparrow E
\quad\text{或}\quad
E_n\downarrow E
$$

都涉及可数并或可数交。$\sigma$-代数正是为保证这些极限集合仍然可测而设计的。

一般不要求对任意不可数并封闭。例如每个单点集 $\{x\}$ 都是 [[Borel 集]]，但任意子集

$$
A=\bigcup_{x\in A}\{x\}
$$

未必是 [[Borel 集]]。

## 9. 与代数的区别

集合代数只要求对**有限并**和补集封闭；$\sigma$-代数进一步要求对**可数并**封闭。

$$
\sigma\text{-代数}\quad\Longrightarrow\quad\text{集合代数},
$$

反向一般不成立。

## 10. 常见误区

1. **只验证有限并**：有限并封闭不足以成为 $\sigma$-代数。
2. **忘记相对全集取补集**：$A^c$ 指 $X\setminus A$。
3. **认为两个 $\sigma$-代数的并仍是 $\sigma$-代数**：一般不成立。
4. **混淆 $\sigma(\mathcal C)$ 与 $\mathcal C$**：生成过程通常会加入大量集合。
5. **认为所有子集都应可测**：在 Lebesgue 测度下存在不[[Lebesgue 可测集|可测集]]。
6. **认为任意并都应可测**：$\sigma$-代数只保证可数并封闭。

## 11. 相关内容

- [[Lebesgue 可测集]]
- [[外测度]]
- [[3. Lebesgue 可测集、测度的可数可加性与 sigma-代数]]
- [[Borel 集]]
- [[可测函数]]
- [[测度空间]]
