# 状态图

> "状态图是计算机科学和相关领域中用来描述系统行为的一种图示。状态图要求所描述的系统由有限数量的状态组成；有时，情况确实如此，而在其他时候，这是一个合理的抽象。" —— 维基百科

Mermaid 可以渲染状态图。该语法试图与 plantUml 中使用的语法相一致，因为这将使用户更容易在 mermaid 和 plantUml 之间分享图表。

````{panels}
```
stateDiagram-v2
    [*] --> Still
    Still --> [*]

    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```
---
```{mermaid}
stateDiagram-v2
    [*] --> Still
    Still --> [*]

    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```
````


旧的渲染器：

````{panels}
```
stateDiagram
    [*] --> Still
    Still --> [*]

    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```
---
```{mermaid}
stateDiagram
    [*] --> Still
    Still --> [*]

    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```
````

在状态图中，系统被描述为它的状态，以及系统的状态如何通过转换而改变为另一个状态。上面的示例图显示了三种状态：**Still**，**Moving** 和 **Crash**。你开始时处于静止状态。从静止状态，你可以改变状态为移动状态。在移动状态下，你可以把状态变回静止或崩溃。从静止状态到崩溃状态是没有过渡的。

## 状态

一个状态可以用多种方式声明。最简单的方法是定义一个状态 ID 作为描述。

````{panels}
```
stateDiagram-v2
    s1
```
---
```{mermaid}
stateDiagram-v2
    s1
```
````

另一种方法是使用带有描述的状态关键词，如下所述：

````{panels}
```
stateDiagram-v2
    state "This is a state description" as s2
```
---
```{mermaid}
stateDiagram-v2
    state "This is a state description" as s2
```
````

另一种定义带有描述的状态的方法是定义状态 ID，然后是冒号和描述。

````{panels}
```
stateDiagram-v2
    s2 : This is a state description
```
---
```{mermaid}
stateDiagram-v2
    s2 : This is a state description
```
````

## 过渡

过渡是一个状态进入另一个状态的路径/边缘。这是用文本箭头表示的，"\-\-\>"。

当你在两个状态之间定义了一个过渡，并且这些状态还没有被定义，那么未定义的状态就会用过渡的 id 来定义。你以后可以为这样定义的状态添加描述。

````{panels}
```
stateDiagram-v2
    s1 --> s2
```
---
```{mermaid}
stateDiagram-v2
    s1 --> s2
```
````

可以给过渡添加文字。来描述它所代表的内容。

````{panels}
```
stateDiagram-v2
    s1 --> s2: A transition
```
---
```{mermaid}
stateDiagram-v2
    s1 --> s2: A transition
```
````

## 开始和结束

有两个特殊的状态表示图的开始和停止。这些都是用 `[*]` 的语法写的，过渡到它的方向决定了它是一个开始或停止的状态。

````{panels}
```
stateDiagram-v2
    [*] --> s1
    s1 --> [*]
```
---
```{mermaid}
stateDiagram-v2
    [*] --> s1
    s1 --> [*]
```
````

## 复合状态

在现实世界中使用状态图时，你经常会遇到多维的图表，因为一个状态可以
有几个内部状态。在这个术语中，这些被称为复合状态。

为了定义一个复合状态，你需要使用 `state` 关键字，后面跟一个 id，然后在复合状态的主体之间 `{}`。请看下面的例子：

````{panels}
```
stateDiagram-v2
    [*] --> First
    state First {
        [*] --> second
        second --> [*]
    }
```
---
```{mermaid}
stateDiagram-v2
    [*] --> First
    state First {
        [*] --> second
        second --> [*]
    }
```
````

你可以分几层来做这件事：

````{panels}
```
stateDiagram-v2
    [*] --> First

    state First {
        [*] --> Second

        state Second {
            [*] --> second
            second --> Third

            state Third {
                [*] --> third
                third --> [*]
            }
        }
    }
```
---
```{mermaid}
stateDiagram-v2
    [*] --> First

    state First {
        [*] --> Second

        state Second {
            [*] --> second
            second --> Third

            state Third {
                [*] --> third
                third --> [*]
            }
        }
    }
```
````

你也可以定义复合状态之间的过渡：

````{panels}
```
stateDiagram-v2
    [*] --> First
    First --> Second
    First --> Third

    state First {
        [*] --> fir
        fir --> [*]
    }
    state Second {
        [*] --> sec
        sec --> [*]
    }
    state Third {
        [*] --> thi
        thi --> [*]
    }
```
---
```{mermaid}
stateDiagram-v2
    [*] --> First
    First --> Second
    First --> Third

    state First {
        [*] --> fir
        fir --> [*]
    }
    state Second {
        [*] --> sec
        sec --> [*]
    }
    state Third {
        [*] --> thi
        thi --> [*]
    }
```
````

*你不能定义属于不同复合状态的内部状态之间的转换*。

## 选项

有时你需要在两条或多条路径之间建立一个选择模型，你可以使用 &lt;&lt;choice&gt;&gt;。

````{panels}
```
stateDiagram-v2
    state if_state <<choice>>
    [*] --> IsPositive
    IsPositive --> if_state
    if_state --> False: if n < 0
    if_state --> True : if n >= 0
```
---
```{mermaid}
stateDiagram-v2
    state if_state <<choice>>
    [*] --> IsPositive
    IsPositive --> if_state
    if_state --> False: if n < 0
    if_state --> True : if n >= 0
```
````

## 分叉

可以在图中指定一个分叉，使用 &lt;&lt;fork&gt;&gt; &lt;&lt;join&gt;&gt;。

````{panels}
```
   stateDiagram-v2
    state fork_state <<fork>>
      [*] --> fork_state
      fork_state --> State2
      fork_state --> State3

      state join_state <<join>>
      State2 --> join_state
      State3 --> join_state
      join_state --> State4
      State4 --> [*]
```
---
```{mermaid}
   stateDiagram-v2
    state fork_state <<fork>>
      [*] --> fork_state
      fork_state --> State2
      fork_state --> State3

      state join_state <<join>>
      State2 --> join_state
      State3 --> join_state
      join_state --> State4
      State4 --> [*]
```
````

## 注解

有时，没有什么比一张便利贴更能说明问题。在状态图中也是如此。

在这里，你可以选择把便条放在一个节点的 *right of* 或 *left of* 的位置。

````{panels}
```
    stateDiagram-v2
        State1: The state with a note
        note right of State1
            Important information! You can write
            notes.
        end note
        State1 --> State2
        note left of State2 : This is the note to the left.
```
---
```{mermaid}
    stateDiagram-v2
        State1: The state with a note
        note right of State1
            Important information! You can write
            notes.
        end note
        State1 --> State2
        note left of State2 : This is the note to the left.
```
````

## 并发性

如同在plantUml中，你可以使用 `--` 符号指定并发性。

````{panels}
```
stateDiagram-v2
    [*] --> Active

    state Active {
        [*] --> NumLockOff
        NumLockOff --> NumLockOn : EvNumLockPressed
        NumLockOn --> NumLockOff : EvNumLockPressed
        --
        [*] --> CapsLockOff
        CapsLockOff --> CapsLockOn : EvCapsLockPressed
        CapsLockOn --> CapsLockOff : EvCapsLockPressed
        --
        [*] --> ScrollLockOff
        ScrollLockOff --> ScrollLockOn : EvScrollLockPressed
        ScrollLockOn --> ScrollLockOff : EvScrollLockPressed
    }
```
---
```{mermaid}
stateDiagram-v2
    [*] --> Active

    state Active {
        [*] --> NumLockOff
        NumLockOff --> NumLockOn : EvNumLockPressed
        NumLockOn --> NumLockOff : EvNumLockPressed
        --
        [*] --> CapsLockOff
        CapsLockOff --> CapsLockOn : EvCapsLockPressed
        CapsLockOn --> CapsLockOff : EvCapsLockPressed
        --
        [*] --> ScrollLockOff
        ScrollLockOff --> ScrollLockOn : EvScrollLockPressed
        ScrollLockOn --> ScrollLockOff : EvScrollLockPressed
    }
```
````

## 设置图表的方向

对于状态图，你可以使用方向语句来设置图表的渲染方向，就像本例中一样。

````{panels}
```
stateDiagram
    direction LR
    [*] --> A
    A --> B
    B --> C
    state B {
      direction LR
      a --> b
    }
    B --> D
```
---
```{mermaid}
stateDiagram
    direction LR
    [*] --> A
    A --> B
    B --> C
    state B {
      direction LR
      a --> b
    }
    B --> D
```
````
