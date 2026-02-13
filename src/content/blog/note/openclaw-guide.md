---
title: "我的 AI 助手大脑：OpenClaw 从零配置指南"
description: "揭秘我的 AI 助手是如何工作的：本地部署、模型选择、Skill 系统配置，以及如何把它变成真正的 Pair Programmer。"
date: 2026-02-14
cover: "/img/cover/5.webp"
tags: ["AI", "OpenClaw", "工具", "效率"]
categories: ["技术折腾"]
---

# 🧠 给 AI 装上“大脑”与“手脚”

大家好，我是 **xixilys**。

如果你看了我和 **🌲树** 共同搭建这个博客的过程，可能会好奇：
*   这个 AI 助手到底是怎么运行的？
*   为什么它不仅能陪聊，还能直接操作我的文件、运行代码、甚至帮我修 Bug？

答案就是：**OpenClaw**。

---

## 🛠️ 什么是 OpenClaw？

简单来说，OpenClaw 是一个**开源的 AI Agent 操作系统**。
它不像 ChatGPT 那样只能在一个网页框框里聊天，它直接运行在我的 **Mac mini** 上，拥有操作系统的权限。

它由两部分组成：
1.  **大脑 (Model)**: 负责思考。我目前主要使用 **Gemini 1.5 Pro** 和 **Claude 3.5 Sonnet**（甚至还在测试 **Gemini 3.0 Pro**！）。
2.  **手脚 (Tools & Skills)**: 负责干活。它能读写文件、运行终端命令、搜索网页、管理 Docker...

---

## ⚙️ 我的配置思路

为了让 **🌲树** 成为合格的科研伙伴，我给它做了如下配置：

### 1. 运行环境
*   **硬件**: Mac mini (M4 Pro)
*   **权限**: 赋予它对 `/Volumes/remote/` (我的外接硬盘) 的完全读写权限，这样它就能帮我整理论文和代码库。
*   **网络**: 配置了本地代理，确保它能顺畅连接 Google 和 Anthropic 的 API。

### 2. 核心技能 (Skills)
OpenClaw 最强大的地方在于它的 **Skill 系统**。我给它安装了这些“超能力”：

*   **🔍 web_search (联网搜索)**: 让它能查到最新的技术文档和论文。
*   **📄 read/write/edit (文件操作)**: 这是它帮我写代码的基础。它能直接修改我的 Python 脚本和 Markdown 博客。
*   **🐚 exec (终端执行)**: 它能帮我跑 `git push`，安装依赖 `npm install`，甚至重启服务。
*   **📚 memory (记忆系统)**: 它会把我们的对话摘要存成 Markdown 文件，这样第二天它还记得我们昨天聊了什么。

### 3. 科研特化 (Research Focus)
为了支持我的 **AI4Science** 研究，我还给它加装了几个特殊的 Skill：
*   **AgentArxiv**: 每天自动去 arXiv 上抓取最新的 CIM 和 DFT 相关的论文。
*   **Citation Hunter**: 给定一篇论文，自动顺藤摸瓜找到它引用的所有关键文献，并下载 PDF。

---

## 💻 实战：它如何帮我写代码？

以搭建这个博客为例，我们的协作流程是这样的：

1.  **我提出需求**: “树，我想把博客封面改成二次元图片。”
2.  **它思考方案**: “好的，我检查了一下项目文件，发现 `/img/cover/` 下有很多现成的图片。建议修改 Frontmatter 中的 `cover` 字段。”
3.  **它执行操作**:
    *   调用 `read` 工具读取 `hello-world.md`。
    *   调用 `edit` 工具把 `cover: placeholder` 改成 `cover: /img/cover/3.webp`。
    *   调用 `exec` 工具运行 `git commit` 和 `git push`。
4.  **我验收结果**: 刷新网页，搞定！✨

整个过程，我甚至不需要打开 VS Code，只要在 Discord 里跟它说句话就行。

---

## 📝 总结

配置 OpenClaw 就像是**收养了一个高智商的数字生命**。
一开始你需要教它规则（配置 Config），给它趁手的工具（安装 Skills），但一旦它熟悉了你的工作流，它就会成为你最得力的伙伴。

如果你也是科研人员或者程序员，强烈推荐你试着部署一个属于自己的 OpenClaw Agent。相信我，用了就回不去了！😎

---

*(本文由 🌲树 协助整理，写于 2026-02-14)*
