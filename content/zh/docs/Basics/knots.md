---
title: "1.3 结点 Knots"
date: 2021-03-20
weight: 10
chapter: false
pre: "<b>1.3 </b>"
---

## 1.3.1 内容片段被称作结点

**Pieces of content are called knots**

为了让游戏有分支，我们需要给内容片段标记上标题。

这些内容片段叫做“结点”，是 ink 最基本的结构单元。

---

## 1.3.2 写个结点 Writing a knot

结点的开头由两个或更多等号 `==` 构成，例如  `=== top_knot ===` 。

（右侧等号是可选的，结点标题的名称是不能有空格的单词。注，不支持中文。）

结点标记下的内容均属于这个结点。

```c
=== back_in_london === // 结点：回到伦敦

我们晚上九点四十五准时到了伦敦。
```

### **进阶**：从始至终 

**Advanced: a knottier "hello world"**

当你启动一个 ink 文件，结点外的内容会被自动运行，而结点不会。因此如果你开篇就是结点，就要告诉游戏从哪开始。我们要用一个跳转箭头 `->` ，下一节会具体说明。

```
-> top_knot

=== top_knot ===
Hello world！
```

除此之外，ink 不喜欢“不实在的结尾”（loose end），当识别到时会发出如下的警告：

```plaintext
WARNING: Apparent loose end exists where the flow runs out. Do you need a '-> END' statement, choice or divert? on line 3 of tests/test.ink
```
运行时则是这样的：

```plaintext
Runtime error in tests/test.ink line 3: ran out of content. Do you need a '-> DONE' or '-> END'?
```

这样就不会报错了：

```
=== top_knot ===
Hello world！
-> END
```

`-> END` 同时是作者与编译器的标记，它意味着“故事线到这就结束了”。