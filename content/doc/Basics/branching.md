+++
title = "分支 Branching"
date = 2021-03-20T15:09:55+08:00
weight = 12
chapter = false
pre = "<b>1.5 </b>"
+++

**Branching The Flow**

## 1.5.1 基础分支 Basic branching

用结点，选项与跳转来组成 choose-your-own 游戏的基础结构。

```
=== paragraph_1 === // 结点：第一段
你手握宝剑，站在墙边。
*   [打开大门] -> 跳转到结点：第二段
*   [破门而入] -> 跳转到结点：第三段
*   [转身回家] -> 跳转到结点：第四段

=== paragraph_2 === // 结点：第二段
你打开大门，走上小路
……
```

---

## 1.5.2 分支与合并 Branching and joining

使用跳转，作者可让故事线分支，也能让其再次合并，不会展示给玩家故事线已合并。

```
=== back_in_london === // 结点：回到伦敦
我们晚上九点四十五准时到了伦敦。
*   “没时间耽误了！”[] 我喊道。
    -> hurry_outside // 跳转到结点：赶到外面
*   “先生，让我们享受这一刻吧！”[] 我喊道。
    我的住人用力敲了下我的脑袋，把我拽到了门外。
    -> dragged_outside // 跳转到结点：拽到外面
*   [我们赶回家] -> hurry_outside
    
=== hurry_outside === // 结点：赶到外面
我们赶回在裁缝街的家 -> as_fast_as_we_could // 跳转到结点：尽可能的快

=== dragged_outside === //结点：拽到外面
他坚持要我们赶回在裁缝街的家
-> as_fast_as_we_could 跳转到结点：尽可能的快

=== as_fast_as_we_could === //结点：我们尽快
<> 尽可能的快。
```
---

## 1.5.3 故事线 The story flow

结点与跳转组成创造了最基本的故事线。这个故事线是“扁平的”（flat）—— 没有调用栈（注，编程用语。此处形容复杂），也没有跳转“返回”（returned）。

在大多数 ink 脚本中，故事线从顶部开始，像意面一样缠绕搅动，最终可喜可贺地到达了 -> END 。

这种非常宽松的结构可让作者续写，分支，合并，而无需关心结构的走向。无需用样板跟踪分支跳转或任何状态。

### **进阶**：循环

**Advanced: Loops**

你完全可以用跳转创造循环内容，并且 ink 能有些特性，如控制内容自己变化，选项何时可以选择。

可浏览“可变文本”和“条件选项”章节了解更多。

看，下面是一个循环，但绝不是一个好循环：

```
=== round ===
and
-> round
```