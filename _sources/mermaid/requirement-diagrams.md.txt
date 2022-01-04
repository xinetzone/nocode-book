# 需求图

> 需求图提供了一个可视化的需求和他们的连接，相互之间和其他记录的元素。建模规范遵循 SysML v1.6 所定义的规范。

渲染的需求是直接的。

````{panels}
:container: container-fluid pb-1
:column: col-12
:card: + shadow
:header: border-0 bg-info
```
    requirementDiagram

    requirement test_req {
    id: 1
    text: the test text.
    risk: high
    verifymethod: test
    }

    element test_entity {
    type: simulation
    }

    test_entity - satisfies -> test_req
```
---
```{mermaid}
    requirementDiagram

    requirement test_req {
    id: 1
    text: the test text.
    risk: high
    verifymethod: test
    }

    element test_entity {
    type: simulation
    }

    test_entity - satisfies -> test_req
```
````

## 语法

需求图有三种类型的组件：需求，元素，和关系。

定义每一个的语法在下面定义。用角括号表示的词，如 ```<word>```，是列举的关键词，其选项在表格中阐述。```user_defined_...``` 在任何需要用户输入的地方使用。

关于用户文本的一个重要说明：所有输入可以用引号包围，也可以不用。例如，```Id: "here is an example"``` 和 ```Id: here is an example``` 都是有效的。然而，用户必须小心对待没有引号的输入。如果检测到另一个关键词，解析器将失败。

### 需求

一个需求定义包含一个需求 `type`、`name`、`id`、`text`、`risk` 和 `verifymethod`。语法如下：

```
<type> user_defined_name {
    id: user_defined_id
    text: user_defined text
    risk: <risk>
    verifymethod: <method>
}
```
---

类型、风险和方法是 SysML 中定义的枚举。

| 关键字 | 选项 |
|---|---|
| Type | requirement, functionalRequirement, interfaceRequirement, performanceRequirement, physicalRequirement, designConstraint |
| Risk | Low, Medium, High |
| VerificationMethod | Analysis, Inspection, Test, Demonstration |

### 元素

一个元素定义包含一个元素名称、类型和文档参考。这三个都是用户定义的。元素功能的目的是轻量级的，但允许需求与其他文件的部分相连。

```
element user_defined_name {
    type: user_defined_type
    docref: user_defined_ref
}
```

### 关系

关系是由源节点、目的节点和关系类型组成的。

每个关系都遵循以下的定义格式

```
{name of source} - <type> -> {name of destination}
```

或

```
{name of destination} <- <type> - {name of source}
```

"源的名称 "和 "目的的名称" 应该是在其他地方定义的需求或元素节点的名称。

关系类型可以是包含，复制，派生，满足，验证，细化，或追踪中的一种。

每个关系在图中都有标记。

## 大型案例

这个例子使用了图表的所有功能。

```
    requirementDiagram

    requirement test_req {
    id: 1
    text: the test text.
    risk: high
    verifymethod: test
    }

    functionalRequirement test_req2 {
    id: 1.1
    text: the second test text.
    risk: low
    verifymethod: inspection
    }

    performanceRequirement test_req3 {
    id: 1.2
    text: the third test text.
    risk: medium
    verifymethod: demonstration
    }

    interfaceRequirement test_req4 {
    id: 1.2.1
    text: the fourth test text.
    risk: medium
    verifymethod: analysis
    }

    physicalRequirement test_req5 {
    id: 1.2.2
    text: the fifth test text.
    risk: medium
    verifymethod: analysis
    }

    designConstraint test_req6 {
    id: 1.2.3
    text: the sixth test text.
    risk: medium
    verifymethod: analysis
    }

    element test_entity {
    type: simulation
    }

    element test_entity2 {
    type: word doc
    docRef: reqs/test_entity
    }

    element test_entity3 {
    type: "test suite"
    docRef: github.com/all_the_tests
    }


    test_entity - satisfies -> test_req2
    test_req - traces -> test_req2
    test_req - contains -> test_req3
    test_req3 - contains -> test_req4
    test_req4 - derives -> test_req5
    test_req5 - refines -> test_req6
    test_entity3 - verifies -> test_req5
    test_req <- copies - test_entity2
```

```{mermaid}
    requirementDiagram

    requirement test_req {
    id: 1
    text: the test text.
    risk: high
    verifymethod: test
    }

    functionalRequirement test_req2 {
    id: 1.1
    text: the second test text.
    risk: low
    verifymethod: inspection
    }

    performanceRequirement test_req3 {
    id: 1.2
    text: the third test text.
    risk: medium
    verifymethod: demonstration
    }

    interfaceRequirement test_req4 {
    id: 1.2.1
    text: the fourth test text.
    risk: medium
    verifymethod: analysis
    }

    physicalRequirement test_req5 {
    id: 1.2.2
    text: the fifth test text.
    risk: medium
    verifymethod: analysis
    }

    designConstraint test_req6 {
    id: 1.2.3
    text: the sixth test text.
    risk: medium
    verifymethod: analysis
    }

    element test_entity {
    type: simulation
    }

    element test_entity2 {
    type: word doc
    docRef: reqs/test_entity
    }

    element test_entity3 {
    type: "test suite"
    docRef: github.com/all_the_tests
    }


    test_entity - satisfies -> test_req2
    test_req - traces -> test_req2
    test_req - contains -> test_req3
    test_req3 - contains -> test_req4
    test_req4 - derives -> test_req5
    test_req5 - refines -> test_req6
    test_entity3 - verifies -> test_req5
    test_req <- copies - test_entity2
```
