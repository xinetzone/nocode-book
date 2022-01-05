# 用户旅程图

> 用户旅程高度详细地描述了不同的用户在一个系统、应用程序或网站中完成特定任务的步骤。这种技术显示了当前（现状）的用户工作流程，并揭示了未来工作流程中需要改进的地方。——维基百科

Mermaid 可以呈现用户旅程图：

```
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
```

```{mermaid}
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
```

每个用户旅程被分成几个部分，这些部分描述了任务的一部分用户试图完成的部分。

任务的语法：`Task name: <score>: <comma separated list of actors>`
