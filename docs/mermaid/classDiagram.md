# 类图

> "在软件工程中，统一建模语言（Unified Modeling Language，UML）中的类图是一种静态结构图，通过显示系统的类、它们的属性、操作（或方法）以及对象之间的关系来描述系统的结构。"
—— 维基百科

类图是面向对象建模的主要构建块。它用于应用程序结构的一般概念性建模，以及将模型转化为编程代码的详细建模。类图也可用于数据建模。类图中的类既代表了主要元素，也代表了应用程序中的交互，还代表了要编程的类。

Mermaid 可以渲染类图。

```
 classDiagram
      Animal <|-- Duck
      Animal <|-- Fish
      Animal <|-- Zebra
      Animal : +int age
      Animal : +String gender
      Animal: +isMammal()
      Animal: +mate()
      class Duck{
          +String beakColor
          +swim()
          +quack()
      }
      class Fish{
          -int sizeInFeet
          -canEat()
      }
      class Zebra{
          +bool is_wild
          +run()
      }
```

```{mermaid}
 classDiagram
      Animal <|-- Duck
      Animal <|-- Fish
      Animal <|-- Zebra
      Animal : +int age
      Animal : +String gender
      Animal: +isMammal()
      Animal: +mate()
      class Duck{
          +String beakColor
          +swim()
          +quack()
      }
      class Fish{
          -int sizeInFeet
          -canEat()
      }
      class Zebra{
          +bool is_wild
          +run()
      }
```

## 语法

### `class`

UML 提供了表示类成员的机制，如属性和方法，以及关于它们的附加信息。

图中一个类的单个实例包含三个隔层：

- 最上面的一格包含了 class 的名称。它以粗体字打印并居中，第一个字母大写。它也可以包含描述该类性质的可选注释文本。
- 中间部分包含该类的属性。它们是左对齐的，第一个字母是小写的。
- 底部的隔间包含了该类可以执行的操作。它们也是左对齐的，第一个字母是小写的。

```
classDiagram
    class BankAccount
    BankAccount : +String owner
    BankAccount : +Bigdecimal balance
    BankAccount : +deposit(amount)
    BankAccount : +withdrawl(amount)
```

```{mermaid}
classDiagram
    class BankAccount
    BankAccount : +String owner
    BankAccount : +Bigdecimal balance
    BankAccount : +deposit(amount)
    BankAccount : +withdrawl(amount)
```

## 定义 `class`

有两种方法定义 class：

- 使用关键字 **class** 明确地定义一个类，如 `class Animal`。这就定义了动物类
- 通过它们之间的 **关系** 定义两个类 `Vehicle <|-- Car`。这就定义了两个类 Vehicle 和 Car，以及它们之间的关系。

```
classDiagram
    class Animal
    Vehicle <|-- Car
```

```{mermaid}
classDiagram
    class Animal
    Vehicle <|-- Car
```

命名规则：一个类的名称应该由字母数字（允许使用 unicode）和下划线字符组成。

## 定义 class 的成员

UML 提供了表示类成员的机制，如属性和方法，以及关于它们的额外信息。

Mermaid 区分属性和函数/方法的依据是：是否有 **括号** `()` 存在。带有 `()` 的被视为函数/方法，而其他的被视为属性。

有两种方法来定义类的成员，无论使用哪种语法来定义成员，其输出结果都是一样的。这两种不同的方式是：

- 使用 **:** （冒号）跟在成员名称后面关联一个类的成员，对一次定义一个成员很有用。比如说：

```
 classDiagram
 class BankAccount
 BankAccount : +String owner
 BankAccount : +BigDecimal balance
 BankAccount : +deposit(amount)
 BankAccount : +withdrawal(amount)
```

```{mermaid}
 classDiagram
 class BankAccount
 BankAccount : +String owner
 BankAccount : +BigDecimal balance
 BankAccount : +deposit(amount)
 BankAccount : +withdrawal(amount)
```

- 使用 **{}** 括号关联一个类的成员，成员在大括号内分组。适用于一次定义多个成员。例如：

```
classDiagram
class BankAccount{
    +String owner
    +BigDecimal balance
    +deposit(amount)
    +withdrawl(amount)
}
```

```{mermaid}
classDiagram
class BankAccount{
    +String owner
    +BigDecimal balance
    +deposit(amount)
    +withdrawl(amount)
}
```

### 返回类型

你可以选择在方法/函数定义的最后加上将被返回的数据类型（注意：在方法定义的最后一个 `)` 和返回类型之间必须有一个空格

例子：

```
classDiagram
class BankAccount{
    +String owner
    +BigDecimal balance
    +deposit(amount) bool
    +withdrawl(amount) int
}
```

```{mermaid}
classDiagram
class BankAccount{
    +String owner
    +BigDecimal balance
    +deposit(amount) bool
    +withdrawl(amount) int
}
```

### 通用类型

成员可以使用通用类型来定义，例如 `List<int>`，用于字段、参数和返回类型，方法是将类型括在 `~` （**tilde**）内。注意：目前不支持 **嵌套的** 类型声明（如  `List<List<int>>`）。

这可以作为类定义方法的一部分来完成：

```
classDiagram
class Square~Shape~{
    int id
    List~int~ position
    setPoints(List~int~ points)
    getPoints() List~int~
}

Square : -List~string~ messages
Square : +setMessages(List~string~ messages)
Square : +getMessages() List~string~
```

```{mermaid}
classDiagram
class Square~Shape~{
    int id
    List~int~ position
    setPoints(List~int~ points)
    getPoints() List~int~
}

Square : -List~string~ messages
Square : +setMessages(List~string~ messages)
Square : +getMessages() List~string~
```

### 返回类型

你可以选择用将被返回的数据类型来结束方法/函数定义。

### 可见性

为了指定一个类成员（即任何属性或方法）的可见性，这些符号可以放在该成员的名称之前，但这是可选的。

- `+` Public
- `-` Private
- `#` Protected
- `~` Package/Internal

>  _注意_ 你也可以在方法定义中加入额外的 _classifiers_，方法的结尾处，即：在 `()` 的后面加入以下符号：
> - `*` Abstract e.g.: `someAbstractMethod()*`
> - `$` Static e.g.: `someStaticMethod()$`

> _注意_ 你也可以在字段定义中加入额外的 _classifiers_，方法是在字段名的末尾加入以下说明：
> - `$` Static e.g.: `String someField$`

## 定义关系

关系是一个一般的术语，涵盖了在类图和对象图上发现的特定类型的逻辑连接。

```
[classA][Arrow][ClassB]
```

在 UML 下有不同类型的关系定义，目前支持的是类：

| Type  | Description   |
| ----- | ------------- |
| <\|-- | Inheritance   |
| \*--  | Composition   |
| o--   | Aggregation   |
| -->   | Association   |
| --    | Link (Solid)  |
| ..>   | Dependency    |
| ..\|> | Realization   |
| ..    | Link (Dashed) |

```
classDiagram
classA <|-- classB
classC *-- classD
classE o-- classF
classG <-- classH
classI -- classJ
classK <.. classL
classM <|.. classN
classO .. classP
```

```{mermaid}
classDiagram
classA <|-- classB
classC *-- classD
classE o-- classF
classG <-- classH
classI -- classJ
classK <.. classL
classM <|.. classN
classO .. classP
```

我们可以用标签来描述两个类之间关系的性质。另外，箭头也可以用在相反的方向：

```
classDiagram
classA --|> classB : Inheritance
classC --* classD : Composition
classE --o classF : Aggregation
classG --> classH : Association
classI -- classJ : Link(Solid)
classK ..> classL : Dependency
classM ..|> classN : Realization
classO .. classP : Link(Dashed)
```

```{mermaid}
classDiagram
classA --|> classB : Inheritance
classC --* classD : Composition
classE --o classF : Aggregation
classG --> classH : Association
classI -- classJ : Link(Solid)
classK ..> classL : Dependency
classM ..|> classN : Realization
classO .. classP : Link(Dashed)
```

### 关系中的标签

可以为一个关系添加一个标签文本：

```
[classA][Arrow][ClassB]:LabelText
```

```
classDiagram
classA <|-- classB : implements
classC *-- classD : composition
classE o-- classF : association
```

```{mermaid}
classDiagram
classA <|-- classB : implements
classC *-- classD : composition
classE o-- classF : association
```

### Two-way 关系

关系可以以多种方式进行：

```
classDiagram
    Animal <|--|> Zebra
```

这是语法：

```
[Relation Type][Link][Relation Type]
```

其中 `Relation Type` 可以是以下之一：

| Type | Description |
| ---- | ----------- |
| <\|  | Inheritance |
| \*   | Composition |
| o    | Aggregation |
| >    | Association |
| <    | Association |
| \|>  | Realization |

而 `Link` 可以是以下之一：

| Type | Description |
| ---- | ----------- |
| --   | Solid       |
| ..   | Dashed      |

## 关系上的 cardinality / Multiplicity

类图中的 Multiplicity 或 cardinality 表示一个类的实例与另一个类的一个实例相连的数量。例如，一个公司会有一个或多个雇员，但每个雇员只为一个公司工作。

Multiplicity 符号被放在关联的两端附近。

不同的 cardinality 选项是：

- `1` 仅 1
- `0..1` 0 或者 1
- `1..*` 1 或更多
- `*` 许多
- `n` n {where n>1}
- `0..n` 0 到 n {where n>1}
- `1..n` 1 到 n {where n>1}

通过在给定的箭头之前（可选）和之后（可选）的引号 `"` 内放置心率文本，可以轻松地定义心率。

```
[classA] "cardinality1" [Arrow] "cardinality2" [ClassB]:LabelText
```

```
classDiagram
    Customer "1" --> "*" Ticket
    Student "1" --> "1..*" Course
    Galaxy --> "many" Star : Contains
```

```{mermaid}
classDiagram
    Customer "1" --> "*" Ticket
    Student "1" --> "1..*" Course
    Galaxy --> "many" Star : Contains
```

## class 注解

可以用特定的标记文本来注释类，这就像类的元数据，清楚地表明其性质。一些常见的注释例子可以是：

- `<<Interface>>` 代表一个接口类
- `<<abstract>>` 代表一个抽象类。
- `<<Service>>` 代表一个服务类
- `<<enumeration>>` 代表一个枚举类

注释被定义在开头的 `<<` 和结尾的 `>>` 中。有两种方法可以为一个类添加注解，无论使用何种语法，输出都是一样的。这两种方法是：

- 在定义了一个类之后的 **_separate line_**。比如说：

```
classDiagram
class Shape
<<interface>> Shape
Shape : noOfVertices
Shape : draw()
```

```{mermaid}
classDiagram
class Shape
<<interface>> Shape
Shape : noOfVertices
Shape : draw()
```

- 在一个 **_嵌套结构中_** 与类定义一起。比如说：

```
classDiagram
class Shape{
    <<interface>>
    noOfVertices
    draw()
}
class Color{
    <<enumeration>>
    RED
    BLUE
    GREEN
    WHITE
    BLACK
}
```

```{mermaid}
classDiagram
class Shape{
    <<interface>>
    noOfVertices
    draw()
}
class Color{
    <<enumeration>>
    RED
    BLUE
    GREEN
    WHITE
    BLACK
}
```

## 设置图表的方向

对于类图，你可以使用方向语句来设置图表的渲染方向，就像本例中一样。

```
classDiagram
  direction RL
  class Student {
    -idCard : IdCard
  }
  class IdCard{
    -id : int
    -name : string
  }
  class Bike{
    -id : int
    -name : string
  }
  Student "1" --o "1" IdCard : carries
  Student "1" --o "1" Bike : rides
```

```{mermaid}
classDiagram
  direction RL
  class Student {
    -idCard : IdCard
  }
  class IdCard{
    -id : int
    -name : string
  }
  class Bike{
    -id : int
    -name : string
  }
  Student "1" --o "1" IdCard : carries
  Student "1" --o "1" Bike : rides
```

## 交互性

可以为一个节点绑定一个点击事件，点击可以导致一个 javascript 回调或一个将在新的浏览器标签中打开的链接。**注意**: 当使用 `securityLevel='strict'` 时，该功能被禁用，而当使用 `securityLevel='loose'` 时，则被启用。

你可以在所有的类都被声明后，在单独的一行中定义这些动作。

```
action className "reference" "tooltip"
click className call callback() "tooltip"
click className href "url" "tooltip"
```

- _action_ 是 `link` 或 `callback`，取决于你想调用哪种类型的交互。
- _className_ 是动作将与之相关的节点的 id。
- _reference_ 是 url 链接，或者是回调的函数名。
- (_optional_) tooltip 是一个字符串，当悬停在元素上时显示（注意：工具提示的样式由类 .mermaidTooltip 设置。）
- 注意：回调函数将以 nodeId 为参数被调用。

### 示例

_URL Link:_

```
classDiagram
class Shape
link Shape "http://www.github.com" "This is a tooltip for a link"
class Shape2
click Shape2 href "http://www.github.com" "This is a tooltip for a link"
```

_Callback:_

```
classDiagram
class Shape
callback Shape "callbackFunction" "This is a tooltip for a callback"
class Shape2
click Shape2 call callbackFunction() "This is a tooltip for a callback"
```

```html
<script>
    var callbackFunction = function(){
        alert('A callback was triggered');
    }
<script>
```

```
classDiagram
    class Class01
    class Class02
    callback Class01 "callbackFunction" "Callback tooltip"
    link Class02 "http://www.github.com" "This is a link"
    class Class03
    class Class04
    click Class03 call callbackFunction() "Callback tooltip"
    click Class04 href "http://www.github.com" "This is a link"
```

> **Success** The tooltip functionality and the ability to link to urls are available from version 0.5.2.

Beginners tip, a full example using interactive links in an html context:

```
<body>
  <div class="mermaid">
    classDiagram
    Animal <|-- Duck
    Animal <|-- Fish
    Animal <|-- Zebra
    Animal : +int age
    Animal : +String gender
    Animal: +isMammal()
    Animal: +mate()
    class Duck{
      +String beakColor
      +swim()
      +quack()
      }
    class Fish{
      -int sizeInFeet
      -canEat()
      }
    class Zebra{
      +bool is_wild
      +run()
      }

      callback Duck callback "Tooltip"
      link Zebra "http://www.github.com" "This is a link"
  </div>

  <script>
    var callback = function(){
        alert('A callback was triggered');
    }
    var config = {
      startOnLoad:true,
      securityLevel:'loose',
    };

    mermaid.initialize(config);
  </script>
</body>
```

## 风格

### node 格式化

它可以应用特定的样式，如更厚的边框或不同的背景颜色给单个节点。这是通过在css样式中预先定义类来实现的，可以从图的定义中应用，如下面的例子：

```html
<style>
    .cssClass > rect{
        fill:#FF0000;
        stroke:#FFFF00;
        stroke-width:4px;
    }
</style>
```

然后按照下面的方法将该类附加到一个特定的节点：

```
    cssClass "nodeId1" cssClass;
```

也可以在一条语句中把一个类附加到一个节点的列表上：

```
    cssClass "nodeId1,nodeId2" cssClass;
```

添加类的一个较短的形式是使用 `:::` 操作符将类名附加到节点上，如下所示：

```
classDiagram
    class Animal:::cssClass
```

或者：

```
classDiagram
    class Animal:::cssClass {
        -int sizeInFeet
        -canEat()
    }
```

- cssClasses 不能与关系语句同时使用这个速记方法来添加。
- 由于现有的类图标记的限制，目前不可能在类图中定义 css 类。

### 默认风格

类图的主要造型是通过预设的 css 类完成的。在渲染过程中，这些类从位于 src/themes/class.scss 的文件中提取。这里使用的类描述如下。

| Class              | Description                                                       |
| ------------------ | ----------------------------------------------------------------- |
| g.classGroup text  | Styles for general class text                                     |
| classGroup .title  | Styles for general class title                                    |
| g.classGroup rect  | Styles for class diagram rectangle                                |
| g.classGroup line  | Styles for class diagram line                                     |
| .classLabel .box   | Styles for class label box                                        |
| .classLabel .label | Styles for class label text                                       |
| composition        | Styles for composition arrow head and arrow line                  |
| aggregation        | Styles for aggregation arrow head and arrow line(dashed or solid) |
| dependency         | Styles for dependency arrow head and arrow line                   |

#### stylesheet 样例

```
body {
    background: white;
}

g.classGroup text {
    fill: $nodeBorder;
    stroke: none;
    font-family: 'trebuchet ms', verdana, arial;
    font-family: var(--mermaid-font-family);
    font-size: 10px;

    .title {
        font-weight: bolder;
    }
}

g.classGroup rect {
    fill: $nodeBkg;
    stroke: $nodeBorder;
}

g.classGroup line {
    stroke: $nodeBorder;
    stroke-width: 1;
}

.classLabel .box {
    stroke: none;
    stroke-width: 0;
    fill: $nodeBkg;
    opacity: 0.5;
}

.classLabel .label {
    fill: $nodeBorder;
    font-size: 10px;
}

.relation {
    stroke: $nodeBorder;
    stroke-width: 1;
    fill: none;
}

@mixin composition {
    fill: $nodeBorder;
    stroke: $nodeBorder;
    stroke-width: 1;
}

#compositionStart {
    @include composition;
}

#compositionEnd {
    @include composition;
}

@mixin aggregation {
    fill: $nodeBkg;
    stroke: $nodeBorder;
    stroke-width: 1;
}

#aggregationStart {
    @include aggregation;
}

#aggregationEnd {
    @include aggregation;
}

#dependencyStart {
    @include composition;
}

#dependencyEnd {
    @include composition;
}

#extensionStart {
    @include composition;
}

#extensionEnd {
    @include composition;
}
```
