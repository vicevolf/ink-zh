---
title: "1.9 查询与函数 Queries and Functions"
date: 2021-03-20
weight: 20
---

**Game Queries and Functions**

INK 提供了一些用于条件逻辑的，关于游戏状态“game level”的查询。它们不是语言的一部分，但它们总是可用的，且不能由作者修改。某种意义上讲，它们是语言的“标准库函数”。惯例是用**大写字母**来命名。

## 1.9.1 CHOICE_COUNT()

`CHOICE_COUNT` 返回到目前为止，当前区域内的选项数，例如：

```
* {false} Option A //false 条件判定为假，不显示

* {true} Option B //true 条件判定为真，显示

* {CHOICE_COUNT() == 1} Option C //条件：选项数等于1
```

输出选项 B 与 C 。这在控制玩家一回合内有多少选项是很有用的。

---

## 1.9.2 TURNS()

`TURNS` 返回自游戏开始以来的回合数。

---

## 1.9.3 TURNS_SINCE(-> knot)

**TURNS_SINCE** 返回自上次浏览，经历过特定结点或针脚的次数（严格地说，玩家输入的）。

- 值为0表示正在经历此处；
- 值为-1表示从未经历过此处；
- 任何正数都表示已经历此处多次了。

```
* {TURNS_SINCE(-> sleeping.intro) > 10} 你觉得很累…… -> sleeping 
* {TURNS_SINCE(-> laugh) == 0} 你尝试不笑了->END
```

注意这里传给 TURNS_SINCE 的参数是“跳转目标”，而非结点地址本身。（因为结点地址是一个数字 —— 读取计数 ——而非故事中的位置…）

### 预览：函数中使用 TURNS_SINCE

**Sneak preview: using TURNS_SINCE in a function**

`TURNS_SINCE(->x) == 0` 检测是非常有用的，通常值得包装成一个 ink 函数。

```
=== function came_from(-> x) 

  ~ return TURNS_SINCE(x) == 0
```

函数部分更具体的说明了这部分语法，但上面的内容你大致可这样用：

```
* {came_from(->  nice_welcome)} 'I'm happy to be here!' 

* {came_from(->  nasty_welcome)} 'Let's keep this quick.'
```

…让游戏对玩家看到的内容做出反应。

## 1.9.4 SEED_RANDOM()

出于测试目的，固定随机数生成器通常很有用，这会让你每次游玩时输出相同的结果。你可用随机数种子系统来实现这一目的。

```
~ SEED_RANDOM(235)
```

传递给种子函数的数字可以是任意的，但提供不同的种子将导致不同的结果序列。

### 进阶：更多查询

**Advanced: more queries**

你可制作自己的外部函数，尽管语法有些不同。详见函数下面。