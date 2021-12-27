# 特殊符号

本节收录一些特殊符号。

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

## 希腊字母

输入 `\小写希腊字母英文全称` 和 `\首字母大写希腊字母英文全称` 来分别输入小写和大写希腊字母。对于大写希腊字母与现有字母相同的，直接输入大写字母即可。

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

## 运算符

关系运算符|markdown|集合运算符|markdown
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

对数运算符|markdown|戴帽符号|markdown|连线符号|markdown
:-:|:-:|:-:|:-:|:-:|:-:
$\log$|`$\log$`|$\hat{y}$|`$\hat{y}$`|$\overline{a+b+c+d}$|`$\overline{a+b+c+d}$`
$\lg$|`$\lg$`|$\check{y}$|`$\check{y}$`|$\underline{a+b+c+d}$|`$\underline{a+b+c+d}$`
$\ln$|`$\ln$`|$\breve{y}$|`$\breve{y}$`|$\overbrace{a+\underbrace{b+c}{1.0}+d}^{2.0}$|`$\overbrace{a+\underbrace{b+c}{1.0}+d}^{2.0}$`

|三角运算符|markdown|微积分运算符|markdown|逻辑运算符|markdown|
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

|箭头符号|markdown|
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

-  $\boldsymbol{\hat y} = \boldsymbol{W} \boldsymbol{x}$ 的输入
代码：
```latex
$\boldsymbol{\hat y} = \boldsymbol{W} \boldsymbol{x}$
```

- $\ell_p$ 范数: `$\ell_p$`

对于一些特殊的数学符号可以使用 `\operatorname{}` 或者 `\text{}` 来进行转换，如：`$\text{cov}$` 和 `$\operatorname{s.t.}$` 便显示为：$\text{cov}$ 和 $\operatorname{s.t.}$



还有：

```latex
$A \xrightarrow{f} B \; a \; \bot b \; \overset{def}{=}$ 
```
$A \xrightarrow{f} B \; a \; \bot b \; \overset{def}{=}$ 

```latex
$$
 \underset{x\in S\subseteq X}{\operatorname{arg\,max}}\, f(x) := \{x \mid x\in S \wedge \forall y \in S : f(y) \le f(x)\}.   
$$
```

$$
 \underset{x\in S\subseteq X}{\operatorname{arg\,max}}\, f(x) := \{x \mid x\in S \wedge \forall y \in S : f(y) \le f(x)\}.   
$$

```latex
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
