+++
title = "准备 Inky"
date = 2021-03-06T15:09:55+08:00
weight = 10
chapter = false
pre = "<b>0. </b>"
+++

## 获取 Inky

Ink 是一门讲故事的“语言”。

我们要用 Ink 语言的官方编辑器 Inky 进行创作，这只需简单的3步：

1. {{% button href="https://github.com/inkle/inky/releases" icon="fas fa-download" %}}下载最新版 Inky{{% /button %}} ，支持 Windows，macOS，Linux ； 
2. 解压下载好的压缩包到合适的位置；
3. 以 Windows 为例，双击运行 **Inky.exe** 。


![inky](/images/learn/logo.png)

你会发现，Inky 直接启动就绪了 —— 是款免安装的“绿色软件”，这也是为什么本节标题不叫“安装 Inky”的原因。

{{%expand "🔎 展开 Inky 界面…" %}}![inky](/images/learn/inky.png){{% /expand%}}

Inky 是左右双栏的编辑器，在**左栏编辑攥写**，在**右栏实时预览**。此时 Inky 在左栏已预置了些内容（虽然不是 Hello World），你可以随意编辑试试写写看；并点击右栏里的预览看看会发生什么。

{{%expand "🔎 展开 预置内容…" %}}

```
Once upon a time...

 * There were two choices.
 * There were four lines of content.

- They lived happily ever after.
    -> END
```

```
曾几何时…

* 有两个选择。
* 有四行内容。

- 从此他们过着幸福的生活。
    -> END //剧终
```  
{{% /expand%}}

{{% notice tip %}}
[Github 下载慢？](https://www.zhihu.com/question/276143842) / [Gitee 镜像](https://gitee.com/xun-lang/inky/releases)
{{% /notice %}}

---

## 认识 Inky

{{% notice info %}}
本页面介绍的 Inky 版本是 V0.12
{{% /notice %}}

### 菜单栏

![inky](/images/learn/inky1.png)

这里虽然有7个菜单按钮，一般我们只会用到 **File** 菜单来新建、打开、保存、导出工程。具体用法会在后面用到时细说。

{{%expand "🔎 展开 菜单说明…" %}}
- File：新建、打开、保存、导出工程等；
- Edit：撤销、重做，剪切、复制、粘贴、全选，快捷键说明；
- View：全屏，主题（明暗），缩放文本；
- Story：【待补充】；
- Ink：输入语法模板；
- Window：控制窗口，开发模式等；
- Help：文档，关于。
  {{% /expand%}}

### 编辑区

让我们先看看，

![inky](/images/learn/inky2.png)

- 编辑区↖左上方：三线菜单展开文件浏览；两个左右三角箭头可帮你切换光标的历史位置，这对编辑较长的故事时很有用。

- 编辑区⬆正上方：状态栏，通常用来提醒你编辑器检查到语法错误警告信息（不要害怕它们，能让实时检测语法错误会很有帮助的；以及 Ink 语法很简单，处理大多数问题也很容易）。

- 编辑区↗右上方：**单箭头是后退**，**双箭头是重启**，这在你预览故事时很有用，比如后退到上一个选择选别的选项试试。

![inky](/images/learn/inky3.gif)

编辑区**左侧是编辑区**，**右侧是预览区**，当我们在左侧编辑攥写内容时，右侧就能实时预览读者玩家看到的内容，并可能游玩体验非常方便。

{{% notice note %}}
常用快捷键：撤销 = Ctrl+Z ；寻找 = Ctrl+F ，替换 = Ctrl+H ；跳转 = Ctrl+P ；注释 = Ctrl+/ ；多行光标操作 = Ctrl+Alt+↑/↓ ；临时折叠 = Alt+L ；整行移动 = Alt+↑/↓ 。你可在 Edit 菜单中随时查看快捷键用法。
{{% /notice %}}

---


## Hello world

学习任何一门理性的编程语言似乎都是从输出 Hello World 开始的，但 Inkl 作为一门讲故事的语言要感性得多。因此，下面就给你一个故事片段让你先试试看，把它复制到 Inky 左侧试试看，你可以随意编辑甚至续写这个故事，看看右侧预览区会有什么变化。

```
伦敦，1872年
Phileas Fogg 先生的住所。

-> london


=== london === //这是节点
Phileas Fogg 先生早早从改革俱乐部回到了家，并乘坐了新型的蒸汽运输机！   
“领航,” 他喊到。 "我们去环游世界！"

+ “环游世界，先生？” 
    我大吃一惊。
    
    -> astonished
    
+ [点头。] -> nod


=== astonished ===
“你在开玩笑！” 我认真地对他说。“你一定是在和我开玩笑，先生。” 
“我很认真。” 

+ “好吧。”

    -> ending


=== nod ===
我点了点头，但不相信一个字。

-> ending


=== ending //这也是节点


# CLASS: end
“我们将在八十天内环游地球。” 他很平静地提出了这个近乎疯狂地计划“我们8:25去巴黎。一小时后。”

-> END

```

若你从未接触过编程，左侧编辑区的蓝色字符是否让你有些“望而生畏”？但不要紧张，这实际上是一种类似于 Markdown 的标记语法，非常简单易学，会在后面遇到时教会你。

那么我们的故事像 Hello World 一样“输出”后是什么样的呢？{{% button href="https://ink-demo.magicoder.org" icon="fas fa-paw" %}}查看示例{{% /button %}}

看起来是个普通，可做选择的故事片段网页而已 —— 可以更有趣些吗？

---

---

👉 下一节我们会开始学习 Ink 语法。