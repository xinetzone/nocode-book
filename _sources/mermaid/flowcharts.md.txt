# 流程图

参考：[flowchart](https://mermaid-js.github.io/mermaid/#/flowchart)

所有的流程图都是由 **节点**、**几何图形** 和 **边**、**箭头** 或 **线条** 组成。Mermaid 代码定义了这些节点和边的构成和交互方式。

它还可以容纳不同的箭头类型，多方向的箭头，以及链接到子图和从子图的边。

```{note}
不要键入单词“end”作为流程图节点。大写所有或任何一个字母，以防止流程图中断，即 "End"或 "End"。或者你也可以采用这种方法 [ workaround.**](https://github.com/mermaid-js/mermaid/issues/1444#issuecomment-639528897) 节点。
```

## 节点（默认）

````{panels}
```
flowchart LR
    id
```
---
```{mermaid}
flowchart LR
    id
```
````

### 带有文本的节点

也可以在框中设置与 `id` 不同的文本。如果多次这样做，将使用的节点找到的最后一个文本。另外，如果稍后为节点定义边，则可以省略文本定义。之前定义的将在呈现框时使用。

````{panels}
```
flowchart LR
    id1[This is the text in the box]
```
---
```{mermaid}
flowchart LR
    id1[This is the text in the box]
```
````

## 方向

此语句声明流程图的方向。

这说明流程图是从上到下（`TD` 或 `TB`）定向的。

````{panels}
```
flowchart TD
    Start --> Stop
```
---
```{mermaid}
flowchart TD
    Start --> Stop
```
````

这声明了流程图是从左到右（`LR`）的方向。

````{panels}
```
flowchart LR
    Start --> Stop
```
---
```{mermaid}
flowchart LR
    Start --> Stop
```
````

还有其他方向：

- `TB` - top to bottom
- `TD` - top-down/ same as top to bottom
- `BT` - bottom to top
- `RL` - right to left
- `LR` - left to right

## 节点形状

圆边节点：

````{panels}
```
flowchart LR
    id1(This is the text in the box)
```
---
```{mermaid}
flowchart LR
    id1(This is the text in the box)
```
````

场馆型节点：

````{panels}
```
flowchart LR
    id1([This is the text in the box])
```
---
```{mermaid}
flowchart LR
    id1([This is the text in the box])
```
````

子程序形状节点：

````{panels}
```
flowchart LR
    id1[[This is the text in the box]]
```
---
```{mermaid}
flowchart LR
    id1[[This is the text in the box]]
```
````

圆柱形节点：

````{panels}
```
flowchart LR
    id1[(Database)]
```
---
```{mermaid}
flowchart LR
    id1[(Database)]
```
````

圆形节点：

````{panels}
```
flowchart LR
    id1((This is the text in the circle))
```
---
```{mermaid}
flowchart LR
    id1((This is the text in the circle))
```
````

非对称形状的节点：

````{panels}
```
flowchart LR
    id1>This is the text in the box]
```
---
```{mermaid}
flowchart LR
    id1>This is the text in the box]
```
````

菱形节点：

````{panels}
```
flowchart LR
    id1{This is the text in the box}
```
---
```{mermaid}
flowchart LR
    id1{This is the text in the box}
```
````

六边形节点：

````{panels}
```
flowchart LR
    id1{{This is the text in the box}}
```
---
```{mermaid}
flowchart LR
    id1{{This is the text in the box}}
```
````

平行四边形节点：

````{panels}
```
flowchart TD
    id1[/This is the text in the box/]
```
---
```{mermaid}
flowchart TD
    id1[/This is the text in the box/]
```
````

反向四边形节点：

````{panels}
```
flowchart TD
    id1[\This is the text in the box\]
```
---
```{mermaid}
flowchart TD
    id1[\This is the text in the box\]
```
````

梯形节点：

````{panels}
```
flowchart TD
    A[/Christmas\]
```
---
```{mermaid}
flowchart TD
    A[/Christmas\]
```
````

反向梯形节点：

````{panels}
```
flowchart TD
    B[\Go shopping/]
```
---
```{mermaid}
flowchart TD
    B[\Go shopping/]
```
````

## 节点之间的边

节点可以用链接/边连接。可以有不同类型的边或在边上附加一个文本字符串。

带箭头的边：

````{panels}
```
flowchart LR
    A-->B
```
---
```{mermaid}
flowchart LR
    A-->B
```
````

开放边

````{panels}
```
flowchart LR
    A --- B
```
---
```{mermaid}
flowchart LR
    A --- B
```
````

带文本的边：

````{panels}
```
flowchart LR
    A-- This is the text! ---B
```
---
```{mermaid}
flowchart LR
    A-- This is the text! ---B
```
````

或者

````{panels}
```
flowchart LR
    A---|This is the text|B
```
---
```{mermaid}
flowchart LR
    A---|This is the text|B
```
````

带有箭头和文字的边：

````{panels}
```
flowchart LR
    A-->|text|B
```
---
```{mermaid}
flowchart LR
    A-->|text|B
```
````

或者


````{panels}
```
flowchart LR
    A-- text -->B
```
---
```{mermaid}
flowchart LR
    A-- text -->B
```
````

带点的边：

````{panels}
```
flowchart LR;
   A-.->B;
```
---
```{mermaid}
flowchart LR;
   A-.->B;
```
````

带点和文本的边：

````{panels}
```
flowchart LR
   A-. text .-> B
```
---
```{mermaid}
flowchart LR
   A-. text .-> B
```
````

粗边：

````{panels}
```
flowchart LR
   A ==> B
```
---
```{mermaid}
flowchart LR
   A ==> B
```
````

带文本的粗边：

````{panels}
```
flowchart LR
   A == text ==> B
```
---
```{mermaid}
flowchart LR
   A == text ==> B
```
````

### 边的连锁化

可以在同一行中声明许多边，如下所示。

````{panels}
```
flowchart LR
   A -- text --> B -- text2 --> C
```
---
```{mermaid}
flowchart LR
   A -- text --> B -- text2 --> C
```
````

也可以在同一行中声明多个节点链接，如下所示：

````{panels}
```
flowchart LR
   a --> b & c--> d
```
---
```{mermaid}
flowchart LR
   a --> b & c--> d
```
````

然后你可以用一种非常有表现力的方式来描述依赖关系。就像下面这个单行线：

````{panels}
```
flowchart TB
    A & B--> C & D
```
---
```{mermaid}
flowchart TB
    A & B--> C & D
```
````

如果你用基本的语法来描述同样的图表，它将需要四行。需要提醒的是，这样做可能会使流程图在 markdown 形式下更难阅读。我想到了瑞典语中的 `lagom` 一词。它的意思是，不要太多，也不要太少。这也适用于表达式语法。

````{panels}
```
flowchart TB
    A --> C
    A --> D
    B --> C
    B --> D
```
---
```{mermaid}
flowchart TB
    A --> C
    A --> D
    B --> C
    B --> D
```
````

## 箭头

有新类型的箭头支持，如下所示：

````{panels}
```
flowchart LR
    A --o B
    B --x C
```
---
```{mermaid}
flowchart LR
    A --o B
    B --x C
```
````

### 多方向的箭头

有可能使用多方向的箭头。

````{panels}
```
flowchart LR
    A o--o B
    B <--> C
    C x--x D
```
---
```{mermaid}
flowchart LR
    A o--o B
    B <--> C
    C x--x D
```
````

### 边的最小长度

流程图中的每个节点最终被分配到渲染图中的一个等级，即根据它所链接的节点，分配到一个垂直或水平层次（取决于流程图的方向）。默认情况下，链接可以跨越任何数量的等级，但你可以通过在链接定义中添加额外的破折号来要求任何链接比其他的长。

在下面的例子中，从节点B到节点E的链接中添加了两个额外的破折号，这样它就比普通链接多跨两个等级：

````{panels}
```
flowchart TD
    A[Start] --> B{Is it?};
    B -->|Yes| C[OK];
    C --> D[Rethink];
    D --> B;
    B ---->|No| E[End];
```
---
```{mermaid}
flowchart TD
    A[Start] --> B{Is it?};
    B -->|Yes| C[OK];
    C --> D[Rethink];
    D --> B;
    B ---->|No| E[End];
```
````

当链接标签写在链接的中间时，额外的破折号必须加在链接的右边。下面的例子等同于前面的例子：

````{panels}
```
flowchart TD
    A[Start] --> B{Is it?};
    B -- Yes --> C[OK];
    C --> D[Rethink];
    D --> B;
    B -- No ----> E[End];
```
---
```{mermaid}
flowchart TD
    A[Start] --> B{Is it?};
    B -- Yes --> C[OK];
    C --> D[Rethink];
    D --> B;
    B -- No ----> E[End];
```
````

对于点状或粗大的链接，需要添加的字符是等号或点，如下表所总结的那样：

| 长度              |    1   |    2    |     3    |
|-------------------|:------:|:-------:|:--------:|
| Normal            |  `---` |  `----` |  `-----` |
| Normal with arrow |  `-->` |  `--->` |  `---->` |
| Thick             |  `===` |  `====` |  `=====` |
| Thick with arrow  |  `==>` |  `===>` |  `====>` |
| Dotted            | `-.-`  | `-..-`  | `-...-`  |
| Dotted with arrow | `-.->` | `-..->` | `-...->` |

## 破坏语法的特殊字符

可以将文本放在引号内，以便呈现更多麻烦的字符。如下面的例子。

````{panels}
```
flowchart LR
    id1["This is the (text) in the box"]
```
---
```{mermaid}
flowchart LR
    id1["This is the (text) in the box"]
```
````

### 转义字符的实体代码

可以使用这里所举的语法来转义字符。

````{panels}
```
flowchart LR
    A["A double quote:#quot;"] -->B["A dec char:#9829;"]
```
---
```{mermaid}
flowchart LR
    A["A double quote:#quot;"] -->B["A dec char:#9829;"]
```
````

给出的数字是以 10 为基数的，所以 `#` 可以被编码为 `#35;`。也支持使用 HTML 字符名称。

## 子图

```
subgraph title
    graph definition
end
```

示例：

````{panels}
```
flowchart TB
    c1-->a2
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
```
---
```{mermaid}
flowchart TB
    c1-->a2
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
```
````

你也可以为子图设置一个明确的 ID。

````{panels}
```
flowchart TB
    c1-->a2
    subgraph ide1 [one]
    a1-->a2
    end
```
---
```{mermaid}
flowchart TB
    c1-->a2
    subgraph ide1 [one]
    a1-->a2
    end
```
````

通过 graphtype 的流程图，也可以像下面的流程图那样，设置通往和来自子图的边。

````{panels}
```
flowchart TB
    c1-->a2
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
    one --> two
    three --> two
    two --> c2
```
---
```{mermaid}
flowchart TB
    c1-->a2
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
    one --> two
    three --> two
    two --> c2
```
````

### 子图中的方向

对于 graphtype 流程图，你可以使用方向语句来设置子图的渲染方向，就像本例中一样。

````{panels}
```
flowchart LR
  subgraph TOP
    direction TB
    subgraph B1
        direction RL
        i1 -->f1
    end
    subgraph B2
        direction BT
        i2 -->f2
    end
  end
  A --> TOP --> B
  B1 --> B2
```
---
```{mermaid}
flowchart LR
  subgraph TOP
    direction TB
    subgraph B1
        direction RL
        i1 -->f1
    end
    subgraph B2
        direction BT
        i2 -->f2
    end
  end
  A --> TOP --> B
  B1 --> B2
```
````

## 交互性

可以为一个节点绑定一个点击事件，点击可以导致一个 javascript 回调或一个链接，这个链接将在一个新的浏览器标签中打开。注意：当使用 `securityLevel='strict'` 时，该功能被禁用，当使用 `securityLevel='loose'` 时，该功能被启用。

```
click nodeId callback
click nodeId call callback()
```

- `nodeId` 是节点的 ID
- `callback` 是在显示图形的页面上定义的 javascript 函数的名称，该函数将以 `nodeId` 为参数被调用。

下面是工具提示使用的例子：

```html
<script>
  var callback = function(){
      alert('A callback was triggered');
  }
</script>
```

工具提示文本被双引号所包围。工具提示的样式由 `.mermaidTooltip` 类设置。

````{panels}
```
flowchart LR;
    A-->B;
    B-->C;
    C-->D;
    click A callback "Tooltip for a callback"
    click B "http://www.github.com" "This is a tooltip for a link"
    click A call callback() "Tooltip for a callback"
    click B href "http://www.github.com" "This is a tooltip for a link"
```
---
```{mermaid}
flowchart LR;
    A-->B;
    B-->C;
    C-->D;
    click A callback "Tooltip for a callback"
    click B "http://www.github.com" "This is a tooltip for a link"
    click A call callback() "Tooltip for a callback"
    click B href "http://www.github.com" "This is a tooltip for a link"
```
````

链接默认是在同一个浏览器标签/窗口中打开的。可以通过在点击定义中添加一个链接目标来改变这一点（支持 `_self`、`_blank`、`_parent` 和 `_top`）。

````{panels}
```
flowchart LR;
    A-->B;
    B-->C;
    C-->D;
    D-->E;
    click A "http://www.github.com" _blank
    click B "http://www.github.com" "Open this in a new tab" _blank
    click C href "http://www.github.com" _blank
    click D href "http://www.github.com" "Open this in a new tab" _blank
```
---
```{mermaid}
flowchart LR;
    A-->B;
    B-->C;
    C-->D;
    D-->E;
    click A "http://www.github.com" _blank
    click B "http://www.github.com" "Open this in a new tab" _blank
    click C href "http://www.github.com" _blank
    click D href "http://www.github.com" "Open this in a new tab" _blank
```
````

初学者的提示，一个在 html 背景下使用交互式链接的完整例子。

```html
<body>
  <div class="mermaid">
    flowchart LR;
        A-->B;
        B-->C;
        C-->D;
        click A callback "Tooltip"
        click B "http://www.github.com" "This is a link"
        click C call callback() "Tooltip"
        click D href "http://www.github.com" "This is a link"
  </div>

  <script>
    var callback = function(){
        alert('A callback was triggered');
    }
    var config = {
        startOnLoad:true,
        flowchart:{
            useMaxWidth:true,
            htmlLabels:true,
            curve:'cardinal',
        },
        securityLevel:'loose',
    };

    mermaid.initialize(config);
  </script>
</body>
```

### 注释

在流程图中可以输入注释，解析器会忽略这些注释。注释需要在自己的行中，并且必须以 `%%` （双百分号）为前导。从注释开始到下一个换行的任何文本都将被视为注释，包括任何流程语法

```
flowchart LR
%% this is a comment A -- text --> B{node}
   A -- text --> B -- text2 --> C
```

## 样式和类

### 样式边

可以对边进行样式设计。例如，你可能想为一个在流程中向后移动的边设置样式。由于边没有与节点相同的 id，所以需要用其他方式来决定边应该被附加到什么样式。使用边在图中被定义时的顺序号来代替id。在下面的例子中，linkStyle 语句中定义的样式将属于图中的第四个边。

```
linkStyle 3 stroke:#ff3,stroke-width:4px,color:red;
```

### 样式节点

它可以应用特定的样式，如更厚的边框或不同的背景颜色到一个节点。

```
flowchart LR
    id1(Start)-->id2(Stop)
    style id1 fill:#f9f,stroke:#333,stroke-width:4px
    style id2 fill:#bbf,stroke:#f66,stroke-width:2px,color:#fff,stroke-dasharray: 5 5
```

### 类

比起每次定义样式，更方便的是定义一个样式类，并将这个类附加到应该有不同外观的节点上。

一个类的定义看起来像下面的例子：

```
classDef className fill:#f9f,stroke:#333,stroke-width:4px;
```

将一个类附加到一个节点上是按以下方式进行的：

```
class nodeId1 className;
```

也可以在一条语句中把一个类附加到一个节点的列表上：

```
class nodeId1,nodeId2 className;
```

添加类的一个较短的形式是使用 `::` 操作符将类名附加到节点上，如下所示：

```
flowchart LR
    A:::someclass --> B
    classDef someclass fill:#f96;
```

### CSS 类

也可以在 CSS 样式中预先定义类，可以从图的定义中应用，如下面的例子：

```html
<style>
    .cssClass > rect{
        fill:#FF0000;
        stroke:#FFFF00;
        stroke-width:4px;
    }
</style>
```

示例：

```
flowchart LR;
    A-->B[AAA<span>BBB</span>];
    B-->D;
    class A cssClass;
```
