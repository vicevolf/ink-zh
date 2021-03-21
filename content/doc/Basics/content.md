+++
title = "内容 Content"
date = 2021-03-20T15:09:55+08:00
weight = 8
chapter = false
pre = "<b>1.1 </b>"
+++

## 1.1.1 最简单的 ink 脚本

**The simplest ink script**

最基本的 ink 脚本就是 .ink 文件中的普通文本而已：

```
Hello, world!
```
当运行时，它们会输出为内容，然后停止。

每行文本都会生成新段落。例如：

```plaintext
Hello, world!
Hello?
Hello, are you there?
```
输出的内容看起来与文本一模一样的。

---

## 1.1.2 注释 Comments

通常文件中的所有文本都会输出为内容，除非有特殊标记。

最简单的语法标记是注释。Ink 支持两种注释方式。它们是方便人们阅读代码用的，而编译器会将它们忽略。

```plaintext
“你怎么看？”她问。

// 不会被输出的内容…

“我无法评论（comment），”我答。

/*
	…或是无行数行数限制的文本块
*/
```

另一种则是用于提醒作者还要去做什么，会被编译器提醒：

```plaintext
TODO: 这块认真写！
```

---

## 1.1.3 标识 Tags

当引擎运行时，文本会按原样呈现。不过有时我们需要标记一行内容提供额外的信息，告诉游戏该怎么运行。

ink 提供了一个简单的系统，使用井号 `#` 为内容添加标识。

```
一行普通的游戏内文本。 # colour it blue
```

它们不会被展示在内容中，但可被游戏读取到，以便你按需使用。详见 [RunningYourInk](https://github.com/inkle/ink/blob/master/Documentation/RunningYourInk.md#marking-up-your-ink-content-with-tags) 。