+++
title = "选项 Choices"
date = 2021-03-20T15:09:55+08:00
weight = 9
chapter = false
pre = "<b>1.2 </b>"
+++

## 1.2.1 最简单的 ink 选项

可通过文字选项让玩家输入。文字选项用星号 `*` 标记 。

如无其他指示，选项会在下一行出现。

```plaintext
Hello world!
*	Hello back!
	Nice to hear from you!
```

```plaintext
Hello world 
1: Hello back! 

▶ 1
Hello back!
Nice to hear from you.
```
默认情况下，选项的文本也会再次输出到内容中。

---

## 1.2.2 不输出文本的选项 

**Suppressing choice text**

一些游戏文本内容与选项是分开的。在 ink 中，如用方括号 `[]` 括起来，选项的文本不会输出到内容中。

```plaintext
Hello world!
* [Hello back!]
  Nice to hear from you!
```

```plaintext
Hello world 
1: Hello back! 

▶ 1
Nice to hear from you.
```

### **进阶**：混合选项与输出文本

**Advanced: mixing choice and output text**

实际上，方括号将选项内容分离，这提供了一种有效率的方式来完成一个分支：

- 在它前面的内容，会成为选项且输出到内容；
- 在它里面的内容，会成为选项但不会输出到内容；
- 在它后面的内容，只会输出到内容。

```plaintext
Hello world!
* Hello [back!] right back to you!
  Nice to hear from you!
```

```plaintext
Hello world 
1: Hello back!

▶ 1
Hello right back to you!
Nice to hear from you.
```

这在写对话类的选项时非常有用。

```plaintext
“怎么了？” 我的主人问。
* “我有些累[。”]，”我回应道。
  “确实，”他说。“这不太好。”
```

```plaintext
“怎么了？” 我的主人问。
1: “我有些累。”

▶ 1
“我有些累，”我回应道。
“确实，”他说。“这不太好。”
```

---

## 1.2.3 多重选项 Multiple Choices

让选项真的成为选项，我们要提供更多的选项。我们只需简单地把它们罗列出来：

```plaintext
“怎么了？” 我的主人问。
* “我有些累[。”]，”我回应道。
  “确实，”他说。“这不太好。”
* “没使，先生！” []我回应道。
  “那好。”
* “我觉得，这场旅行太糟了[。”]我一点也不想再来一次了。”
  “啊，”他回应道，不是那种不友好的语气。“我看得出你很沮丧，但明天一切都会好起来的。”
```

上述的语法标记足以写出一组选项。在真正的游戏里，我们希望玩家进入不同分支的故事线。为了做到这一点我们需要更多的结构。