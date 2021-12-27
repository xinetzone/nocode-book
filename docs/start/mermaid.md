# Mermaid

在 [`VS code`](https://code.visualstudio.com/) 中安装插件 `Markdown Preview Mermaid Support`，则便可支持 Mermaid

## 流程图

flowchart

```{mermaid}
graph LR;  
A-->B;
A-->C;  
B-->D;  
C-->D;
```

## 时序图

sequence diagram

```{mermaid}
sequenceDiagram
　　　participant Alice
　　　participant Bob
　　　Alice->John:Hello John, how are you?
　　　loop Healthcheck
　　　　　John->John:Fight against hypochondria
　　　end
　　　Note right of John:Rational thoughts <br/>prevail...
　　　John-->Alice:Great!
　　　John->Bob: How about you?
　　　Bob-->John: Jolly good!
```

## 甘特图

gantt diagram

```{mermaid}
gantt
　　　dateFormat　YYYY-MM-DD
　　　title Adding GANTT diagram functionality to mermaid
　　　section A section
　　　Completed task　　:done, des1, 2014-01-06,2014-01-08
　　　Active task 　　　　:active, des2, 2014-01-09, 3d
　　　future task 　　　　:　　　  des3, after des2, 5d
　　　future task2　　　　:　　　  des4, after des3, 5d
　　　section Critical tasks
　　　Completed task in the critical line　:crit, done, 2014-01-06,24h
　　　Implement parser and json　　　　　　:crit, done, after des1, 2d
　　　Create tests for parser　　　　　　　:crit, active, 3d
　　　Future task in critical line　　　　　:crit, 5d
　　　Create tests for renderer　　　　　　:2d
　　　Add to ,mermaid　　　　　　　　　　　:1d
```

## Graph

```md
graph LR
    A --> B
```

这是申明一个由左到右，水平向右的图。

```{mermaid}
graph LR
A -->B
```

可能方向有：

- `TB` - top bottom
- `BT` - bottom top
- `RL` - right left
- `LR` - left right
- `TD` - same as TB

### 节点与形状

#### 默认节点

```md
graph LR
id1  
```

- [x] 注意：`id` 显示在节点内部。

```{mermaid}
graph LR
id1
```

#### 文本节点

```md
graph LR
id[This is the text in the box];
```

展示如下：

```{mermaid}
graph LR
id[This is the text in the box];
```

#### 圆角节点

```md
graph LR
id(This is the text in the box);
```

即：

```{mermaid}
graph LR
id(This is the text in the box);
```

#### 圆节点(The form of a circle)

```md
graph LR
id((This is the text in the circle));
```

```{mermaid}
graph LR
id((This is the text in the circle));
```

#### 非对称节点(asymetric shape)

```md
graph LR
id>This is the text in the box]
```

```{mermaid}
graph LR
id>This is the text in the box]
```

#### 菱形节点(rhombus)

```md
graph LR
id{This is the text in the box}
```

```{mermaid}
graph LR
id{This is the text in the box}
```

### 连接线

节点间的连接线有多种形状，而且可以在连接线中加入标签：

#### 箭头形连接

```md
graph LR;
  A-->B;
```

```{mermaid}
graph LR;
  A-->B;
```

#### 开放行连接

```md
graph LR
A --- B
```

```{mermaid}
graph LR
A --- B
```

#### 标签连接

```md
graph LR
A -- This is the label text --- B;
```

```{mermaid}
graph LR
A -- This is the label text --- B;
```

#### 箭头标签连接

`A–>|text|B` 或者 `A– text –>B`

```{mermaid}
graph LR
 A-- text -->B
```

### 虚线(dotted link，点连线)

`-.->` 和 `-.-`

```{mermaid}
graph LR
A-.->B
```

```{mermaid}
graph LR
A-.-B
```

#### 标签虚线

```md
graph LR
A-.text.->B
```

```{mermaid}
graph LR
A-.text.->B
```

### 粗实线

`==>`

```{mermaid}
graph LR
A==>B
```

#### 标签粗线

`=\=text\==>` 和 `=\=text\===`

```{mermaid}
graph LR
A==text==>B
```

```{mermaid}
graph LR
A==text===B
```

---------------

### 特殊的语法

使用引号可以抑制一些特殊的字符的使用，可以避免一些不必要的麻烦。

```md
graph LR
d1["This is the (text) in the box"]
```

```{mermaid}
graph LR
d1["This is the (text) in the box"]
```

### html 字符的转义字符

转义字符的使用语法

流程图定义如下：

```md
graph LR
        A["A double quote:#quot;"]-->B["A dec char:#9829;"]
```

```{mermaid}
graph LR
        A["A double quote:#quot;"]-->B["A dec char:#9829;"]
```

### 子图(Subgraphs)

```md
subgraph title
graph definition
end
```

示例：

```md
graph TB
        subgraph one
        a1 --> a2
        end
        subgraph two
        b2 --> b2
        end
        subgraph three
        c1 --> c2
        end
        c1 --> a2
```

```{mermaid}
graph TB
        subgraph one
        a1 --> a2
        end
        subgraph two
        b2 --> b2
        end
        subgraph three
        c1 --> c2
        end
        c1 --> a2
```

### 基础 fontawesome 支持

想加入来自frontawesome的图表字体，详情请点击：[fontawdsome](http://fontawesome.io/)

引用的语法为：`++fa:#icon class name#++`

```md
graph TD
      B["fa:fa-twitter for peace"]
      B-->C[fa:fa-ban forbidden]
      B-->D(fa:fa-spinner);
      B-->E(A fa:fa-camerra-retro perhaps?);
```

```{mermaid}
graph TD
      B["fa:fa-twitter for peace"]
      B-->C[fa:fa-ban forbidden]
      B-->D(fa:fa-spinner);
      B-->E(A fa:fa-camerra-retro perhaps?);
```

更多参考：[mermaid docs](https://mermaidjs.github.io/)

## 图表(graph)

### 定义连接线的样式

```md
graph LR
     id1(Start)-->id2(Stop)
     style id1 fill:#f9f,stroke:#333,stroke-width:4px;
     style id2 fill:#ccf,stroke:#f66,stroke-width:2px,stroke-dasharray:5,5;
```

```{mermaid}
graph LR
     id1(Start)-->id2(Stop)
     style id1 fill:#f9f,stroke:#333,stroke-width:4px;
     style id2 fill:#ccf,stroke:#f66,stroke-width:2px,stroke-dasharray:5,5;
```

备注：上面的样式参考 CSS 样式。

### 样式类

为了方便样式的使用，可以定义类来使用样式

类的定义示例：

```md
classDef className fill:#f9f,stroke:#333,stroke-width:4px;
```

对节点使用样式类：

```md
class nodeId className;
```

同时对多个节点使用相同的样式类：

```md
class nodeId1,nodeId2 className;
```

可以在CSS中提前定义样式类，应用在图表的定义中。

```md
graph LR
      A-->B[AAABBB];
      B-->D;
      class A cssClass;
```

#### 默认样式类：

当没有指定样式的时候，默认采用。

```md
classDef default fill:#f9f,stroke:#333,stroke-width:4px;
```

示例：

```md
graph LR
    classDef default fill:#f90,stroke:#555,stroke-width:4px;
    id1(Start)-->id2(Stop)
```

```{mermaid}
graph LR
    classDef default fill:#f90,stroke:#555,stroke-width:4px;
    id1(Start)-->id2(Stop)
```

## [序列图](https://en.wikipedia.org/wiki/Unified_Modeling_Language#Interaction_diagrams)(sequence diagram)

示例：

```{mermaid}
sequenceDiagram
    Alice->John: Hello John, how are you ?
    John-->Alice:Great!
    Alice->>John: dont borther me !
    John-->>Alice:Great!
    Alice-xJohn: wait!
    John--xAlice: Ok!
```

```md
sequenceDiagram
    Alice->John: Hello John, how are you ?
    John-->Alice:Great!
    Alice->>John: dont borther me !
    John-->>Alice:Great!
    Alice-xJohn: wait!
    John--xAlice: Ok!
```

如果想让 John 出现在前面，mermaid 通过设定参与者(participants)的顺序控制二者的顺序。上面的图可以做如下修改：

```md
sequenceDiagram
　　participant John
　　participant Alice
　　Alice-xJohn:Hello John,how are you?
　　John-->>Alice:Great!
```

```{mermaid}
sequenceDiagram
　　participant John
　　participant Alice
　　Alice-xJohn:Hello John,how are you?
　　John-->>Alice:Great!
```

箭头的六种样式：
- `->`
- `–>`
- `->>`
- `–>>`
- `-x`
- `–x`

### 便签

给序列图增加便签：

具体规则：

```md
[right of | left of | over][Actor]:Text
```

示例：

```md
sequenceDiagram
　　participant John
　　Note left of John: Text in note
```

```{mermaid}
sequenceDiagram
　　participant John
　　Note left of John: Text in note
```

跨越两个 Actor 的便签：

```md
sequenceDiagram
　　Alice->John:Hello John, how are you?
　　Note over Alice,John:A typical interaction
```

```{mermaid}
sequenceDiagram
　　Alice->John:Hello John, how are you?
　　Note over Alice,John:A typical interaction
```

### 循环 Loops

在序列图中，也可以使用循环，具体规则如下：

```md
loop Loop text
... statements...
end
```

示例：

```md
sequenceDiagram
　　Alice->>John: Hello!
　　loop Reply every minute
　　　　John->>Alice:Great!
　　end
```

```{mermaid}
sequenceDiagram
　　Alice->>John: Hello!
　　loop Reply every minute
　　　　John->>Alice:Great!
　　end
```

### 选择 ALT

在序列图中选择的表达。规则如下：

```md
alt Describing text
...statements...
else
...statements...
end
```

或者使用 `opt` (推荐在没有 `else` 的情况下使用)

```md
opt Describing text
...statements...
end
```

示例：

```md
sequenceDiagram
　　Alice->>Bob: Hello Bob, how are you?
　　alt is sick
　　　　Bob->>Alice:not so good :(
　　else is well
　　　　Bob->>Alice:Feeling fresh like a daisy:)
　　end
　　opt Extra response
　　　　Bob->>Alice:Thanks for asking
　　end
```

```{mermaid}
sequenceDiagram
　　Alice->>Bob: Hello Bob, how are you?
　　alt is sick
　　　　Bob->>Alice:not so good :(
　　else is well
　　　　Bob->>Alice:Feeling fresh like a daisy:)
　　end
　　opt Extra response
　　　　Bob->>Alice:Thanks for asking
　　end
```

## 甘特图(gantt)

甘特图是一类条形图，由 Karol Adamiechi 在 1896 年提出, 而在 1910 年 Henry Gantt 也独立的提出了此种图形表示。通常用在对项目终端元素和总结元素的开始及完成时间进行的描述。
示例：

```md
gantt
dateFormat YYYY-MM-DD

section S1
T1: 2014-01-01, 9d

section S2
T2: 2014-01-11, 9d

section S3
T3: 2014-01-02, 9d
```

```{mermaid}
gantt
dateFormat YYYY-MM-DD

section S1
T1: 2014-01-01, 9d

section S2
T2: 2014-01-11, 9d

section S3
T3: 2014-01-02, 9d
```

更加丰富的：

```md
gantt
    dateFormat  YYYY-MM-DD
    title Adding GANTT diagram functionality to mermaid

    section A section
    Completed task            :done,    des1, 2014-01-06,2014-01-08
    Active task               :active,  des2, 2014-01-09, 3d
    Future task               :         des3, after des2, 5d
    Future task2              :         des4, after des3, 5d

    section Critical tasks
    Completed task in the critical line :crit, done, 2014-01-06,24h
    Implement parser and jison          :crit, done, after des1, 2d
    Create tests for parser             :crit, active, 3d
    Future task in critical line        :crit, 5d
    Create tests for renderer           :2d
    Add to mermaid                      :1d

    section Documentation
    Describe gantt syntax               :active, a1, after des1, 3d
    Add gantt diagram to demo page      :after a1  , 20h
    Add another diagram to demo page    :doc1, after a1  , 48h

    section Last section
    Describe gantt syntax               :after doc1, 3d
    Add gantt diagram to demo page      : 20h
    Add another diagram to demo page    : 48h
```

```{mermaid}
gantt
    dateFormat  YYYY-MM-DD
    title Adding GANTT diagram functionality to mermaid

    section A section
    Completed task            :done,    des1, 2014-01-06,2014-01-08
    Active task               :active,  des2, 2014-01-09, 3d
    Future task               :         des3, after des2, 5d
    Future task2              :         des4, after des3, 5d

    section Critical tasks
    Completed task in the critical line :crit, done, 2014-01-06,24h
    Implement parser and jison          :crit, done, after des1, 2d
    Create tests for parser             :crit, active, 3d
    Future task in critical line        :crit, 5d
    Create tests for renderer           :2d
    Add to mermaid                      :1d

    section Documentation
    Describe gantt syntax               :active, a1, after des1, 3d
    Add gantt diagram to demo page      :after a1  , 20h
    Add another diagram to demo page    :doc1, after a1  , 48h

    section Last section
    Describe gantt syntax               :after doc1, 3d
    Add gantt diagram to demo page      : 20h
    Add another diagram to demo page    : 48h
```

header 1 | header 2
---------|----------
 `title` | 标题
 `dateFormat` | 日期格式
 `section` | 模块
 `Completed` | 已经完成
 `Active` | 当前正在进行
 `Future` | 后续待处理
 `crit` | 关键阶段
 `日期缺失` | 默认从上一项完成后

 关于日期的格式可以参考：

- [string-format](http://momentjs.com/docs/#/parsing/string-format/)
- [Time-Formatting](https://github.com/mbostock/d3/wiki/Time-Formatting)

范例

```md
graph TB
    sq[Square shape] --> ci((Circle shape))

    subgraph A subgraph
        di{Diamond with  line break} -.-> ro(Rounded)
        di==>ro2(Rounded square shape)
    end

    e --> od3>Really long text with linebreak<br>in an Odd shape]

    cyr[Cyrillic]-->cyr2((Circle shape Начало));

    classDef green fill:#9f6,stroke:#333,stroke-width:2px;
    classDef orange fill:#f96,stroke:#333,stroke-width:4px;
    class sq,e green
    class di orange
```

```{mermaid}
graph TB
    sq[Square shape] --> ci((Circle shape))

    subgraph A subgraph
        di{Diamond with  line break} -.-> ro(Rounded)
        di==>ro2(Rounded square shape)
    end

    e --> od3>Really long text with linebreak<br>in an Odd shape]

    cyr[Cyrillic]-->cyr2((Circle shape Начало));

    classDef green fill:#9f6,stroke:#333,stroke-width:2px;
    classDef orange fill:#f96,stroke:#333,stroke-width:4px;
    class sq,e green
    class di orange
```

## 一个小 Bug

在 Markdown 模式下

    ```{mermaid}
    graph TB
    id[a]
    ```

与 LaTex 公式不能实现混编, 否则, 公式将不能正确显示.

若要与 LaTex 实现混编, 只需要将其改为下面的形式即可
```md
<div class="mermaid">graph LR;  
id[a]
</div>
```