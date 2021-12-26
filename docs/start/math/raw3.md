# 特殊符号

-  $\boldsymbol{\hat y} = \boldsymbol{W} \boldsymbol{x}$ 的输入
代码：
```md
$\boldsymbol{\hat y} = \boldsymbol{W} \boldsymbol{x}$
```

- $\ell_p$ 范数: `$\ell_p$`

对于一些特殊的数学符号可以使用 `\operatorname{}` 或者 `\text{}` 来进行转换，如：`$\text{cov}$` 和 `$\operatorname{s.t.}$` 便显示为：$\text{cov}$ 和 $\operatorname{s.t.}$



还有：

```md
$A \xrightarrow{f} B \; a \; \bot b \; \overset{def}{=}$ 
```
$A \xrightarrow{f} B \; a \; \bot b \; \overset{def}{=}$ 

```md
$$
 \underset{x\in S\subseteq X}{\operatorname{arg\,max}}\, f(x) := \{x \mid x\in S \wedge \forall y \in S : f(y) \le f(x)\}.   
$$
```

$$
 \underset{x\in S\subseteq X}{\operatorname{arg\,max}}\, f(x) := \{x \mid x\in S \wedge \forall y \in S : f(y) \le f(x)\}.   
$$

```md
$$
\operatorname*{\arg\max}_{x\in S\subseteq X}\, f(x) := \{x \mid x\in S \wedge \forall y \in S : f(y) \le f(x)\}.   
$$
```

$$
\operatorname*{\arg\max}_{x \in S \subseteq X}\, f(x) := \{x \mid x\in S \wedge \forall y \in S : f(y) \le f(x)\}.   
$$

- 更多特殊符号可以访问：[Detexify](http://detexify.kirelabs.org/classify.html)
- 更多关于数学符号的内容，参 考 [L ATEX Mathematical Symbols](https://github.com/q735613050/filezoo/blob/master/Symbols.pdf)
    - 关于数学符号的解释见 [List of mathematical symbols by subject](https://en.wikipedia.org/wiki/List_of_mathematical_symbols_by_subject)
- 更多精彩参考<http://www.cnblogs.com/q735613050/p/7253073.html>

## 对齐多行公式

```latex
$$
\begin{aligned}
a  &= b^2 + c^2\\
&= w^3 + b
\end{aligned}
$$
```

显示：

$$
\begin{aligned}
a  &= b^2 + c^2\\
&= w^3 + b
\end{aligned}
$$

### 关于矩阵的语法

```
$$
\begin{Bmatrix}
	1&2&3\\
	4&5&6\\
	7&8&9
\end{Bmatrix}
 \tag{7}
$$
```

显示：

$$
\begin{Bmatrix}
	1&2&3\\
	4&5&6\\
	7&8&9
\end{Bmatrix}
 \tag{7}
$$

更多矩阵设计：

```
$$
\begin{vmatrix}
	1&2&3\\
	4&5&6\\
	7&8&9
\end{vmatrix}
 \tag{8}
$$

$$
\begin{Vmatrix}
1&2&3\\
4&5&6\\
7&8&9
\end{Vmatrix}
 \tag{9}
$$

$$
\bigl(
	\begin{smallmatrix} 
		... 
	\end{smallmatrix}
\bigr)
$$

$$ 
\left[
    \begin{array}{cc|c}
      1 & 2 & 3 \\
      4 & 5 & 6
    \end{array}
\right] \tag{12}
$$
```
显示：

$$
\begin{vmatrix}
	1&2&3\\
	4&5&6\\
	7&8&9
\end{vmatrix}
 \tag{8}
$$

$$
\begin{Vmatrix}
1&2&3\\
4&5&6\\
7&8&9
\end{Vmatrix}
 \tag{9}
$$

$$
\bigl(
	\begin{smallmatrix} 
		... 
	\end{smallmatrix}
\bigr)
$$

$$ 
\left[
    \begin{array}{cc|c}
      1 & 2 & 3 \\
      4 & 5 & 6
    \end{array}
\right] \tag{12}
$$
