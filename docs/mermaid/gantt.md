# 甘特图

> 甘特图是一种条形图，由 Karol Adamiecki 在 1896 年首次开发，并由 Henry Gantt 在 1910 年代独立开发，说明了项目进度和任何一个项目完成所需的时间量。甘特图说明了一个项目的终端要素和摘要要素的开始和结束日期之间的天数。

## 给用户的说明

甘特图将把每个计划任务记录为一个连续的条形，从左边延伸到右边。X 轴代表时间，Y 轴记录不同的任务和它们完成的顺序。

重要的是要记住，当一个任务的特定日期、日子或日期集合被 "排除" 时，甘特图将通过向右延伸相同数量的日子来适应这些变化，而不是在任务内部创建一个缺口。

但是，如果被排除的日期在两个被设定为连续开始的任务之间，被排除的日期将被图形化地跳过，留出空白，下面的任务将在被排除日期结束后开始。

甘特图对于跟踪一个项目完成前所需的时间非常有用，但它也可以用来用图形表示 "非工作日"，只需做一些调整。

Mermaid 可以将甘特图呈现为 SVG、PNG 或 MarkDown 链接，可以粘贴到文档中。

```
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section Section
    A task           :a1, 2014-01-01, 30d
    Another task     :after a1  , 20d
    section Another
    Task in sec      :2014-01-12  , 12d
    another task      : 24d
```

```{mermaid}
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section Section
    A task           :a1, 2014-01-01, 30d
    Another task     :after a1  , 20d
    section Another
    Task in sec      :2014-01-12  , 12d
    another task      : 24d
```

## 语法


```
gantt
    dateFormat  YYYY-MM-DD
    title       Adding GANTT diagram functionality to mermaid
    excludes    weekends
    %% (`excludes` accepts specific dates in YYYY-MM-DD format, days of the week ("sunday") or "weekends", but not the word "weekdays".)

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
    Functionality added                 :milestone, 2014-01-25, 0d

    section Documentation
    Describe gantt syntax               :active, a1, after des1, 3d
    Add gantt diagram to demo page      :after a1  , 20h
    Add another diagram to demo page    :doc1, after a1  , 48h

    section Last section
    Describe gantt syntax               :after doc1, 3d
    Add gantt diagram to demo page      :20h
    Add another diagram to demo page    :48h
```

```{mermaid}
gantt
    dateFormat  YYYY-MM-DD
    title       Adding GANTT diagram functionality to mermaid
    excludes    weekends
    %% (`excludes` accepts specific dates in YYYY-MM-DD format, days of the week ("sunday") or "weekends", but not the word "weekdays".)

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
    Functionality added                 :milestone, 2014-01-25, 0d

    section Documentation
    Describe gantt syntax               :active, a1, after des1, 3d
    Add gantt diagram to demo page      :after a1  , 20h
    Add another diagram to demo page    :doc1, after a1  , 48h

    section Last section
    Describe gantt syntax               :after doc1, 3d
    Add gantt diagram to demo page      :20h
    Add another diagram to demo page    :48h
```

可以设置多个依赖关系，用空格隔开：

```
    gantt
        apple :a, 2017-07-20, 1w
        banana :crit, b, 2017-07-23, 1d
        cherry :active, c, after b a, 1d
```

```{mermaid}
    gantt
        apple :a, 2017-07-20, 1w
        banana :crit, b, 2017-07-23, 1d
        cherry :active, c, after b a, 1d
```

### 标题

`title` 是一个 *可选的* 字符串，显示在甘特图的顶部，用来描述整个图表。

### 章节声明

你可以将图表划分为不同的部分，例如将项目的不同部分如开发和文档分开。

为此，用 `section` 关键字开始一行，并给它一个名字。（注意，与 [整个图表的标题](#标题) 不同，这个名字是 *必须的*）。

### 里程碑

你可以在图表中添加里程碑。里程碑与任务不同，它们代表一个单一的时间点，并以关键字 `milestone` 来标识。下面是一个关于如何使用里程碑的例子。你可能会注意到，里程碑的确切位置是由里程碑的初始日期和任务的 "duration" 决定的，这种方式：*initial date*+*duration*/2。

```
gantt 
dateFormat HH:mm
axisFormat %H:%M
Initial milestone : milestone, m1, 17:49,2min
taska2 : 10min
taska3 : 5min 
Final milestone : milestone, m2, 18:14, 2min
```

```{mermaid}
gantt 
dateFormat HH:mm
axisFormat %H:%M
Initial milestone : milestone, m1, 17:49,2min
taska2 : 10min
taska3 : 5min 
Final milestone : milestone, m2, 18:14, 2min
```

## 设置日期

`dateFormat` 定义了你的甘特图元素的日期 **input** 的格式。这些日期如何在渲染的图表 **output** 中表示，由 `axisFormat` 定义。

### date 输入格式

默认的输入日期格式是 `YYYY-MM-DD`。你可以定义你的自定义 ``dateFormat``。

```
dateFormat YYYY-MM-DD
```

支持以下格式化选项：

```
Input       Example             Description:
YYYY        2014                4 digit year
YY          14                  2 digit year
Q           1..4                Quarter of year. Sets month to first month in quarter.
M MM        1..12               Month number
MMM MMMM    January..Dec        Month name in locale set by moment.locale()
D DD        1..31               Day of month
Do          1st..31st           Day of month with ordinal
DDD DDDD    1..365              Day of year
X           1410715640.579      Unix timestamp
x           1410715640579       Unix ms timestamp
H HH        0..23               24 hour time
h hh        1..12               12 hour time used with a A.
a A         am pm               Post or ante meridiem
m mm        0..59               Minutes
s ss        0..59               Seconds
S           0..9                Tenths of a second
SS          0..99               Hundreds of a second
SSS         0..999              Thousandths of a second
Z ZZ        +12:00              Offset from UTC as +-HH:mm, +-HHmm, or Z
```

更多信息见：http://momentjs.com/docs/#/parsing/string-format/

### 在轴上输出日期格式

默认的输出日期格式是 YYY-MM-DD。你可以定义你的自定义 ``axisFormat``，比如 `2020-Q1` 表示 2020 年的第一季度。

```
axisFormat  %Y-%m-%d
```

支持以下格式化字符串：

```
%a - abbreviated weekday name.
%A - full weekday name.
%b - abbreviated month name.
%B - full month name.
%c - date and time, as "%a %b %e %H:%M:%S %Y".
%d - zero-padded day of the month as a decimal number [01,31].
%e - space-padded day of the month as a decimal number [ 1,31]; equivalent to %_d.
%H - hour (24-hour clock) as a decimal number [00,23].
%I - hour (12-hour clock) as a decimal number [01,12].
%j - day of the year as a decimal number [001,366].
%m - month as a decimal number [01,12].
%M - minute as a decimal number [00,59].
%L - milliseconds as a decimal number [000, 999].
%p - either AM or PM.
%S - second as a decimal number [00,61].
%U - week number of the year (Sunday as the first day of the week) as a decimal number [00,53].
%w - weekday as a decimal number [0(Sunday),6].
%W - week number of the year (Monday as the first day of the week) as a decimal number [00,53].
%x - date, as "%m/%d/%Y".
%X - time, as "%H:%M:%S".
%y - year without century as a decimal number [00,99].
%Y - year with century as a decimal number.
%Z - time zone offset, such as "-0700".
%% - a literal "%" character.
```

更多信息见：https://github.com/mbostock/d3/wiki/Time-Formatting

## Today 标记

你可以设计或隐藏当前日期的标记。要设计它，请为 `todayMarker` 键添加一个值。

```
todayMarker stroke-width:5px,stroke:#0f0,opacity:0.5
```

要隐藏标记，将 `todayMarker` 设置为 `off`。

```
todayMarker off
```
