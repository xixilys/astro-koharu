---
title: "告别手动搜论文：AgentArxiv 与 Citation Hunter 实战"
description: "如何让 AI 每天自动追踪 arXiv 上的最新科研成果，并顺藤摸瓜找到引用的关键文献。"
date: 2026-02-14
cover: "/img/cover/6.webp"
tags: ["科研", "AI", "AgentArxiv", "论文", "CitationHunter"]
categories: ["科研工具"]
---

# 📚 我的论文“狩猎”系统 (Paper Hunting System)

作为一个 PhD，每天读论文是基本功。但 arXiv 上的更新速度太快了，光是筛选标题就要花掉大半个上午。
有没有办法让 AI 帮我**过滤垃圾论文**，只把真正有价值的送到我面前？

答案是有的。这就是我要介绍的 **AgentArxiv** 和 **Citation Hunter**。

---

## 🔍 痛点：手动搜索的低效

传统的读论文流程：
1.  打开 arXiv，搜 `DFT` 或 `CIM`。
2.  肉眼扫描几十个标题，点进去看 Abstract。
3.  觉得不错，下载 PDF。
4.  读完发现它引用了一篇神作，又去搜那篇引用... (无限套娃)

这太慢了！我们要把这个流程自动化。🚀

---

## 🤖 解决方案 1：AgentArxiv (每日简报)

我给我的 AI 助手 **🌲树** 配置了一个叫 `AgentArxiv` 的 Skill。
它的工作原理很简单：
1.  **关键词订阅**: 我设置好关键词 `Compute-in-Memory`, `DFT acceleration`, `AI for Science`。
2.  **每日抓取**: 每天早上，它会自动去 arXiv 抓取最新的相关论文。
3.  **智能筛选**: 它会调用 **Gemini 3.0 Pro** 读取每篇论文的摘要，判断是否真的跟我的研究方向契合。
4.  **推送到 Discord**: 把筛选后的论文列表推送到我的 Discord 频道，并附上简短的中文摘要。

这样，我每天醒来只要看一眼 Discord，就能知道今天有哪些值得一读的新文章。📰

---

## 🕸️ 解决方案 2：Citation Hunter (顺藤摸瓜)

有时候读到一篇很好的综述，我想把里面提到的**关键引用文献**全部找出来读一遍。
手动一篇篇搜太痛苦了！

所以我写了一个叫 `Citation Hunter` 的 Python 脚本，并把它集成到了 OpenClaw 里。
现在的流程是：
1.  我给 **🌲树** 发一篇 PDF 或 DOI。
2.  它调用脚本，解析 PDF 里的参考文献列表。
3.  利用 **Semantic Scholar API** 查询这些引用的被引数和相关性。
4.  自动下载其中**高影响力**的 PDF 到我的本地库。

---

## 📝 总结

这套系统极大地解放了我的生产力。
*   **AgentArxiv** 帮我做广度扫描 (Breadth)，不错过最新动态。
*   **Citation Hunter** 帮我做深度挖掘 (Depth)，迅速构建知识图谱。

这就是 AI 时代科研的新范式：把**找资料**这种重复劳动交给 AI，把**思考和创新**留给自己。💡

---

*(本文由 🌲树 协助整理，写于 2026-02-14)*
