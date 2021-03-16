+++
title = "在命令行下使用 inklecate"
date = 2021-03-06T15:09:55+08:00
weight = 99
pre = "<b>1. </b>"

+++

你也许在某些情况下会在命令行中使用 ink ，幸运的是，我们有 **inklecate** 这一命令行下的工具

 1. [下载 **inklecate** 的最新版本](https://github.com/inkle/ink/releases) (或者自行构建)
 3. 在命令行中执行如下命令：

    **Mac:**  `./inklecate -p myStory.ink`

    **Windows:**  `inklecate.exe -p myStory.ink`

    **Linux:**  `mono inklecate.exe -p myStory.ink`

    *在Linux上运行需要Mono runtime 以及 Mono System.Core library (for CLI 4.0). 如果你使用 debian repository ，你可以用这个命令来安装：* <br>
    `sudo apt install mono-complete`

    使用参数 `-p` 进入游玩模式，可以在命令行中运行 ink 游戏。 如果你想编译为 `.json` 文件，只需要把上面例子中的 `-p` 去掉即可。



有关编译出来的 json 文件结构，参见 *使用 json* （施工中）