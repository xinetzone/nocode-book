# 矩阵

矩阵相关。

## 无框矩阵

在开头使用 `\begin{matrix}`，在结尾使用 `\end{matrix}`，在中间插入矩阵元素，每个元素之间插入 `&`，并在每行结尾处使用 `\\`。

使用矩阵时必须声明 `$` 或 `$$` 符号。

````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info
```latex
$$
\begin{matrix}
    1 & x & x^2 \\
    1 & y & y^2 \\
    1 & z & z^2 \\
\end{matrix}
$$
```
---
$$
\begin{matrix}
    1 & x & x^2 \\
    1 & y & y^2 \\
    1 & z & z^2 \\
\end{matrix}
$$
````

## 边框矩阵

在开头将 `matrix` 替换为 `pmatrix` `bmatrix` `Bmatrix` `vmatrix` `Vmatrix`。

````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info
```latex
$ \begin{matrix} 1 & 2 \\ 3 & 4 \\ \end{matrix} $
$ \begin{pmatrix} 1 & 2 \\ 3 & 4 \\ \end{pmatrix} $
$ \begin{bmatrix} 1 & 2 \\ 3 & 4 \\ \end{bmatrix} $
$ \begin{Bmatrix} 1 & 2 \\ 3 & 4 \\ \end{Bmatrix} $
$ \begin{vmatrix} 1 & 2 \\ 3 & 4 \\ \end{vmatrix} $
$ \begin{Vmatrix} 1 & 2 \\ 3 & 4 \\ \end{Vmatrix} $
```
---
$ \begin{matrix} 1 & 2 \\ 3 & 4 \\ \end{matrix} $
$ \begin{pmatrix} 1 & 2 \\ 3 & 4 \\ \end{pmatrix} $
$ \begin{bmatrix} 1 & 2 \\ 3 & 4 \\ \end{bmatrix} $
$ \begin{Bmatrix} 1 & 2 \\ 3 & 4 \\ \end{Bmatrix} $
$ \begin{vmatrix} 1 & 2 \\ 3 & 4 \\ \end{vmatrix} $
$ \begin{Vmatrix} 1 & 2 \\ 3 & 4 \\ \end{Vmatrix} $
````

## 带省略符号的矩阵

使用 `\cdots`、`\ddots`、`\vdots` 来输入省略符号。

````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info
```latex
$$
\begin{pmatrix}
    1 & a_1 & a_1^2 & \cdots & a_1^n \\
    1 & a_2 & a_2^2 & \cdots & a_2^n \\
    \vdots & \vdots & \vdots & \ddots & \vdots \\
    1 & a_m & a_m^2 & \cdots & a_m^n \\
\end{pmatrix}
$$
```
---
$$
\begin{pmatrix}
    1 & a_1 & a_1^2 & \cdots & a_1^n \\
    1 & a_2 & a_2^2 & \cdots & a_2^n \\
    \vdots & \vdots & \vdots & \ddots & \vdots \\
    1 & a_m & a_m^2 & \cdots & a_m^n \\
\end{pmatrix}
$$
````

## 带分割符号的矩阵

````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info
```latex
$$
\left[
    \begin{array}{cc|c}
        1 & 2 & 3 \\
        4 & 5 & 6 \\
    \end{array}
\right]
$$
```
---
$$
\left[
    \begin{array}{cc|c}
        1 & 2 & 3 \\
        4 & 5 & 6 \\
    \end{array}
\right]
$$
````

其中 `cc|c` 代表在一个三列矩阵中的第二和第三列之间插入分割线。

## 行中矩阵

若想在一行内显示矩阵，使用 `\bigl(\begin{smallmatrix} ... \end{smallmatrix}\bigr)`。

````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info
```latex
这是一个行中矩阵的示例 $\bigl(\begin{smallmatrix} a & b \\ c & d \end{smallmatrix}\bigr)$ 。
```
---
这是一个行中矩阵的示例 $\bigl(\begin{smallmatrix} a & b \\ c & d \end{smallmatrix}\bigr)$ 。
````