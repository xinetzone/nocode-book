# 其他

- `$\smash{\displaystyle\max_{0 \leq q \leq n-1}} f(q) \le n$` 显示：
$\smash{\displaystyle\max_{0 \leq q \leq n-1}} f(q) \le n$
- `$f(x + \epsilon) \approx f(x) + f'(x) \epsilon + \mathcal{O}(\epsilon^2).$`, 显示:
$f(x + \epsilon) \approx f(x) + f'(x) \epsilon + \mathcal{O}(\epsilon^2).$
- 求导符号使用 `$\text{d}x$`, 即：$\text{d}x$
- 表示 `$\LaTeX$` 为 ：$\LaTeX$

## 添加注释文字 `\text`

在 `\text {文字}` 中仍可以使用 `$公式$` 插入其它公式。

````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info

```latex
$$ f(n)= \begin{cases} n/2, & \text {if $n$ is even} \\ 3n+1, & \text{if $n$ is odd} \end{cases} $$
```
---
$$ f(n)= \begin{cases} n/2, & \text {if $n$ is even} \\ 3n+1, & \text{if $n$ is odd} \end{cases} $$
````

## 在字符间加入空格

有四种宽度的空格可以使用： `\,`、`\;`、`\quad` 和 `\qquad`，灵活使用 `\text{n 个空格}` 也可以在任意位置实现空格。

同时存在一种负空格 `\!` 用来减小字符间距，一般在物理单位中使用。
反复使用 `\!` 命令能够实现不同元素的叠加渲染。

````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info

```latex
$$
\begin{array}{c|c}
    \text{Spaces} & \text{Negative Space in Units} \\
    \hline \\
    \overbrace{a \! b}^{\text{\!}} \mid \underbrace{ab}_{\rm{default}} \mid \overbrace{a \, b}^{\text{\,}} \mid \underbrace{a \; b}_{\text{\;}} \mid \overbrace{a \quad b}^{\text{\quad}} \mid \underbrace{a \qquad b}_{\text{\qquad}} & \mathrm{N}\!\cdot\!\mathrm{m} \mid \mathrm{s}\!\cdot\!\mathrm{A} \mid \mathrm{kg}\!\cdot\!\mathrm{m}^2 \\ 
\end{array}
$$
```
---
$$
\begin{array}{c|c}
    \text{Spaces} & \text{Negative Space in Units} \\
    \hline \\
    \overbrace{a \! b}^{\text{\!}} \mid \underbrace{ab}_{\rm{default}} \mid \overbrace{a \, b}^{\text{\,}} \mid \underbrace{a \; b}_{\text{\;}} \mid \overbrace{a \quad b}^{\text{\quad}} \mid \underbrace{a \qquad b}_{\text{\qquad}} & \mathrm{N}\!\cdot\!\mathrm{m} \mid \mathrm{s}\!\cdot\!\mathrm{A} \mid \mathrm{kg}\!\cdot\!\mathrm{m}^2 \\ 
\end{array}
$$
````

一些常见的公式单位可表达如下：

````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info

```latex
$$ \mu_0=4\pi\times10^{-7} \ \left.\mathrm{\mathrm{T}\!\cdot\!\mathrm{m}}\middle/\mathrm{A}\right. $$
$$ 180^\circ=\pi \ \mathrm{rad} $$
$$ \mathrm{N_A} = 6.022\times10^{23} \ \mathrm{mol}^{-1} $$
```
---
$$ \mu_0=4\pi\times10^{-7} \ \left.\mathrm{\mathrm{T}\!\cdot\!\mathrm{m}}\middle/\mathrm{A}\right. $$
$$ 180^\circ=\pi \ \mathrm{rad} $$
$$ \mathrm{N_A} = 6.022\times10^{23} \ \mathrm{mol}^{-1} $$
````

## 更改文字颜色 `\color`

使用 `\color{颜色}{文字}` 来更改特定的文字颜色。

更改文字颜色需要浏览器支持 ，如果浏览器不知道你所需的颜色，那么文字将被渲染为黑色。支持如下颜色：

```
black		grey	
silver		white	
maroon		red	
yellow		lime	
olive		        green	
teal		        auqa	
blue		        navy	
purple		fuchsia
```

对于较新的浏览器（HTML5 & CSS3），HEX 颜色将被支持：

输入 `\color {#rgb} {text}` 来自定义更多的颜色，其中 `#rgb` 或 `#rrggbb `的 `r g b` 可输入 `0-9` 和 `a-f` 来表示红色、绿色和蓝色的纯度（饱和度）。

````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info

```latex
$$
\begin{array}{|rrrrrrrr|}\hline
    \verb+#000+ & \color{#000}{text} & & &
    \verb+#00F+ & \color{#00F}{text} & & \\
    & & \verb+#0F0+ & \color{#0F0}{text} &
    & & \verb+#0FF+ & \color{#0FF}{text} \\
    \verb+#F00+ & \color{#F00}{text} & & &
    \verb+#F0F+ & \color{#F0F}{text} & & \\
    & & \verb+#FF0+ & \color{#FF0}{text} &
    & & \verb+#FFF+ & \color{#FFF}{text} \\
\hline\end{array}
$$
```
---
$$
\begin{array}{|rrrrrrrr|}\hline
    \verb+#000+ & \color{#000}{text} & & &
    \verb+#00F+ & \color{#00F}{text} & & \\
    & & \verb+#0F0+ & \color{#0F0}{text} &
    & & \verb+#0FF+ & \color{#0FF}{text} \\
    \verb+#F00+ & \color{#F00}{text} & & &
    \verb+#F0F+ & \color{#F0F}{text} & & \\
    & & \verb+#FF0+ & \color{#FF0}{text} &
    & & \verb+#FFF+ & \color{#FFF}{text} \\
\hline\end{array}
$$
````

````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info

```latex
$$
\begin{array}{|rrrrrrrr|}\hline
    \verb+#000+ & \color{#000}{text} & \verb+#005+ & \color{#005}{text} & \verb+#00A+ & \color{#00A}{text} & \verb+#00F+ & \color{#00F}{text}  \\
    \verb+#500+ & \color{#500}{text} & \verb+#505+ & \color{#505}{text} & \verb+#50A+ & \color{#50A}{text} & \verb+#50F+ & \color{#50F}{text}  \\
    \verb+#A00+ & \color{#A00}{text} & \verb+#A05+ & \color{#A05}{text} & \verb+#A0A+ & \color{#A0A}{text} & \verb+#A0F+ & \color{#A0F}{text}  \\
    \verb+#F00+ & \color{#F00}{text} & \verb+#F05+ & \color{#F05}{text} & \verb+#F0A+ & \color{#F0A}{text} & \verb+#F0F+ & \color{#F0F}{text}  \\
\hline
    \verb+#080+ & \color{#080}{text} & \verb+#085+ & \color{#085}{text} & \verb+#08A+ & \color{#08A}{text} & \verb+#08F+ & \color{#08F}{text}  \\
    \verb+#580+ & \color{#580}{text} & \verb+#585+ & \color{#585}{text} & \verb+#58A+ & \color{#58A}{text} & \verb+#58F+ & \color{#58F}{text}  \\
    \verb+#A80+ & \color{#A80}{text} & \verb+#A85+ & \color{#A85}{text} & \verb+#A8A+ & \color{#A8A}{text} & \verb+#A8F+ & \color{#A8F}{text}  \\
    \verb+#F80+ & \color{#F80}{text} & \verb+#F85+ & \color{#F85}{text} & \verb+#F8A+ & \color{#F8A}{text} & \verb+#F8F+ & \color{#F8F}{text}  \\
\hline
    \verb+#0F0+ & \color{#0F0}{text} & \verb+#0F5+ & \color{#0F5}{text} & \verb+#0FA+ & \color{#0FA}{text} & \verb+#0FF+ & \color{#0FF}{text}  \\
    \verb+#5F0+ & \color{#5F0}{text} & \verb+#5F5+ & \color{#5F5}{text} & \verb+#5FA+ & \color{#5FA}{text} & \verb+#5FF+ & \color{#5FF}{text}  \\
    \verb+#AF0+ & \color{#AF0}{text} & \verb+#AF5+ & \color{#AF5}{text} & \verb+#AFA+ & \color{#AFA}{text} & \verb+#AFF+ & \color{#AFF}{text}  \\
    \verb+#FF0+ & \color{#FF0}{text} & \verb+#FF5+ & \color{#FF5}{text} & \verb+#FFA+ & \color{#FFA}{text} & \verb+#FFF+ & \color{#FFF}{text}  \\
\hline\end{array}
$$
```
---
$$
\begin{array}{|rrrrrrrr|}\hline
    \verb+#000+ & \color{#000}{text} & \verb+#005+ & \color{#005}{text} & \verb+#00A+ & \color{#00A}{text} & \verb+#00F+ & \color{#00F}{text}  \\
    \verb+#500+ & \color{#500}{text} & \verb+#505+ & \color{#505}{text} & \verb+#50A+ & \color{#50A}{text} & \verb+#50F+ & \color{#50F}{text}  \\
    \verb+#A00+ & \color{#A00}{text} & \verb+#A05+ & \color{#A05}{text} & \verb+#A0A+ & \color{#A0A}{text} & \verb+#A0F+ & \color{#A0F}{text}  \\
    \verb+#F00+ & \color{#F00}{text} & \verb+#F05+ & \color{#F05}{text} & \verb+#F0A+ & \color{#F0A}{text} & \verb+#F0F+ & \color{#F0F}{text}  \\
\hline
    \verb+#080+ & \color{#080}{text} & \verb+#085+ & \color{#085}{text} & \verb+#08A+ & \color{#08A}{text} & \verb+#08F+ & \color{#08F}{text}  \\
    \verb+#580+ & \color{#580}{text} & \verb+#585+ & \color{#585}{text} & \verb+#58A+ & \color{#58A}{text} & \verb+#58F+ & \color{#58F}{text}  \\
    \verb+#A80+ & \color{#A80}{text} & \verb+#A85+ & \color{#A85}{text} & \verb+#A8A+ & \color{#A8A}{text} & \verb+#A8F+ & \color{#A8F}{text}  \\
    \verb+#F80+ & \color{#F80}{text} & \verb+#F85+ & \color{#F85}{text} & \verb+#F8A+ & \color{#F8A}{text} & \verb+#F8F+ & \color{#F8F}{text}  \\
\hline
    \verb+#0F0+ & \color{#0F0}{text} & \verb+#0F5+ & \color{#0F5}{text} & \verb+#0FA+ & \color{#0FA}{text} & \verb+#0FF+ & \color{#0FF}{text}  \\
    \verb+#5F0+ & \color{#5F0}{text} & \verb+#5F5+ & \color{#5F5}{text} & \verb+#5FA+ & \color{#5FA}{text} & \verb+#5FF+ & \color{#5FF}{text}  \\
    \verb+#AF0+ & \color{#AF0}{text} & \verb+#AF5+ & \color{#AF5}{text} & \verb+#AFA+ & \color{#AFA}{text} & \verb+#AFF+ & \color{#AFF}{text}  \\
    \verb+#FF0+ & \color{#FF0}{text} & \verb+#FF5+ & \color{#FF5}{text} & \verb+#FFA+ & \color{#FFA}{text} & \verb+#FFF+ & \color{#FFF}{text}  \\
\hline\end{array}
$$
````

## 添加删除线

使用删除线功能必须声明 `$$` 符号。

在公式内使用 `\require{cancel}` 来允许片段删除线的显示。
声明片段删除线后，使用 `\cancel{字符}`、`\bcancel{字符}`、`\xcancel{字符}` 和 `\cancelto{字符}` 来实现各种片段删除线效果。

````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info
```latex
$$
\require{cancel}
\begin{array}{rl}
    \verb|y+\cancel{x}| & y+\cancel{x} \\
    \verb|\cancel{y+x}| & \cancel{y+x} \\
    \verb|y+\bcancel{x}| & y+\bcancel{x} \\
    \verb|y+\xcancel{x}| & y+\xcancel{x} \\
    \verb|y+\cancelto{0}{x}| & y+\cancelto{0}{x} \\
    \verb+\frac{1\cancel9}{\cancel95} = \frac15+& \frac{1\cancel9}{\cancel95} = \frac15 \\
\end{array}
$$
```
---
$$
\require{cancel}
\begin{array}{rl}
    \verb|y+\cancel{x}| & y+\cancel{x} \\
    \verb|\cancel{y+x}| & \cancel{y+x} \\
    \verb|y+\bcancel{x}| & y+\bcancel{x} \\
    \verb|y+\xcancel{x}| & y+\xcancel{x} \\
    \verb|y+\cancelto{0}{x}| & y+\cancelto{0}{x} \\
    \verb+\frac{1\cancel9}{\cancel95} = \frac15+& \frac{1\cancel9}{\cancel95} = \frac15 \\
\end{array}
$$
````

使用 `\require{enclose}` 来允许整段删除线的显示。
声明整段删除线后，使用 `\enclose{删除线效果}{字符}` 来实现各种整段删除线效果。
其中，删除线效果有 `horizontalstrike`、`verticalstrike`、`updiagonalstrike` 和 `downdiagonalstrike`，可叠加使用。

````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info
```latex
$$
\require{enclose}
\begin{array}{rl}
    \verb|\enclose{horizontalstrike}{x+y}| & \enclose{horizontalstrike}{x+y} \\
    \verb|\enclose{verticalstrike}{\frac xy}| & \enclose{verticalstrike}{\frac xy} \\
    \verb|\enclose{updiagonalstrike}{x+y}| & \enclose{updiagonalstrike}{x+y} \\
    \verb|\enclose{downdiagonalstrike}{x+y}| & \enclose{downdiagonalstrike}{x+y} \\
    \verb|\enclose{horizontalstrike,updiagonalstrike}{x+y}| & \enclose{horizontalstrike,updiagonalstrike}{x+y} \\
\end{array}
$$
```
---
$$
\require{enclose}
\begin{array}{rl}
    \verb|\enclose{horizontalstrike}{x+y}| & \enclose{horizontalstrike}{x+y} \\
    \verb|\enclose{verticalstrike}{\frac xy}| & \enclose{verticalstrike}{\frac xy} \\
    \verb|\enclose{updiagonalstrike}{x+y}| & \enclose{updiagonalstrike}{x+y} \\
    \verb|\enclose{downdiagonalstrike}{x+y}| & \enclose{downdiagonalstrike}{x+y} \\
    \verb|\enclose{horizontalstrike,updiagonalstrike}{x+y}| & \enclose{horizontalstrike,updiagonalstrike}{x+y} \\
\end{array}
$$
````

此外， \enclose 命令还可以产生包围的边框和圆等，参见 [MathML Menclose Documentation](https://developer.mozilla.org/en-US/docs/Web/MathML/Element/menclose) 以查看更多效果。

`````{admonition} 分别使用 circle 和 roundedbox 包围的公式
````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info
```latex
$$
\require{enclose}
\begin{array}{c}
    \enclose{circle}{f(\top),\, f^2(\top),\, f^3(\top) \,\cdots\, f^n(\top)} \\
    \enclose{roundedbox}{f(\bot),\, f^2(\bot),\, f^3(\bot) \,\cdots\, f^n(\bot)} \\
\end{array}
$$
```
````
---
$$
\require{enclose}
\begin{array}{c}
    \enclose{circle}{f(\top),\, f^2(\top),\, f^3(\top) \,\cdots\, f^n(\top)} \\
    \enclose{roundedbox}{f(\bot),\, f^2(\bot),\, f^3(\bot) \,\cdots\, f^n(\bot)} \\
\end{array}
$$
`````

`````{admonition} 使用 box 框住所有公式
````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info
```latex
$$
\require{enclose}
\enclose{box}{
    \begin{array}{c}
        f(\top),\, f^2(\top),\, f^3(\top) \,\cdots\, f^n(\top) \\
        f(\bot),\, f^2(\bot),\, f^3(\bot) \,\cdots\, f^n(\bot) \\
    \end{array}
}
$$
```
````
---
$$
\require{enclose}
\enclose{box}{
    \begin{array}{c}
        f(\top),\, f^2(\top),\, f^3(\top) \,\cdots\, f^n(\top) \\
        f(\bot),\, f^2(\bot),\, f^3(\bot) \,\cdots\, f^n(\bot) \\
    \end{array}
}
$$
`````