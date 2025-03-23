# README

## 开始写博客

### 0. 工具准备

1. 命令行终端，推荐 Warp
2. 编辑器，推荐 VSCode
3. Git
4. 其他命令行工具： HomeBrew, Go, Hugo

### 1. Clone 本仓库到本地

```shell
git clone https://github.com/hutusa/hutusa.github.io.git
```

### 2. 创建一篇博客

进入本地目录：

```shell
cd hutusa.github.io
```

执行命令创建一篇新博客：

```shell
hugo new content posts/2025-03-23-first-post.md 
```

该命令表示将在 content 目录下的 posts 子文件夹中建立一个名为 `2025-03-23-first-post.md` 的文本文件，`2025-03-23`是日期，可以修改为当前日期，`first-post`是博客的名称，将用来做博客的url.

### 3. 编辑博客

使用 vscode 打开博客工程：

```shell
code .
```

打开 `content/posts` 下的博客文件，编辑博客写作。可以修改头部的meta 内容，或保留：

```
---
date: '2025-03-23T09:22:19+08:00'
author: ["Lisa Zhong"]
title: First Post
slug: first-post
summary: "Sample article."
tags: ["blog", "podcast"]
categories: ["blog"]
---
```


在 --- 下方另起一行写博客内容即可，博客文本采用 Markdown 格式。

### 4. 在本地调试博客

在本地命令行终端上执行：

```shell
hugo server -D
```

如果有报错，需要根据报错信息fix bug. 如果没有报错，最后会出现如下字样：

```shell
Built in 35 ms
Environment: "development"
Serving pages from disk
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1) 
Press Ctrl+C to stop
```

这个时候根据提示打开浏览器，输入 `http://localhost:1313/` 或 `http://127.0.0.1:1313/` 即可查看博客的效果，可以根据浏览器的效果来修改博客，直到满意。

终止调式按 `Ctrl` + 'c' 键即可。

### 5. 提交博客

编辑好后，在本地执行 Git 查看文件修改状态：

```shell
git status
```

可以看到有一个新增文件。将文件添加到Git 缓冲区：

```shell
git add .
```

然后提交到本地的Git 库历史，`add new post` 是这次提交的记录消息，用于追溯，可修改，表示这次新增或改了哪些东西。

```shell
git commit -m"add new post"
```

然后提交到 GitHub 上：

```shell
git push origin main
```

其中 origin 表示GitHub 上的仓库，main 表示当前工作的分支。

提交完之后，等待 GitHub Actions 的结果。在 `https://github.com/hutusa/hutusa.github.io/actions` 查看最新一次的 action 执行情况，如果有报错，点击进去查看原因并 fix bug. 如果执行成功，打开 `https://distil.ca/` 即可查看最新的博客。
