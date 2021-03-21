+++
title = "针脚 Stitches"
date = 2021-03-20T15:09:55+08:00
weight = 15
chapter = false
pre = "<b>1.6 </b>"
+++

**Includes and Stitches**

## 1.6.1 结点可有子结点

**Knots can be subdivided**

随着故事越来越长，在没有其他结构的情况下会越来越乱，难以保持秩序。

结点可以包括被称为“针脚”的子结点。它们用单个等号 `=` 标记。

```
=== the_orient_express === // 结点：东方快车
= in_first_class // 针脚：头等厢
	……
= in_third_class // 针脚：三等厢
	……
= in_the_guards_van // 针脚：警务车厢
	……
= missed_the_train // 针脚：错过火车
	……
```

例如可以将场景作结点，里面的事件作为针脚。

---

## 1.6.2 针脚有唯一的名称

**Stitches have unique names**

针脚可跳转到它的“位置”（address）。

```
* [前往三等厢]
  -> the_orient_express.in_third_class // 跳转到针脚：东方快车结点，三等厢针脚

* [前往警务车厢]
  -> the_orient_express.in_the_guards_van //跳转到针脚： 东方快车结点，警务车厢针脚
```

---

## 1.6.3 第一个针脚是默认的

**The first stitch is the default**

如果结点内包含针脚，会默认跳转到结点内的第一个针脚。

```c
* [前往头等厢]
  “头等厢, 先生。 还有其他地方吗？”
  -> the_orient_express // 跳转到结点：东方快车
```

等同于（...除非我们改变结点内针脚的顺序！）：

```
* [前往头等厢]
  “头等厢, 先生。 还有其他地方吗？”
  -> the_orient_express.in_first_class // 跳转到针脚：东方快车结点，头等厢
```

你也可以在针脚的顶部与结点间加入任何内容，但注意此时不会再自动进入第一个针脚。

```
=== the_orient_express ===  // 结点：东方快车
我们上车了，但是去哪？
* [头等厢] -> in_first_class // 跳转到针脚：头等厢
* [二等厢] -> in_second_class //跳转到针脚：三等厢

= in_first_class // ✨ 不会再自动进入第一个针脚
  ……
= in_second_class // 针脚：三等厢
  ……
```

---

## 1.6.4 本地跳转 Local diverts

在结点内部，你无需针脚的完整地址。

```
-> the_orient_express // 跳转到结点：东方快车

=== the_orient_express === // 结点：东方快车
= in_first_class // 针脚：头等厢
  我安顿好我的主人。
  * [前往三等厢]
    -> in_third_class // ✨ 跳转到针脚：三等厢
= in_third_class // 针脚：三等厢
  我坐下来了。
```

这意味着针脚与结点不能共享名称，但不同的结点里可以有相同名称的针脚。（像东方快车与蒙古专列都可以有头等舱。）如你使用了不明确的名称，编译器会发出警告。

---

## 1.6.5 脚本文件可联合

**Script files can be combined**

你可用 INCLUDE 语句将内容拆到多个文件里。

```
INCLUDE newspaper.ink
INCLUDE cities/vienna.ink
INCLUDE journeys/orient_express.ink
```

INCLUDE 语句必须在文件顶部，而非结点内部。

结点跳转到哪个文件并没有限制，换句话说，分割文件并不会影响游戏的命名空间（namespacing） 。