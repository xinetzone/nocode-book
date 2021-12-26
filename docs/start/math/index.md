# 数学

```{toctree}
:maxdepth: 2
:hidden:

basic
raw
raw1
raw2
raw3
```

- `$` 表示行内公式：

    ````{panels}
    :container: container-fluid pb-1
    :column: col-12
    :card: + shadow
    :header: border-0 bg-info
    
    myst
    ^^^
    ```
    质能守恒方程可以用一个很简洁的方程式 $E=mc^2$ 来表达。
    ```
    ---
    预览
    ^^^
    质能守恒方程可以用一个很简洁的方程式 $E=mc^2$ 来表达。
    ````

- `$$` 表示整行公式：

    ````{panels}
    :container: container-fluid pb-1
    :column: col-12
    :card: + shadow
    :header: border-0 bg-info
    
    myst
    ^^^
    ```
    $$\sum_{i=1}^n a_i=0$$

    $$f(x_1,x_x,\ldots,x_n) = x_1^2 + x_2^2 + \cdots + x_n^2 $$

    $$\sum^{j-1}_{k=0}{\widehat{\gamma}_{kj} z_k}$$
    ```
    ---
    预览
    ^^^
    $$\sum_{i=1}^n a_i=0$$

    $$f(x_1,x_x,\ldots,x_n) = x_1^2 + x_2^2 + \cdots + x_n^2 $$

    $$\sum^{j-1}_{k=0}{\widehat{\gamma}_{kj} z_k}$$
    ````


- 自动编号的公式可以用如下方法表示：

    ```
    \begin{equation}
    数学公式
    \label{eq:当前公式名}
    \end{equation}
    自动编号后的公式可在全文任意处使用 \eqref{eq:公式名} 语句引用。
    ```

    ````{panels}
    :container: container-fluid pb-1
    :column: col-12
    :card: + shadow
    :header: border-0 bg-info

    myst
    ^^^
    ```
    $ J_\alpha(x) = \sum_{m=0}^\infty \frac{(-1)^m}{m! \Gamma (m + \alpha + 1)} {\left({ \frac{x}{2} }\right)}^{2m + \alpha} \text {，行内公式示例} $
    ```
    ---
    预览
    ^^^
    $ J_\alpha(x) = \sum_{m=0}^\infty \frac{(-1)^m}{m! \Gamma (m + \alpha + 1)} {\left({ \frac{x}{2} }\right)}^{2m + \alpha} \text {，行内公式示例} $
    ---
    myst
    ^^^
    ```
    $$ J_\alpha(x) = \sum_{m=0}^\infty \frac{(-1)^m}{m! \Gamma (m + \alpha + 1)} {\left({ \frac{x}{2} }\right)}^{2m + \alpha} \text {，独立公式示例} $$
    ```
    ---
    预览
    ^^^
    $$ J_\alpha(x) = \sum_{m=0}^\infty \frac{(-1)^m}{m! \Gamma (m + \alpha + 1)} {\left({ \frac{x}{2} }\right)}^{2m + \alpha} \text {，独立公式示例} $$
    ````
