+++
title = "进阶操作"
date = 2021-03-06T15:09:55+08:00
weight = 100
chapter = true
pre = "<b>📜 </b>"

+++

本章节将会简短地重新介绍一遍 ink ，并且介绍一些进阶的操作以及编译的原理。

# 深入探究

在开始深入探究 ink 之前，我们需要对 ink 的一些名词和相关的技术栈有初步的了解。

## ink的工具链

* [Ink](https://www.inklestudios.com/ink) 是核心的叙事引擎，用C#编写。它包含了编译器的代码如果你并非专业人员，你不需要去关心这个。
* [Inky](https://www.github.com/inkle/inky) 是我们的编辑器，提供了一个能即时预览的文字编辑器。如果你是刚开始着手于ink，那么这就是你所需要的一切。
* [ink-unity-integration](https://www.github.com/inkle/ink-unity-integration) 是一个能让你将 ink 引擎集成在 Unity 游戏中的插件，它包含了所有的 Ink 引擎源代码。
* **inklecate** 是一个在命令行下的ink编译器。它被用于 Inky 的后台。
* [inkjs](https://github.com/y-lohse/inkjs) 是一个移植到 JavaScript 的 ink 引擎，驱动基于网页的游戏。它会在你用 inky 导出的网页故事中出现。
* [inkle](https://www.inklestudios.com) 是创造ink的游戏开发工作室。
* [inklewriter](https://www.inklewriter.com) 是一个与我们无关的被设计为易于使用的交互式故事创作工具，但是它的功能并不那么强大。可以将 inklewriter 故事导出为 ink ，但反过来却不行。

### 我需要用到什么？

如果你是

* **编剧 / 写手**：Inky
* **Unity 游戏开发者**： ink-unity-integration 插件. 如果你也同时在读/写 ink ，inky是可选的。
* **网页游戏作者**： Inky

### 关于它们的版本

为了确保工具间的正确使用，

- 发布在各自的 Github release page 的最新版本的 ink / inky / ink-unity-integration 应当能协同工作。虽然 Ink 和 Inky 的**版本号**是独立的。但你仍然可以在 About 栏中看见 inky 使用了哪个版本的 ink 引擎。
- ink / ink-unity-integration 在相同版本相同引擎的情况下应当产生相同的结果，除了集成插件可能会为 Unity 方面的更改而发行的额外的次要版本。但他们版本号 `X.0.0` 和 `0.Y.0` 中 X 与 Y 应当相同。在 ink-unity-integration 中类似的 `0.0.Z` 版本号可能是标志着 Unity 方面的更改。
- inkjs 由社区进行开发维护 (主要是 @y-lohse 和 @ephread). 它通常会落后 ink 引擎一个大版本，但他们也同时在努力地赶上每个发行版的进度！
- ink 引擎同样有在代码内的可读格式和储存格式（参见源代码中的 Story.cs 和 StoryState.cs ）。

接下来的内容中我们将会介绍各个工具。