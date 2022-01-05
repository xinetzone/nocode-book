# 饼图

> 饼图（或圆图）是一种圆形的统计图形，它被分成若干片，以说明数字比例。在饼图中，每个片断的弧长（以及由此产生的中心角和面积）与它所代表的数量成正比。虽然它因类似于一个被切开的饼而被命名，但它的表现方式却有不同。最早的饼图一般归功于 1801 年 William Playfair 的《Statistical Breviary》。
——维基百科

Mermaid 可以呈现饼状图的图表。

```
pie title Pets adopted by volunteers
    "Dogs" : 386
    "Cats" : 85
    "Rats" : 15
```

```{mermaid}
pie title Pets adopted by volunteers
    "Dogs" : 386
    "Cats" : 85
    "Rats" : 15
```

## 语法

绘制饼状图在 mermaid 中真的很简单。
- 以 `pie` 关键字开始图示
- 后面有 `title` 关键字和它的字符串值，给饼图一个标题。这是 ***可选的***
- 紧随其后的是 dataSet
    - 饼图中某个部分的 `label` 在 `" "` 引号中。
    - 后面有 `:` 冒号作为分隔符
    - 后面是 `positive numeric value` （支持到小数点后两位）

```
[pie]
     [title] [titlevalue]  (OPTIONAL)
      "[datakey1]" : [dataValue1]
      "[datakey2]" : [dataValue2]
      "[datakey3]" : [dataValue3]
      .
      .
```

## 示例

```
pie
    title Key elements in Product X
    "Calcium" : 42.96
    "Potassium" : 50.05
    "Magnesium" : 10.01
    "Iron" :  5
```

```{mermaid}
pie
    title Key elements in Product X
    "Calcium" : 42.96
    "Potassium" : 50.05
    "Magnesium" : 10.01
    "Iron" :  5
```
