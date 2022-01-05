# 序列图

> 序列图是一种交互图，显示流程如何相互操作以及以何种顺序操作。

Mermaid 可以渲染序列图。

```
sequenceDiagram
    Alice->>John: Hello John, how are you?
    John-->>Alice: Great!
    Alice-)John: See you later!
```

```{mermaid}
sequenceDiagram
    Alice->>John: Hello John, how are you?
    John-->>Alice: Great!
    Alice-)John: See you later!
```

```{note}
关于节点的说明，由于 mermaid 语言的脚本方式，"end" 这个词有可能破坏图表。

如果不可避免，必须使用小括号 ()、引号 "" 或大括号 {}，[] 来括住 "end" 这个词：(end), [end], {end}
```

## 语法

### 参与者

参与者的定义可以是隐性的，就像本页面的第一个例子一样。参与者或行动者是按照图表源文本中的出现顺序呈现的。有时你可能想以不同的顺序显示参与者，而不是他们在第一条信息中出现的方式。可以通过以下方式来指定行动者的出现顺序：

```
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>Bob: Hi Bob
    Bob->>Alice: Hi Alice
```

```{mermaid}
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>Bob: Hi Bob
    Bob->>Alice: Hi Alice
```

### 行动者

如果你特别想使用行动者符号而不是带有文字的矩形，你可以通过使用行动者语句来实现，如下所示。

```
sequenceDiagram
    actor Alice
    actor Bob
    Alice->>Bob: Hi Bob
    Bob->>Alice: Hi Alice
```

```{mermaid}
sequenceDiagram
    actor Alice
    actor Bob
    Alice->>Bob: Hi Bob
    Bob->>Alice: Hi Alice
```

### 别名

行为者可以有一个方便的标识符和一个描述性的标签。

``
sequenceDiagram
    participant A as Alice
    participant J as John
    A->>J: Hello John, how are you?
    J->>A: Great!
```

```{mermaid}
sequenceDiagram
    participant A as Alice
    participant J as John
    A->>J: Hello John, how are you?
    J->>A: Great!
```

## 信息

信息可以有两种显示方式，要么是实线，要么是虚线。

```
[Actor][Arrow][Actor]:Message text
```

目前支持六种类型的箭头：

| Type | Description                                 |
| ---- | ------------------------------------------- |
| ->   | Solid line without arrow                    |
| -->  | Dotted line without arrow                   |
| ->>  | Solid line with arrowhead                   |
| -->> | Dotted line with arrowhead                  |
| -x   | Solid line with a cross at the end          |
| --x  | Dotted line with a cross at the end.        |
| -)   | Solid line with an open arrow at the end (async)  |
| --)  | Dotted line with a open arrow at the end (async) |

## 激活

激活和停用一个行为体是可能的。(去)激活可以是专门的声明。

```
sequenceDiagram
    Alice->>John: Hello John, how are you?
    activate John
    John-->>Alice: Great!
    deactivate John
```

```{mermaid}
sequenceDiagram
    Alice->>John: Hello John, how are you?
    activate John
    John-->>Alice: Great!
    deactivate John
```

还有一种快捷方式是在信息箭头上附加 `+`/`-` 后缀：

```
sequenceDiagram
    Alice->>+John: Hello John, how are you?
    John-->>-Alice: Great!
```

```{mermaid}
sequenceDiagram
    Alice->>+John: Hello John, how are you?
    John-->>-Alice: Great!
```

激活可以叠加在同一个 actor 身上。

```
sequenceDiagram
    Alice->>+John: Hello John, how are you?
    Alice->>+John: John, can you hear me?
    John-->>-Alice: Hi Alice, I can hear you!
    John-->>-Alice: I feel great!
```

```{mermaid}
sequenceDiagram
    Alice->>+John: Hello John, how are you?
    Alice->>+John: John, can you hear me?
    John-->>-Alice: Hi Alice, I can hear you!
    John-->>-Alice: I feel great!
```

## 注解

可以在一个序列图中添加注释。这是由以下符号完成的 Note [ right of | left of | over ] [Actor]: Text 中的内容：

```
sequenceDiagram
    participant John
    Note right of John: Text in note
```

```{mermaid}
sequenceDiagram
    participant John
    Note right of John: Text in note
```

也可以创建跨越两个参与者的笔记：

```
sequenceDiagram
    Alice->John: Hello John, how are you?
    Note over Alice,John: A typical interaction
```

```{mermaid}
sequenceDiagram
    Alice->John: Hello John, how are you?
    Note over Alice,John: A typical interaction
```

## 循环

在序列图中表达循环是可能的。这可以通过以下符号来实现

```
loop Loop text
... statements ...
end
```

示例：

```
sequenceDiagram
    Alice->John: Hello John, how are you?
    loop Every minute
        John-->Alice: Great!
    end
```

```{mermaid}
sequenceDiagram
    Alice->John: Hello John, how are you?
    loop Every minute
        John-->Alice: Great!
    end
```

## Alt

在一个序列图中，有可能表达替代路径。这可以通过以下符号来实现

```
alt Describing text
... statements ...
else
... statements ...
end
```

或如果有序列是可选的（如果没有其他）。

```
opt Describing text
... statements ...
end
```

示例：

```
sequenceDiagram
    Alice->>Bob: Hello Bob, how are you?
    alt is sick
        Bob->>Alice: Not so good :(
    else is well
        Bob->>Alice: Feeling fresh like a daisy
    end
    opt Extra response
        Bob->>Alice: Thanks for asking
    end
```

```{mermaid}
sequenceDiagram
    Alice->>Bob: Hello Bob, how are you?
    alt is sick
        Bob->>Alice: Not so good :(
    else is well
        Bob->>Alice: Feeling fresh like a daisy
    end
    opt Extra response
        Bob->>Alice: Thanks for asking
    end
```

## Parallel

有可能显示平行发生的行动。

这可以通过以下符号来实现

```
par [Action 1]
... statements ...
and [Action 2]
... statements ...
and [Action N]
... statements ...
end
```

示例：

```
sequenceDiagram
    par Alice to Bob
        Alice->>Bob: Hello guys!
    and Alice to John
        Alice->>John: Hello guys!
    end
    Bob-->>Alice: Hi Alice!
    John-->>Alice: Hi Alice!
```

```{mermaid}
sequenceDiagram
    par Alice to Bob
        Alice->>Bob: Hello guys!
    and Alice to John
        Alice->>John: Hello guys!
    end
    Bob-->>Alice: Hi Alice!
    John-->>Alice: Hi Alice!
```

也可以对平行块进行嵌套：

```
sequenceDiagram
    par Alice to Bob
        Alice->>Bob: Go help John
    and Alice to John
        Alice->>John: I want this done today
        par John to Charlie
            John->>Charlie: Can we do this today?
        and John to Diana
            John->>Diana: Can you help us today?
        end
    end
```

```{mermaid}
sequenceDiagram
    par Alice to Bob
        Alice->>Bob: Go help John
    and Alice to John
        Alice->>John: I want this done today
        par John to Charlie
            John->>Charlie: Can we do this today?
        and John to Diana
            John->>Diana: Can you help us today?
        end
    end
```

## 背景高亮

可以通过提供彩色的背景矩形来突出流量。这可以通过以下符号来实现。

颜色是用 rgb 和 rgba 语法定义的。

```
rect rgb(0, 255, 0)
... content ...
end
```

```
rect rgba(0, 0, 255, .1)
... content ...
end
```

示例：

```
sequenceDiagram
    participant Alice
    participant John

    rect rgb(191, 223, 255)
    note right of Alice: Alice calls John.
    Alice->>+John: Hello John, how are you?
    rect rgb(200, 150, 255)
    Alice->>+John: John, can you hear me?
    John-->>-Alice: Hi Alice, I can hear you!
    end
    John-->>-Alice: I feel great!
    end
    Alice ->>+ John: Did you want to go to the game tonight?
    John -->>- Alice: Yeah! See you there.
```

```{mermaid}
sequenceDiagram
    participant Alice
    participant John

    rect rgb(191, 223, 255)
    note right of Alice: Alice calls John.
    Alice->>+John: Hello John, how are you?
    rect rgb(200, 150, 255)
    Alice->>+John: John, can you hear me?
    John-->>-Alice: Hi Alice, I can hear you!
    end
    John-->>-Alice: I feel great!
    end
    Alice ->>+ John: Did you want to go to the game tonight?
    John -->>- Alice: Yeah! See you there.
```

## 转义字符的实体代码

可以使用这里所举的语法来转义字符。

```
sequenceDiagram
    A->>B: I #9829; you!
    B->>A: I #9829; you #infin; times more!
```

```{mermaid}
sequenceDiagram
    A->>B: I #9829; you!
    B->>A: I #9829; you #infin; times more!
```

给出的数字是基数10，所以 `#` 可以编码为 `#35;`。也支持使用 HTML 字符名称。

因为分号可以代替换行符来定义标记，你需要使用 `#59;` 来在消息文本中包含分号。

## sequenceNumbers

可以在序列图中的每个箭头上获得一个序列号。这可以在添加美人鱼到网站时进行配置，如下图所示：

```html
    <script>
      mermaid.initialize({
        sequence: { showSequenceNumbers: true },
      });
    </script>
```

它也可以通过图中的代码打开，如图所示。

```
sequenceDiagram
    autonumber
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```

```{mermaid}
sequenceDiagram
    autonumber
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```

## Actor 菜单

行为体可以有弹出式菜单，其中包含指向外部页面的个性化链接。例如，如果一个角色代表一个网络服务，有用的链接可能包括一个指向服务健康仪表板的链接，包含服务代码的 repo，或者描述服务的维基页面。

这可以通过添加一个或多个格式的链接行来配置：

```
link <actor>: <link-label> @ <link-url>
```
示例：

```
sequenceDiagram
    participant Alice
    participant John
    link Alice: Dashboard @ https://dashboard.contoso.com/alice
    link Alice: Wiki @ https://wiki.contoso.com/alice
    link John: Dashboard @ https://dashboard.contoso.com/john
    link John: Wiki @ https://wiki.contoso.com/john
    Alice->>John: Hello John, how are you?
    John-->>Alice: Great!
    Alice-)John: See you later!
```

```{mermaid}
sequenceDiagram
    participant Alice
    participant John
    link Alice: Dashboard @ https://dashboard.contoso.com/alice
    link Alice: Wiki @ https://wiki.contoso.com/alice
    link John: Dashboard @ https://dashboard.contoso.com/john
    link John: Wiki @ https://wiki.contoso.com/john
    Alice->>John: Hello John, how are you?
    John-->>Alice: Great!
    Alice-)John: See you later!
```

### 高级 Menu 语法

有一种高级语法是依靠 JSON 格式的。如果你能适应 JSON 格式，那么这也是存在的。

这可以通过添加格式的链接行来配置。

```
links <actor>: <json-formatted link-name link-url pairs>
```

示例：

```
sequenceDiagram
    participant Alice
    participant John
    links Alice: {"Dashboard": "https://dashboard.contoso.com/alice", "Wiki": "https://wiki.contoso.com/alice"}
    links John: {"Dashboard": "https://dashboard.contoso.com/john", "Wiki": "https://wiki.contoso.com/john"}
    Alice->>John: Hello John, how are you?
    John-->>Alice: Great!
    Alice-)John: See you later!
```

```{mermaid}
sequenceDiagram
    participant Alice
    participant John
    links Alice: {"Dashboard": "https://dashboard.contoso.com/alice", "Wiki": "https://wiki.contoso.com/alice"}
    links John: {"Dashboard": "https://dashboard.contoso.com/john", "Wiki": "https://wiki.contoso.com/john"}
    Alice->>John: Hello John, how are you?
    John-->>Alice: Great!
    Alice-)John: See you later!
```
