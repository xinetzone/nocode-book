# 基础

本节介绍数学公式常用语法。

## **上下标**

`^` 表示上标, `_` 表示下标。如果上下标的内容多于一个字符，需要用 `{}` 将这些内容括成一个整体。上下标可以嵌套，也可以同时使用。

```{tab} 例 1
`$$ x^{y^z}=(1+{\rm e}^x)^{-2xy^w} $$`
```    
```{tab} 显示
$$ x^{y^z}=(1+{\rm e}^x)^{-2xy^w} $$
```

另外，如果要在左右两边都有上下标，可以用 `\sideset` 命令

```{tab} 例 2
`$$ \sideset{^1_2}{^3_4}\bigotimes $$`
```

```{tab} 显示
$$ \sideset{^1_2}{^3_4}\bigotimes $$
```

## **括号和分隔符**

`()`、`[]` 和 ``|`` 表示符号本身，使用 `\{\}` 来表示 `{}`。当要显示大括号或分隔符时，要用 `\left` 和 `\right` 命令。一些特殊的括号：

|输入|显示|
|:---------:|:----------:|
|`$$\langle表达式\rangle$$`|$$\langle表达式 \rangle$$|
|`$$\lceil表达式\rceil$$`|$$\lceil表达式 \rceil$$|
|`$$\lfloor表达式\rfloor$$`|$$\lfloor表达式 \rfloor$$|
|`$$\lbrace表达式\rbrace$$`|$$\lbrace表达式 \rbrace$$|

```{tab} 例 3
`$$ f(x,y,z) = 3y^2z \left( 3+\frac{7x+5}{1+y^2} \right) $$`
```    
```{tab} 显示
$$ f(x,y,z) = 3y^2z \left( 3+\frac{7x+5}{1+y^2} \right) $$
```

### **大括号和行标**

使用 `\left` 和 `\right` 来创建自动匹配高度的 `(圆括号)`，`[方括号]` 和 `{花括号}`。 

在每个公式末尾前使用 `\tag{行标}` 来实现行标。

````{tab} 例 4
```latex
$$
f\left(
   \left[ 
     \frac{
       1+\left\{x,y\right\}
     }{
       \left(
          \frac{x}{y}+\frac{y}{x}
       \right)
       \left(u+1\right)
     }+a
   \right]^{3/2}
\right)
\tag{行标}
$$
```
````
```{tab} 显示
$$
f\left(
   \left[ 
     \frac{
       1+\left\{x,y\right\}
     }{
       \left(
          \frac{x}{y}+\frac{y}{x}
       \right)
       \left(u+1\right)
     }+a
   \right]^{3/2}
\right)
\tag{行标}
$$
```

有时候要用 `\left.` 或 `\right.` 进行匹配而不显示本身。   

````{tab} 例 5
`$$\left. \frac{ {\rm d}u}{ {\rm d}x} \right| _{x=0}$$`
````
````{tab} 显示
$$\left. \frac{ {\rm d}u}{ {\rm d}x} \right| _{x=0}$$
````

## 偏导

````{tab} 例 6
`$$\frac{\partial^{2}y}{\partial x^{2}}$$`
````
````{tab} 显示
$$\frac{\partial^{2}y}{\partial x^{2}}$$
````

## **分数**

通常使用 `\frac {分子} {分母}` 命令产生一个分数 $\frac {分子} {分母}$，分数可嵌套。

便捷情况可直接输入 `\frac ab` 来快速生成一个 $\frac ab$。如果分式很复杂，亦可使用 `分子 \over 分母` 命令，此时分数仅有一层。

```{tab} 例 7
`$$\frac{a-1}{b-1} \quad  \text{and}  \quad {a+1\over b+1}$$`
```

```{tab} 显示
$$\frac{a-1}{b-1} \quad   \text{and}   \quad {a+1\over b+1}$$
```

## **开方**

使用 `\sqrt [根指数，省略时为2] {被开方数}` 命令开方。

```{tab} 例 8
`$$\sqrt{2} \quad \text{and} \quad \sqrt[n]{3}$$`
```
```{tab} 显示
$$\sqrt{2} \quad \text{and} \quad \sqrt[n]{3}$$
```

## **省略号**

数学公式中常见的省略号有两种，`\ldots` 表示与文本底线对齐的省略号，`\cdots` 表示与文本中线对齐的省略号。

```{tab} 例 9
`$$f(x_1,x_2,\underbrace{\ldots}_{\rm ldots} ,x_n) = x_1^2 + x_2^2 + \underbrace{\cdots}_{\rm cdots} + x_n^2$$`
```
```{tab} 显示
$$f(x_1,x_2,\underbrace{\ldots}_{\rm ldots} ,x_n) = x_1^2 + x_2^2 + \underbrace{\cdots}_{\rm cdots} + x_n^2$$
```

## **矢量**

使用 `\vec{矢量}` 来自动产生一个矢量。也可以使用 `\overrightarrow ` 等命令自定义字母上方的符号。

```{tab} 例 10
`$$\vec{a} \cdot \vec{b}=0$$`
```
```{tab} 显示
$$\vec{a} \cdot \vec{b}=0$$
```

或者

```{tab} 例 11
`$$\overleftarrow{xy} \quad \text{and} \quad \overleftrightarrow{xy} \quad and \quad \overrightarrow{xy}$$`
```
```{tab} 显示
$$\overleftarrow{xy} \quad \text{and} \quad \overleftrightarrow{xy} \quad and \quad \overrightarrow{xy}$$
```
## **积分**

使用 `\int_积分下限^积分上限 {被积表达式}` 来输入一个积分。

```{tab} 例 12
`$$\int_0^1 {x^2} \,{\rm d}x$$`
```
```{tab} 显示
$$\int_0^1 {x^2} \,{\rm d}x$$
```

## **极限**

使用 `\lim_{变量 \to 表达式} 表达式` 来输入一个极限。如有需求，可以更改 `\to` 符号至任意符号。

```{tab} 例 13
`$$ \lim_{n \to +\infty} \frac{1}{n(n+1)} \quad \text{and} \quad \lim_{x\leftarrow{示例}} \frac{1}{n(n+1)} $$`
```
```{tab} 显示
$$ \lim_{n \to +\infty} \frac{1}{n(n+1)} \quad \text{and} \quad \lim_{x\leftarrow{示例}} \frac{1}{n(n+1)} $$
```
## **累加、累乘**

使用 `\sum_{下标表达式}^{上标表达式} {累加表达式}` 来输入一个累加。与之类似，使用 `\prod \bigcup \bigcap` 来分别输入累乘、并集和交集。此类符号在行内显示时上下标表达式将会移至右上角和右下角。

```{tab} 例 14
`$$\sum_{i=1}^n \frac{1}{i^2} \quad \text{and} \quad \prod_{i=1}^n \frac{1}{i^2} \quad \text{and} \quad \bigcup_{i=1}^{2} R$$`
```
```{tab} 显示
$$\sum_{i=1}^n \frac{1}{i^2} \quad \text{and} \quad \prod_{i=1}^n \frac{1}{i^2} \quad \text{and} \quad \bigcup_{i=1}^{2} R$$
```

## **设定表格**

````{tab} 例 15
```latex
$$
\begin{array}{ccc|c}
a11 & a12 & a13  & b1 \\
a21 & a22  & a23 & b2  \\ 
a31 & a32  & a33 & b3  \\
\end{array}
$$
```
````
````{tab} 显示
$$
\begin{array}{ccc|c}
a11 & a12 & a13  & b1 \\
a21 & a22  & a23 & b2  \\ 
a31 & a32  & a33 & b3  \\
\end{array}
$$
````

## 对齐多行公式

````{tab} 例 16
```latex
$$
\begin{aligned}
a  &= b^2 + c^2\\
&= w^3 + b
\end{aligned}
$$
```
````

````{tab} 显示
$$
\begin{aligned}
a  &= b^2 + c^2\\
&= w^3 + b
\end{aligned}
$$
````

## 高亮

使用 `\bbox[底色, (可选)边距, (可选)边框 border: 框宽度 框类型 框颜色]` 命令来高亮一行公式。

底色和框颜色支持详见“更改文字颜色”，边距及框宽度支持 绝对像素 `px` 或 相对大小 `em`，框类型支持 `实线` `solid` 或 `虚线` `dashed`。

`````{panels}
:column: col-12

````{tab} 例 17
```latex
$$
\bbox[yellow]{
    e^x=\lim_{n\to\infty} \left( 1+\frac{x}{n} \right)^n \qquad (1)
}
$$
```
````

````{tab} 显示
$$
\bbox[yellow]{
    e^x=\lim_{n\to\infty} \left( 1+\frac{x}{n} \right)^n \qquad (1)
}
$$
````
---
````{tab} 例 18
```latex
$$
\bbox[#9ff, 5px]{ % 此处向外添加 5 像素的边距
    e^x=\lim_{n\to\infty} \left( 1+\frac{x}{n} \right)^n \qquad (1)
}
$$
```
````
````{tab} 显示
$$
\bbox[#9ff, 5px]{ % 此处向外添加 5 像素的边距
    e^x=\lim_{n\to\infty} \left( 1+\frac{x}{n} \right)^n \qquad (1)
}
$$
````
---
````{tab} 例 19
```latex
$$
% 此处使用 0.5 倍行高作为边距，附加 2 像素的实线边框（Ctrl+Alt+Y 可见）
\bbox[#2f3542, 0.5em, border:2px solid #f1f2f6]{
    \color{#f1f2f6}{e^x=\lim_{n\to\infty} \left( 1+\frac{x}{n} \right)^n \qquad (1)}
}
$$
```
````
````{tab} 显示
$$
% 此处使用 0.5 倍行高作为边距，附加 2 像素的实线边框（Ctrl+Alt+Y 可见）
\bbox[#2f3542, 0.5em, border:2px solid #f1f2f6]{
    \color{#f1f2f6}{e^x=\lim_{n\to\infty} \left( 1+\frac{x}{n} \right)^n \qquad (1)}
}
$$
````
`````
