# 基础

## **上下标**
`^ `表示上标, `_` 表示下标。如果上下标的内容多于一个字符，需要用 `{}`将这些内容括成一个整体。上下标可以嵌套，也可以同时使用。     
例子：
`$$ x^{y^z}=(1+{\rm e}^x)^{-2xy^w} $$`     
显示：

$$ x^{y^z}=(1+{\rm e}^x)^{-2xy^w} $$

另外，如果要在左右两边都有上下标，可以用` \sideset` 命令

- 例子：
`$$ \sideset{^1_2}{^3_4}\bigotimes $$`
- 显示：

$$ \sideset{^1_2}{^3_4}\bigotimes $$

## **括号和分隔符**
`()`、`[] `和` | `表示符号本身，使用 `\{\}` 来表示 `{} `。当要显示大号的括号或分隔符时，要用 `\left` 和 `\right` 命令。
一些特殊的括号：

|输入|显示|
|:---------:|:----------:|
|`$$\langle表达式\rangle$$`|$$\langle表达式 \rangle$$|
|`$$\lceil表达式\rceil$$`|$$\lceil表达式 \rceil$$|
|`$$\lfloor表达式\rfloor$$`|$$\lfloor表达式 \rfloor$$|
|`$$\lbrace表达式\rbrace$$`|$$\lbrace表达式 \rbrace$$|

例子：
`$$ f(x,y,z) = 3y^2z \left( 3+\frac{7x+5}{1+y^2} \right) $$`     
显示：
$$ f(x,y,z) = 3y^2z \left( 3+\frac{7x+5}{1+y^2} \right) $$

## **分数**
通常使用 `\frac {分子} {分母} `命令产生一个分数\frac {分子} {分母}，分数可嵌套。 
便捷情况可直接输入 `\frac ab `来快速生成一个\frac ab。 
如果分式很复杂，亦可使用 分子 \over 分母 命令，此时分数仅有一层。

例子：

`$$\frac{a-1}{b-1} \quad  and  \quad {a+1\over b+1}$$`
$$\frac{a-1}{b-1} \quad   and   \quad {a+1\over b+1}$$

## **开方**
使用 `\sqrt [根指数，省略时为2] {被开方数} `命令输入开方。

例子：

`$$\sqrt{2} \quad and \quad \sqrt[n]{3}$$`
$$\sqrt{2} \quad and \quad \sqrt[n]{3}$$

## **省略号**
数学公式中常见的省略号有两种，\ldots 表示与文本底线对齐的省略号，\cdots 表示与文本中线对齐的省略号。

例子：

`$$f(x_1,x_2,\underbrace{\ldots}_{\rm ldots} ,x_n) = x_1^2 + x_2^2 + \underbrace{\cdots}_{\rm cdots} + x_n^2$$`

显示：
$$f(x_1,x_2,\underbrace{\ldots}_{\rm ldots} ,x_n) = x_1^2 + x_2^2 + \underbrace{\cdots}_{\rm cdots} + x_n^2$$

## **矢量**
使用 `\vec{矢量} `来自动产生一个矢量。也可以使用 `\overrightarrow `等命令自定义字母上方的符号。

例子：

`$$\vec{a} \cdot \vec{b}=0$$`

显示：
$$\vec{a} \cdot \vec{b}=0$$

例子：

`$$\overleftarrow{xy} \quad and \quad \overleftrightarrow{xy} \quad and \quad \overrightarrow{xy}$$`

显示：
$$\overleftarrow{xy} \quad and \quad \overleftrightarrow{xy} \quad and \quad \overrightarrow{xy}$$

## **积分**
使用 \int_积分下限^积分上限 {被积表达式} 来输入一个积分。

例子：

`$$\int_0^1 {x^2} \,{\rm d}x$$`

显示：
$$\int_0^1 {x^2} \,{\rm d}x$$

## **极限运算**
使用` \lim_{变量 \to 表达式} 表达式` 来输入一个极限。如有需求，可以更改 `\to` 符号至任意符号。

例子：

`$$ \lim_{n \to +\infty} \frac{1}{n(n+1)} \quad and \quad \lim_{x\leftarrow{示例}} \frac{1}{n(n+1)} $$`

显示：
$$ \lim_{n \to +\infty} \frac{1}{n(n+1)} \quad and \quad \lim_{x\leftarrow{示例}} \frac{1}{n(n+1)} $$

## **累加、累乘运算**
使用 `\sum_{下标表达式}^{上标表达式} {累加表达式} `来输入一个累加。 
与之类似，使用 `\prod \bigcup \bigcap `来分别输入累乘、并集和交集。 
此类符号在行内显示时上下标表达式将会移至右上角和右下角。

例子：

`$$\sum_{i=1}^n \frac{1}{i^2} \quad and \quad \prod_{i=1}^n \frac{1}{i^2} \quad and \quad \bigcup_{i=1}^{2} R$$`

显示：
$$\sum_{i=1}^n \frac{1}{i^2} \quad and \quad \prod_{i=1}^n \frac{1}{i^2} \quad and \quad \bigcup_{i=1}^{2} R$$

## **希腊字母**
输入 `\小写希腊字母英文全称 `和` \首字母大写希腊字母英文全称 `来分别输入小写和大写希腊字母。 
对于大写希腊字母与现有字母相同的，直接输入大写字母即可。

|输入|显示|输入|显示|
|:--------:|:--------:|:----------:|:--------:|
|`$\alpha$`|$\alpha$|`$A$`|$A$|
|`$\beta$`|$\beta$|`$B$`|$B$|
|`$\gamma$`|$\gamma$|`$\Gamma$`|$\Gamma$|
|`$\delta$`|$\delta$|`$\Delta$`|$\Delta$|
|`$\epsilon$`|$\epsilon$|`$E$`|$E$|
|`$\zeta$`|$\zeta$|`$Z$`|$Z$|
|`$\eta$`|$\eta$|`$H$`|$H$|
|`$\theta$`|$\theta$|`$\Theta$`|$\Theta$|
|`$\iota$`|$\iota$|`$I$`|$I$|
|`$\kappa$`|$\kappa$|`$K$`|$K$|
|`$\lambda$`|$\lambda$|`$\Lambda$`|$\Lambda$|
|`$\nu$`|$\nu$|`$N$`|$N$|
|`$\mu$`|$\mu$|`$M$`|$M$|
|`$\xi$`|$\xi$|`$\Xi$`|$\Xi$|
|`$o$`|$o$|`$O$`|$O$|
|`$\pi$`|$\pi$|`$\Pi$`|$\Pi$|
|`$\rho$`|$\rho$|`$P$`|$P$|
|`$\sigma$`|$\sigma$|`$\Sigma$`|$\Sigma$|
|`$\tau$`|$\tau$|`$T$`|$T$|
|`$\upsilon$`|$\upsilon$|`$\Upsilon$`|$\Upsilon$|
|`$\phi$`|$\phi$|`$\Phi$`|$\Phi$|
|`$\chi$`|$\chi$|`$X$`|$X$|
|`$\psi$`|$\psi$|`$\Psi$`|$\Psi$|
|`$\omega$`|$\omega$|`$\Omega$`|$\Omega$|

## 大括号和行标的使用

使用 `\left `和 `\right `来创建自动匹配高度的 (圆括号)，[方括号] 和 {花括号} 。 
在每个公式末尾前使用` \tag{行标} `来实现行标。
例子：

```
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

显示： 

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

小技巧：
- `$\smash{\displaystyle\max_{0 \leq q \leq n-1}} f(q) \le n$` 显示：
$\smash{\displaystyle\max_{0 \leq q \leq n-1}} f(q) \le n$
- `$f(x + \epsilon) \approx f(x) + f'(x) \epsilon + \mathcal{O}(\epsilon^2).$`, 显示:
$f(x + \epsilon) \approx f(x) + f'(x) \epsilon + \mathcal{O}(\epsilon^2).$
- 求导符号使用 `$\text{d}x$`, 即：$\text{d}x$


[Markdown公式（二）](http://www.cnblogs.com/q735613050/p/7474449.html)以表格的形式列出了常用符号。

更多内容参见<https://www.zybuluo.com/codeep/note/163962>

## 字体转换

若要对公式的某一部分字符进行字体转换，可以用 `{\字体 {需转换的部分字符}}` 命令，其中 `\字体` 部分可以参照下表选择合适的字体。一般情况下，公式默认为意大利体.

输入|说明|显示实例
:-:|:-:|:-:
`\rm`|罗马体|${\rm D}$
`\cal`|花体|$\cal D$
`\it`|意大利体|$\it D$
`\Bbb`|黑板粗体|$\Bbb D$
`\bf`|粗体|$\bf D$
`\mit`|数学斜体|$\mit D$
`\sf`|等线体|$\sf D$
`\scr`|手写体|$\scr D$
`\tt`|打字机体|$\tt D$
`\frak`|旧德式字体|$\frak D$
`\boldsymbol`|黑体|$\boldsymbol{X}$, $\boldsymbol{x}$

## 设定表格

```md
$$
\begin{array}{ccc|c}
a11 & a12 & a13  & b1 \\
a21 & a22  & a23 & b2  \\ 
a31 & a32  & a33 & b3  \\
\end{array}
$$
```

显示：

$$
\begin{array}{ccc|c}
a11 & a12 & a13  & b1 \\
a21 & a22  & a23 & b2  \\ 
a31 & a32  & a33 & b3  \\
\end{array}
$$

还可以表示 `$\KaTeX$` 和 `$\LaTeX$` 为 ：
$\KaTeX$  $\LaTeX$。