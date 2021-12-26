# 1. 如何输入括号和分隔符
## `()` 、 `[]` 和 `|` 表示自己， `{}` 表示 `{}` 。当要显示大号的括号或分隔符时，要用 `\left` 和 `\right` 命令。    
例子：`$$f(x,y,z) = 3y^2z \left( 3+\frac{7x+5}{1+y^2} \right)$$` ,显示：
$$f(x,y,z) = 3y^2z \left( 3+\frac{7x+5}{1+y^2} \right)$$ 

## 有时候要用`\left.`或`\right.`进行匹配而不显示本身。       
例子：`$$\left. \frac{ {\rm d}u}{ {\rm d}x} \right| _{x=0}$$`,显示：
$$\left. \frac{ {\rm d}u}{ {\rm d}x} \right| _{x=0}$$

## 1.1 偏导

`$$\frac{\partial^{2}y}{\partial x^{2}}$$`
$$\frac{\partial^{2}y}{\partial x^{2}}$$

## 2. 运算符：

关系运算符|markdown语言|集合运算符|markdown语言
:-:|:-:|:-:|:-:
$\pm$|`$\pm$`|$\emptyset$|`$\emptyset$`
$\times$|`$\times$`|$\in$|`$\in$`
$\div$|`$\div$`|$\notin$|`$\notin$`|$\ln$
$\mid$|`$\mid$`|$\subset$|`$\subset$`
$\nmid$|`$\nmid$`|$\supset$|`$\supset$`
$\cdot$|`$\cdot$`|$\subseteq$|`$\subseteq$`
$\circ$|`$\circ$`|$\supseteq$|`$\supseteq$`
$\ast$|`$\ast$`|$\bigcap$|`$\bigcap$`
$\bigodot$|`$\bigodot$`|$\bigcup$|`$\bigcup$`
$\bigotimes$|`$\bigotimes$`|$\bigvee$|`$\bigvee$`
$\bigoplus$|`$\bigoplus$`|$\bigvee$|`$\bigvee$`
$\leq$|`$\leq$`|$\bigwedge$|`$\bigwedge$`
$\geq$|`$\geq$`|$\biguplus$|`$\biguplus$`
$\neq$|`$\neq$`|$\bigsqcup$|`$\bigsqcup$`
$\approx$|`$\approx$`|
$\equiv$|`$\equiv$`|$\ll$|`$\ll$`|$\gg$|`$\gg$`
$\sum$|`$\sum$`
$\prod$|`$\prod$`|$\sim$|`$\sim$`
$\coprod$|`$\coprod$`|$\backsim$|`$\backsim$`
$\prec$ $\preceq$ $\succ$ $\succeq$|`$\prec$ $\preceq$ $\succ$ $\succeq$`

对数运算符|markdown语言|戴帽符号|markdown语言|连线符号|markdown语言
:-:|:-:|:-:|:-:|:-:|:-:
$\log$|`$\log$`|$\hat{y}$|`$\hat{y}$`|$\overline{a+b+c+d}$|`$\overline{a+b+c+d}$`
$\lg$|`$\lg$`|$\check{y}$|`$\check{y}$`|$\underline{a+b+c+d}$|`$\underline{a+b+c+d}$`
$\ln$|`$\ln$`|$\breve{y}$|`$\breve{y}$`|$\overbrace{a+\underbrace{b+c}{1.0}+d}^{2.0}$|`$\overbrace{a+\underbrace{b+c}{1.0}+d}^{2.0}$`


----


|三角运算符|markdown语言|微积分运算符|markdown语言|逻辑运算符|markdown语言|
|:-:|:-:|:-:|:-:|:-:|:-:|
|$\bot$|`$\bot$`|$\prime$|`$\prime$`|$\because$|`$\because$`|
|$\angle$|`$\angle$`|$\int$|`$\int$`|$\therefore$|`$\therefore$`|
|$30^\circ$|`$30^\circ$`|$\iint$|`$\iint$`|$\forall$|`$\forall$`|
|$\sin$|`$\sin$`|$\iiint$|`$\iiint$`|$\exists$|`$\exists$`|
|$\cos$|`$\cos$`|$\iiiint$|`$\iiiint$`|$\not=$|`$\not=$`|
|$\tan$|`$\tan$`|$\oint$|`$\oint$`|$\not>$|`$\not>$`|
|$\cot$|`$\cot$`|$\lim$|`$\lim$`|$\not\subset$|`$\not\subset$`|
|$\sec$|`$\sec$`|$\infty$|`$\infty$`|
|$\csc$|`$\csc$`|$\nabla$|`$\nabla$`|

|箭头符号|markdown语言|
|:-:|:-:|
|$\uparrow$|`$\uparrow$`|
|$\downarrow$|`$\downarrow$`|
|$\Uparrow$|`$\Uparrow$`|
|$\Downarrow$|`$\Downarrow$`|
|$\rightarrow$|`$\rightarrow$`|
|$\leftarrow$|`$\leftarrow$`|
|$\Rightarrow$|`$\Rightarrow$`|
|$\Leftarrow$|`$\Leftarrow$`|
|$\longrightarrow$|`$\longrightarrow$`|
|$\longleftarrow$|`$\longleftarrow$`|
|$\Longrightarrow$|`$\Longrightarrow$`|
|$\Longleftarrow$|`$\Longleftarrow$`|
|$f: {\mathbf x_t} \mapsto {\mathbf y_t}$|`$f: {\mathbf x_t} \mapsto {\mathbf y_t}$`|
|$\Longleftrightarrow$|`\Longleftrightarrow`|

更多关于箭头的符号见：[MathJax 支持的 Latex 符号总结(各种箭头符号)](https://blog.csdn.net/liyuanbhu/article/details/51473886)


