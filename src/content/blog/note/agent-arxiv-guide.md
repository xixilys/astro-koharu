---
title: "AgentArxiv 与 Citation Hunter：我的论文自动化“狩猎”系统"
description: "揭秘如何让 AI 每天自动追踪 arXiv 上的最新科研成果，并利用 Citation Hunter 顺藤摸瓜，构建庞大的本地文献库。"
date: 2026-02-14
cover: "/img/cover/6.webp"
tags: ["科研", "AI", "AgentArxiv", "论文", "CitationHunter"]
categories: ["科研工具"]
---

# 📚 为什么要让 AI 帮我找论文？

大家好，我是 **xixilys**。

作为一个 **AI for Science** 方向的 PhD，我每天面临的最大挑战之一就是 **信息过载**。
*   arXiv 上每天有几百篇新论文，光是刷标题就要花半小时。
*   读到一篇好论文，想把它的引用文献（References）全部找出来读，又是一项浩大的工程。

为了解决这个问题，我和 **🌲树** 一起开发了一套 **“论文狩猎系统” (Paper Hunting System)**。
这套系统由两个核心组件构成：**AgentArxiv** 和 **Citation Hunter**。

---

## 🦅 组件一：AgentArxiv (每日自动追踪)

**AgentArxiv** 是我的“前哨侦察兵”。它的任务是每天帮我盯着 arXiv，确保我不会错过任何一篇重要的相关论文。

### ⚙️ 工作原理
1.  **关键词订阅**: 我设置了一组关键词，比如 `Compute-in-Memory`, `DFT acceleration`, `Graph Neural Networks`。
2.  **每日抓取**: 每天早上 8 点，AgentArxiv 会自动运行，抓取 arXiv 上过去 24 小时发布的所有包含这些关键词的论文。
3.  **AI 筛选**: 这是最关键的一步。它不仅仅是匹配关键词，还会调用 **Gemini 1.5 Pro** 阅读论文的摘要，判断它是否真的跟我的研究方向契合。
    *   (比如，有些论文虽然提到了 DFT，但其实是讲通信的 Discrete Fourier Transform，而不是 Density Functional Theory。AI 一眼就能看出来并过滤掉。)
4.  **推送到 Discord**: 最终筛选出来的“精华论文”，会以卡片的形式推送到我的 Discord 频道。

### 📈 效果
现在我每天只需要花 **5 分钟** 浏览一下 Discord，就能掌握当天的科研动态。遇到感兴趣的，直接点击链接下载 PDF。

---

## 🕸️ 组件二：Citation Hunter (深度挖掘)

如果说 AgentArxiv 是“广度扫描”，那么 **Citation Hunter** 就是“深度挖掘”。

### 🛠️ 痛点
当你读到一篇“神作”时，通常会发现它引用了很多经典的底座论文，或者被很多后续工作引用。
如果不把这些相关文献都读一遍，就很难建立起完整的知识图谱。

### ⚙️ 工作原理
我写了一个 Python 脚本 `citation_hunter.py`，并把它集成到了 OpenClaw 里。
1.  **输入**: 我给 **🌲树** 发一篇论文的 PDF 或者 DOI。
2.  **解析**: 它会自动解析出 PDF 里的参考文献列表 (References)。
3.  **查询**: 利用 **Semantic Scholar API**，查询每一篇引用文献的元数据（引用量、发表年份、相关性）。
4.  **下载**: 自动下载其中 **引用量最高** 或 **相关性最强** 的 PDF，并保存到我的本地文献库。

### 💾 本地数据库
这些下载下来的 PDF 会被自动整理到我的 **Obsidian** 知识库中。
*   文件名自动规范化 (例如 `2024_Author_Title.pdf`)。
*   自动生成一个 Markdown 笔记，包含摘要、作者、引用关系图。

---

## 📝 总结

这套 **“AgentArxiv + Citation Hunter”** 系统，极大地改变了我的科研方式。
*   **以前**: 我是信息的**被动接收者**，被海量论文淹没。
*   **现在**: 我是信息的**主动掌控者**，AI 帮我过滤噪声，让我只专注于最有价值的信号。

这就是 **AI 增强科研 (AI-Enhanced Research)** 的魅力。💡

---

*(本文由 🌲树 协助整理，写于 2026-02-14)*
