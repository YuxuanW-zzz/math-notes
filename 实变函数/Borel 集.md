---
aliases:
  - Borel集
  - Borel set
  - 博雷尔集
  - Borel σ-代数
tags:
  - 实变函数
  - 测度论
  - 点集拓扑
  - 概念
---

# Borel 集

Borel 集是由开集生成的 [[sigma-代数|$\sigma$-代数]] 中的集合。它把拓扑中的开集、闭集与测度论中的可测结构连接起来。

## 1. 定义

设 $X$ 是拓扑空间，$\tau$ 是 $X$ 的所有开集组成的集合族。定义 **Borel $\sigma$-代数**

$$
\mathcal B(X):=\sigma(\tau).
$$

这里 $\sigma(\tau)$ 表示包含所有开集的最小 $\sigma$-代数，即

$$
\mathcal B(X)
=\bigcap\{\mathcal A:\mathcal A\text{ 是 }X\text{ 上的 }\sigma\text{-代数，且 }\tau\subseteq\mathcal A\}.
$$

若 $B\in\mathcal B(X)$，就称 $B$ 为 **Borel 集**。

在实变函数中，通常取 $X=\mathbb R^d$，并使用通常的欧氏拓扑。

> [!tip] 直观理解
> 从开集出发，允许反复取补集、可数并和可数交，得到的整个生成结构就是 Borel $\sigma$-代数。“最小 $\sigma$-代数”是严格定义，不能只理解成做一次或有限层运算。

## 2. 基本性质

$\mathcal B(X)$ 是 $\sigma$-代数，因此：

1. $\varnothing,X\in\mathcal B(X)$；
2. 所有开集都是 Borel 集；
3. 所有闭集都是 Borel 集，因为闭集是开集的补集；
4. 对可数并、可数交、补集封闭；
5. 对有限并、有限交、差集与对称差封闭。

例如，若 $A,B\in\mathcal B(X)$，则

$$
A\setminus B=A\cap B^c\in\mathcal B(X).
$$

> [!warning] 不保证任意并封闭
> $\sigma$-代数只保证可数并封闭。虽然 $\mathbb R^d$ 中每个单点集都是 Borel 集，但任意子集 $A=\bigcup_{x\in A}\{x\}$ 不一定是 Borel 集。

## 3. 常见的 Borel 集

### 3.1 区间、矩形与单点集

在 $\mathbb R$ 中，开区间、闭区间、半开区间和无界区间都是 Borel 集。例如

$$
[a,b)=[a,+\infty)\cap(-\infty,b).
$$

在 $\mathbb R^d$ 中，开矩形、闭矩形与立方体也都是 Borel 集。单点集 $\{x\}$ 是闭集，因而是 Borel 集。

### 3.2 可数集

若 $A=\{x_1,x_2,\dots\}$，则

$$
A=\bigcup_{n=1}^{\infty}\{x_n\}
$$

是 Borel 集。因此 $\mathbb Q$ 是 Borel 集，$\mathbb R\setminus\mathbb Q$ 也为 Borel 集。

### 3.3 $F_\sigma$ 集与 $G_\delta$ 集

- **$F_\sigma$ 集**：可数个闭集的并，$F=\bigcup_nF_n$。
- **$G_\delta$ 集**：可数个开集的交，$G=\bigcap_nO_n$。

它们都是 Borel 集，且互为补集类型：

$$
F\text{ 是 }F_\sigma
\quad\Longleftrightarrow\quad
F^c\text{ 是 }G_\delta.
$$

例如，$\mathbb Q$ 是 $F_\sigma$ 集，所以无理数集是 $G_\delta$ 集。[[Cantor 集]] 是闭集，因此也是 Borel 集。

> [!warning] Borel 集不止这两类
> $F_\sigma$ 与 $G_\delta$ 只是常见类型；一般 Borel 集未必属于其中任一种。对这些集合继续做可数并、可数交，可以得到更高层级的 Borel 集。

## 4. 等价的生成集合族

### 4.1 实数轴上的生成族

以下集合族生成同一个 $\mathcal B(\mathbb R)$：

$$
\{\text{所有开集}\},\qquad
\{(a,b):a<b\},\qquad
\{(p,q):p,q\in\mathbb Q,\ p<q\},
$$

以及

$$
\{(-\infty,a):a\in\mathbb R\},\qquad
\{(-\infty,a]:a\in\mathbb R\}.
$$

**有理端点为何足够？** 每个开集 $O\subseteq\mathbb R$ 都满足

$$
O=\bigcup_{\substack{p,q\in\mathbb Q,\ p<q\\(p,q)\subseteq O}}(p,q).
$$

有理端点区间构成可数族，因此右端是可数并；它们本身又是开集，故双方生成的 $\sigma$-代数相同。

**半直线为何足够？** 因为

$$
(-\infty,a]=\bigcap_{n=1}^{\infty}(-\infty,a+1/n),
$$

以及

$$
(a,b)=(-\infty,b)\setminus(-\infty,a].
$$

反过来，半直线本身也是 Borel 集。

### 4.2 $\mathbb R^d$ 中的生成族

所有有理端点开矩形

$$
(p_1,q_1)\times\cdots\times(p_d,q_d),
\qquad p_i,q_i\in\mathbb Q,\ p_i<q_i,
$$

构成可数拓扑基。每个开集都是这些矩形的可数并，因此它们生成 $\mathcal B(\mathbb R^d)$。

## 5. 与 [[Lebesgue 可测集]]的关系

### 5.1 Borel 集一定 Lebesgue 可测

所有开集都是 [[Lebesgue 可测集]]，而 Lebesgue [[Lebesgue 可测集|可测集]]族 $\mathcal M(\mathbb R^d)$ 是 $\sigma$-代数。因此由最小性，

$$
\mathcal B(\mathbb R^d)\subseteq\mathcal M(\mathbb R^d).
$$

对 $d\geq1$，实际上有严格包含：

$$
\mathcal B(\mathbb R^d)
\subsetneq\mathcal M(\mathbb R^d)
\subsetneq\mathcal P(\mathbb R^d).
$$

### 5.2 Lebesgue [[Lebesgue 可测集|可测集]]未必是 Borel 集

[[Cantor 集]] $C$ 是 Borel 零测集。它的任意子集都是 Lebesgue 可测的，但并非每个子集都是 Borel 集。

一种存在性说明是：$|C|=\mathfrak c$，所以 $C$ 的子集有 $2^{\mathfrak c}$ 个；而 $\mathbb R$ 中的 Borel 集只有 $\mathfrak c$ 个，其中 $\mathfrak c=|\mathbb R|$。由 Cantor 定理 $2^{\mathfrak c}>\mathfrak c$，必有非 Borel 的子集 $A\subseteq C$。同时 $m^*(A)=0$，所以 $A$ Lebesgue 可测。

> [!note] 区分两个结论
> “零测集的任意子集可测”是 Lebesgue 测度的完备性；不能据此说这些子集都是 Borel 集。

### 5.3 完备化与零测差

Lebesgue $\sigma$-代数是 Borel $\sigma$-代数关于 Lebesgue 测度的**完备化**。具体地，$E$ Lebesgue 可测当且仅当存在 Borel 集 $B,Z$，使

$$
m(Z)=0,
\qquad E\triangle B\subseteq Z.
$$

由 [[4. 测度的连续性、可测集逼近与不可测集]]，还可取 $F_\sigma$ 集 $F$ 与 $G_\delta$ 集 $G$，使

$$
F\subseteq E\subseteq G,
\qquad m(G\setminus E)=m(E\setminus F)=0.
$$

所以每个 Lebesgue [[Lebesgue 可测集|可测集]]都与某个 Borel 集只差一个零测集。

## 6. 与可测函数的关系

对有限值函数 $f:\mathbb R^d\to\mathbb R$：

- **Borel 可测**：对每个 $B\in\mathcal B(\mathbb R)$，$f^{-1}(B)\in\mathcal B(\mathbb R^d)$；
- **Lebesgue 可测**：对每个 $B\in\mathcal B(\mathbb R)$，$f^{-1}(B)\in\mathcal M(\mathbb R^d)$。

因为目标空间的 Borel $\sigma$-代数由开集生成，两种判别都只需检查所有开集的原像；进一步，只需检查所有水平集 $\{f<a\}$。

连续函数是 Borel 可测的：开集的原像是开集。Borel 可测函数一定 Lebesgue 可测，但反向不成立。例如若 $A$ 是 Lebesgue 可测而非 Borel 的集合，则示性函数 $\chi_A$ Lebesgue 可测，却不是 Borel 可测，因为

$$
\chi_A^{-1}((1/2,3/2))=A.
$$

参见 [[5. 可测函数、几乎处处收敛与简单函数逼近]]。

## 7. 常见误区

1. **把 Borel 集等同于开集或闭集**：它们还包含大量可数集合运算生成的集合。
2. **把所有 Borel 集都写成 $F_\sigma$ 或 $G_\delta$**：一般不成立。
3. **认为 Borel 集对不可数并封闭**：只保证可数并封闭。
4. **认为零测集的任意子集都是 Borel 集**：它们一定 Lebesgue 可测，但可能非 Borel。
5. **混淆 Borel 集与 Borel 测度**：前者是集合类型；后者是在 Borel $\sigma$-代数上定义的测度，需另外指定。

## 8. 相关内容

- [[sigma-代数|$\sigma$-代数]]
- [[Lebesgue 可测集]]
- [[外测度]]
- [[Cantor 集]]
- [[3. Lebesgue 可测集、测度的可数可加性与 sigma-代数]]
- [[4. 测度的连续性、可测集逼近与不可测集]]
- [[5. 可测函数、几乎处处收敛与简单函数逼近]]
