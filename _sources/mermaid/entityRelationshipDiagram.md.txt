# 实体关系图

> 实体-关系模型（entity–relationship model 或 ER 模型）描述了特定知识领域中感兴趣的相互关联的事物。一个基本的 ER 模型是由实体类型（对感兴趣的事物进行分类）和指定实体（这些实体类型的实例）之间可能存在的关系组成。——维基百科

请注意，ER 建模的从业者几乎总是将 *实体类型* 简单地称为 *实体*。 例如，`CUSTOMER` 实体 *type* 将被简单地称为 `CUSTOMER` 实体。这很常见，所以不应该做其他事情，但从技术上讲，实体是实体类型的一个抽象的 *实例*，而这正是 ER 图所显示的——抽象的实例，以及它们之间的关系。这就是为什么实体总是使用单数名词来命名。

Mermaid 可以渲染 ER 图

```
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ LINE-ITEM : contains
    CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
```

```{mermaid}
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ LINE-ITEM : contains
    CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
```

实体名称通常是大写的，尽管在这方面没有公认的标准，而且在 Mermaid 中也没有要求。

实体之间的关系用线来表示，线的末端标记代表 cardinality。Mermaid 使用最流行的乌鸦脚符号。乌鸦脚直观地表达了它所连接的实体的许多实例的可能性。

ER 图可以用于各种目的，从没有任何实现细节的抽象逻辑模型，到关系数据库表的物理模型。在 ER 图中加入属性定义可以帮助理解实体的目的和意义。这些不一定要详尽无遗；通常一个小的属性子集就足够了。Mermaid 允许在它们的 *type* 和 *name* 方面进行定义。

```
erDiagram
    CUSTOMER ||--o{ ORDER : places
    CUSTOMER {
        string name
        string custNumber
        string sector
    }
    ORDER ||--|{ LINE-ITEM : contains
    ORDER {
        int orderNumber
        string deliveryAddress
    }
    LINE-ITEM {
        string productCode
        int quantity
        float pricePerUnit
    }
```

```{mermaid}
erDiagram
    CUSTOMER ||--o{ ORDER : places
    CUSTOMER {
        string name
        string custNumber
        string sector
    }
    ORDER ||--|{ LINE-ITEM : contains
    ORDER {
        int orderNumber
        string deliveryAddress
    }
    LINE-ITEM {
        string productCode
        int quantity
        float pricePerUnit
    }
```

在 ER 图上包括属性时，你必须决定是否将外键作为属性包括在内。这可能取决于你试图表现关系表结构的紧密程度。如果你的图是一个 *logical*  模型，并不是为了暗示关系的实现，那么最好不包括这些，因为关联关系已经传达了实体的关联方式。例如，JSON 数据结构可以实现一对多的关系，不需要外键属性，使用数组。同样地，面向对象的编程语言可以使用指针或对集合的引用。甚至对于那些旨在实现关系的模型，你可能会决定包含外键属性会重复已经被关系所描绘的信息，并且不会给实体增加意义。归根结底，这是你的选择。

## 语法

### 实体与关系

Mermaid 的 ER 图的语法与 PlantUML 兼容，有一个扩展来标记关系。 每个语句由以下部分组成：

```
    <first-entity> [<relationship> <second-entity> : <relationship-label>]
```

这里：

- `first-entity` 是一个实体的名称。名称必须以英文字母开头，也可以包含数字、连字符和下划线。
- `relationship` 描述了这两个实体相互关联的方式。见下文。
- `second-entity` 是另一个实体的名称。
- `relationship-label` 从第一个实体的角度来描述这种关系。

例如：

```
    PROPERTY ||--|{ ROOM : contains
```

这句话可以理解为 *一个属性包含一个或多个房间，而一个房间是一个且只有一个属性的一部分*。你可以看到，这里的标签是从第一个实体的角度出发的：一个属性包含一个房间，但一个房间不包含一个属性。 当从第二个实体的角度考虑时，通常很容易推断出等同的标签。（有些 ER 图从两个角度来标注关系，但这里不支持这样做，而且通常是多余的）。

只有声明中的 `first-entity` 部分是强制性的。这使得显示一个没有关系的实体成为可能，这在反复构建图表的过程中很有用。 如果一个声明的任何其他部分被指定，那么所有部分都是强制性的。

### 关系的语法

每个语句的 `relationship` 部分可以分解为三个子部分：

- 第一个实体相对于第二个实体的 cardinality。
- 这种关系是否赋予了 "子" 实体身份
- 第二个实体相对于第一个实体的 cardinality

Cardinality 是一个描述另一个实体的多少个元素可以与有关实体相关的属性。在上面的例子中，一个 `PROPERTY` 可以有一个或多个 `ROOM` 实例与之相关联，而一个 `ROOM` 只能与一个 `PROPERTY` 相关联。在每个心数标记中，有两个字符。最外面的字符代表一个最大值，最里面的字符代表一个最小值。下表总结了可能的基数：

| Value (left) | Value (right) | Meaning                                                |
|:------------:|:-------------:|--------------------------------------------------------|
|     `\|o`     |      `o\|`     | Zero or one                                            |
|     `\|\|`     |      `\|\|`     | Exactly one                                            |
|     `}o`     |      `o{`     | Zero or more (no upper limit)                          |
|     `}\|`     |      `\|{`     | One or more (no upper limit)                           |

### 识别

关系可以被划分为 *identifying* 或 *non-identifying*，它们分别用实线或虚线来表示。当其中一个实体没有另一个实体就不能独立存在时，这一点就很重要。例如，一家为人们驾驶汽车提供保险的公司可能需要存储关于 `NAMED-DRIVER` 的数据。在建模时，我们可以先观察到一个 `CAR` 可以由许多 `PERSON` 的实例驾驶，而一个 `PERSON` 可以驾驶许多 `CAR` —— 这两个实体都可以在没有对方的情况下存在，所以这是一种非识别关系，我们可以在 Mermaid 中指定为：`PERSON }|..|{ CAR : "driver"`。注意关系中间的两个点，这将导致两个实体之间的虚线被画出来。但是当这种多对多的关系被分解成两个一对多的关系时，我们发现如果没有 `PERSON` 和  `CAR`，`NAMED-DRIVER` 就不可能存在——这种关系变得可以识别，可以用连字符来指定，转化成实线。

```
erDiagram
    CAR ||--o{ NAMED-DRIVER : allows
    PERSON ||--o{ NAMED-DRIVER : is
```

### 属性

可以通过指定实体名称和包含多个 `type name` 对的块来为实体定义属性，其中一个块由开头的 `{` 和结尾的 `}` 分隔。例如：

```
erDiagram
    CAR ||--o{ NAMED-DRIVER : allows
    CAR {
        string registrationNumber
        string make
        string model
    }
    PERSON ||--o{ NAMED-DRIVER : is
    PERSON {
        string firstName
        string lastName
        int age
    }
```

```{mermaid}
erDiagram
    CAR ||--o{ NAMED-DRIVER : allows
    CAR {
        string registrationNumber
        string make
        string model
    }
    PERSON ||--o{ NAMED-DRIVER : is
    PERSON {
        string firstName
        string lastName
        int age
    }
```

属性是在实体框内呈现的：

```
erDiagram
    CAR ||--o{ NAMED-DRIVER : allows
    CAR {
        string registrationNumber
        string make
        string model
    }
    PERSON ||--o{ NAMED-DRIVER : is
    PERSON {
        string firstName
        string lastName
        int age
    }
```

```{mermaid}
erDiagram
    CAR ||--o{ NAMED-DRIVER : allows
    CAR {
        string registrationNumber
        string make
        string model
    }
    PERSON ||--o{ NAMED-DRIVER : is
    PERSON {
        string firstName
        string lastName
        int age
    }
```

`type` 和 `name` 的值必须以字母开头，可以包含数字、连字符或下划线。 除此以外，没有任何限制，也没有隐含的有效数据类型集。

#### 属性的键和注释

属性也可以有一个 `key` 或注释的定义。键可以是 "PK" 或 "FK"，表示主键或外键。而 `comment` 是在属性的末尾用引号来定义的。评论本身不能有引号字符。

```
erDiagram
    CAR ||--o{ NAMED-DRIVER : allows
    CAR {
        string allowedDriver FK 'The license of the allowed driver'
        string registrationNumber
        string make
        string model
    }
    PERSON ||--o{ NAMED-DRIVER : is
    PERSON {
        string driversLicense PK 'The license #'
        string firstName
        string lastName
        int age
    }
```

```{mermaid}
erDiagram
    CAR ||--o{ NAMED-DRIVER : allows
    CAR {
        string allowedDriver FK 'The license of the allowed driver'
        string registrationNumber
        string make
        string model
    }
    PERSON ||--o{ NAMED-DRIVER : is
    PERSON {
        string driversLicense PK 'The license #'
        string firstName
        string lastName
        int age
    }
```

### 其他事项

- 如果你想让关系标签超过一个字，你必须在这个短语周围使用双引号。
- 如果你不希望在一个关系上有任何标签，你必须使用一个空的双引号字符串

## 风格

### 配置选项

用于简单的颜色定制。

| Name     | Used as                                                              |
| :------- | :------------------------------------------------------------------- |
| `fill`   | Background color of an entity or attribute                           |
| `stroke` | Border color of an entity or attribute, line color of a relationship |

### 使用的类

以下的 CSS 类选择器可用于更丰富的样式设计。

| Selector                   | Description                                           |
| :------------------------- | :---------------------------------------------------- |
| `.er.attributeBoxEven`     | The box containing attributes on even-numbered rows   |
| `.er.attributeBoxOdd`      | The box containing attributes on odd-numbered rows    |
| `.er.entityBox`            | The box representing an entity                        |
| `.er.entityLabel`          | The label for an entity                               |
| `.er.relationshipLabel`    | The label for a relationship                          |
| `.er.relationshipLabelBox` | The box surrounding a relationship label              |
| `.er.relationshipLine`     | The line representing a relationship between entities |
