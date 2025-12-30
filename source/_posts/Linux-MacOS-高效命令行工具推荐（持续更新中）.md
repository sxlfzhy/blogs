---
title: Linux/MacOS 高效命令行工具推荐（持续更新中）
date: 2025-08-08 12:33:46
tags:
  - 效率工具
  - Linux
---

本文整理了 Linux/macOS 系统下能显著提升工作效率的命令行工具，这些工具经过作者日常使用验证，了解这些，你会爱上 Linux命令行。

Linux 系统中提供了很多基础命令，如`cd`、`top`、`cat`等，这些命令就像是上个世纪的工具，能用但不好用更不美观。熟练使用下面这些命令，将可以使你的终端效率提高十倍。

## 工具清单与核心推荐

### yazi ⭐️⭐️⭐️⭐️⭐️

> 最好用的终端文件管理器，可以快速查看/切换文件，查找文件，进行编辑/删除，复制等操作。

**Yazi** 是一款基于 Rust 编写的终端文件管理器，专为需要快速、灵活和异步文件管理的用户设计。Yazi 的目标是提供一个简洁且高效的终端文件管理体验。如果你正在寻找一款高效且强大的终端文件管理工具，Yazi 无疑是一个值得尝试的选择。

- **官网：** [https://yazi-rs.github.io](https://yazi-rs.github.io)

- **优势：**

  - 导航：目录导航、光标移动
  - 文件操作：查看、编辑、创建、删除、重命名等
  - 其他操作：文件列表排序、查找文件、复制路径

- **资源：**

  - [【命令行必备】Yazi：最强文件管理器_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1yRkCYVEUT/?spm_id_from=333.337.search-card.all.click&vd_source=5d876fc94223e09ca29ed660ffc5224f)
  - [x-cmd演示效果](https://cn.x-cmd.com/1min/yazi)

![yazi使用截图](https://static.lanyangyang.me/img/2025/12/b6ad61d127482dfe7674d6409d303554.png)

---

### zoxide(z) ⭐️⭐️⭐️⭐️⭐️

> cd 命令替代工具，cd的升级版，比cd命令爽太多了。

传统的 `cd` 命令虽然简单，但在频繁切换目录时效率较低。而 `zoxide` 通过记录用户访问过的目录，并根据访问频率和最近使用情况进行排序，使得用户可以通过输入部分目录名称快速跳转到目标目录。`zoxide` 的核心理念是“少输入，多产出”，通过最少的输入实现最快的目录跳转。

- **官网：** [https://github.com/ajeetdsouza/zoxide](https://github.com/ajeetdsouza/zoxide?tab=readme-ov-file)
- **优势：**
  - **智能学习：** zoxide 会根据用户的使用习惯，智能地学习和排序目录。用户访问频率越高的目录，跳转时所需输入的字符越少。
  - **快速跳转：** 支持模糊匹配，输入 `z proj` 即可跳转 `~/code/projects`
- **推荐配置**（.zshrc/.bashrc）：

```bash
eval "$(zoxide init --cmd z --hook pwd)"
alias cd="z"  # 彻底替代 cd
```

- **演示：**

![zoxide使用效果](https://static.lanyangyang.me/img/2025/12/1f11546c0272e42177f8333c104dd696.png)

---

### bat ⭐️⭐️⭐️⭐️⭐️

> 增强版文件查看器，替代cat

`cat`命令只是简单的输出，而 `bat` 是包含语法高亮的文件查看器，同时提供一些更复杂的功能。

- **官网：** [https://github.com/sharkdp/bat](https://github.com/sharkdp/bat)
- **优势：**
  - **语法高亮：** `bat` 对大部分编程语言和标记语言提供语法高亮
  - **不可打印(non-printable)字符可视化：** 添加 `-A` 参数可以文件文件中的不可打印字符
- **推荐配置：**

```bash
alias cat="bat --paging=never"
```

- **演示：** [https://cn.x-cmd.com/1min/bat](https://cn.x-cmd.com/1min/bat)

![bat命令演示](https://static.lanyangyang.me/img/2025/12/33c5c31596e9b609ec7c1c8591e070f4.png)

### glances ⭐️⭐️⭐️⭐️⭐️

> 开源系统监控神器，助你洞察系统运行状态，替代 top ！

**Glances**是一款开源的跨平台系统监控工具，专为中国用户设计，让你一眼掌握计算机的健康状态。无论是服务器管理、个人电脑维护，还是容器监控，Glances都能提供全面、实时的系统数据，让你对硬件和软件状况了如指掌。

- **官网：** [https://github.com/nicolargo/glances](https://github.com/nicolargo/glances)
- **优势：**
  - 实时显示CPU、内存、磁盘、网络等系统资源的使用情况，比 Top 展示的内容更多
  - 支持硬件传感器监控，确保硬件运行在安全范围内
  - 通过直观的图表和Dashboard，信息一目了然

![glances命令演示](https://static.lanyangyang.me/img/2025/12/5756b65b91edfda72fbccdadd041615f.png)

### eza ⭐️⭐️⭐️⭐️

> ls 替代工具

eza 的主要功能是列出目录的内容。它与`ls`命令的主要区别是采用了以颜色区分文件类型的方式，让界面更加吸引人和易读。

- **官网：** [https://github.com/eza-community/eza](https://github.com/eza-community/eza)
- **优势：** 好看
- **更多：** [eza-themes](https://github.com/eza-community/eza-themes) - eza 官方的颜色主题仓库。
- **演示：** [https://cn.x-cmd.com/1min/eza](https://cn.x-cmd.com/1min/eza)

![eza命令演示](https://static.lanyangyang.me/img/2025/12/382b503f5e3ae0b0b49b527b45fde725.png)

### duf ⭐️⭐️⭐️⭐️

`df` 命令的现代化替代品， 用于查看磁盘空间使用情况和磁盘文件系统信息。其直观的输出和多样化的自定义选项，帮助用户更好地管理和优化存储资源。

- **官网：** [https://cn.x-cmd.com/pkg/duf](https://cn.x-cmd.com/pkg/duf)
- **优势：** 更直观，更好看。
- **推荐配置：**

```bash
alias df="duf"
```

![duf命令演示](https://static.lanyangyang.me/img/2025/12/9b5fe4df9a92ccadf8e8c5aee2e2fa6e.png)

### dust ⭐️⭐️⭐️⭐️

`du` 命令的现代化替代品， 用于查看磁盘空间使用情况，提供实时的磁盘空间概览，并以直观的图形方式展示文件和目录的大小。

- **官网：** [https://github.com/bootandy/dust](https://github.com/bootandy/dust)
- **优势：** 更直观，更好看。
- **推荐配置：**

```bash
alias du="dust"
```

### tig ⭐️⭐️⭐️⭐️

> 可以图形化的查看 git 历史，操作更便捷。

`Tig` 是一个在 Linux 系统中用于查看 Git 仓库历史的命令行工具，它提供了一个交互式的界面来浏览 Git 的提交历史、分支、标签等信息。`Tig` 的名称来源于 "Tom's Interactive Git"，是由 Tom Preston-Werner 开发的一个项目。

- **官网：** [https://jonas.github.io/tig/](https://jonas.github.io/tig/)
- **优势：**
  - 通过解析 Git 仓库中的对象数据库，提供了一个简洁的界面来显示提交历史。
  - 支持多种视图，如日志视图、树视图、差异视图等，用户可以通过键盘快捷键进行导航和操作。
  - 键盘导航（`j`/`k` 上下移动，`q` 退出）
- **更多介绍：**
  - [📦 tig（1）: Git 可视化神器，让你的代码管理更轻松_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV11gpMemExU/?spm_id_from=333.337.search-card.all.click&vd_source=5d876fc94223e09ca29ed660ffc5224f)
  - [📦 tig(2): 带你体验 Git 的交互式提交代码流程_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV13g4DeWEsV?spm_id_from=333.788.videopod.sections&vd_source=5d876fc94223e09ca29ed660ffc5224f)
- **演示：** [https://cn.x-cmd.com/1min/tig](https://cn.x-cmd.com/1min/tig)

![tig命令演示](https://static.lanyangyang.me/img/2025/12/2ca30b02e78c23744298fe9afb67e068.png)

## 使用建议

- **原生命令优先：** 虽然推荐工具能提升效率，但建议先熟练掌握 `cd`、`ls`、`cat` 等原生命令，它们是终端操作的基础。
- **兼容性考虑：**不要在工作 shell 中使用

## 扩展资源

1. [推荐 20 个堪称神器的命令行工具-CSDN博客](https://blog.csdn.net/codingpy/article/details/103998398)
2. [Linux下你可能不知道的命令行如意金箍棒 - SunnyZhang的I世界](http://www.baidu.com/link?url=HW5TDPZkWbPaLdjye5-VFDn62kkHd98tY50TjqT88dP_y2e3fbKLCYOayBY9RaanOhjac8IHf5kUh9EdNngHAGykqiebBJ2heH_eaPhw7c_)
3. [X-cmd 工具合集](https://cn.x-cmd.com/)

**PS: 如果你有 `意见建议`、`其它命令行工具推荐`，请在评论区讨论，可能会被收集到文档中。**
