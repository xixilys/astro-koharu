---
title: "构建本地论文数据库：从 PDF 到 Obsidian 知识图谱"
description: "把 AI 帮你找到、读完的论文，整理成一套井井有条的本地知识库。Obsidian + Zotero 梦幻联动。"
date: 2026-02-14
cover: "/img/cover/8.webp"
tags: ["科研", "Obsidian", "Zotero", "知识管理", "AI"]
categories: ["科研工具"]
---

# 🧠 为什么需要本地数据库？

大家好，我是 **xixilys**。

在前几篇文章里，我介绍了 **OpenClaw** (大脑)、**AgentArxiv** (找论文) 和 **Gemini 3.0 Pro** (读论文)。
但如果这些知识仅仅是停留在 Discord 聊天记录里，或者是分散的 Markdown 文件，那它们很快就会被遗忘。

我们需要把它们变成 **属于自己的知识资产 (Knowledge Asset)**。

---

## 🛠️ 我的工具栈：Obsidian + Zotero

如果你还在用 Windows 自带的文件夹管理几千篇 PDF，或者只是简单地用 Mendeley 存个标题，那你真的亏大了。
我的方案是：**Zotero (管理文献元数据) + Obsidian (管理思考笔记)**。

### 1. Zotero：文献的“身份证”
*   **功能**: 自动抓取 PDF 的标题、作者、年份、DOI 等元数据。
*   **必装插件**:
    *   **Zotero File**: 自动重命名 PDF 文件 (`2024_Author_Title.pdf`)。
    *   **Better BibTeX**: 生成唯一的引文 Key (`@author2024title`)，方便在 Obsidian 里引用。

### 2. Obsidian：知识的“神经元”
*   **功能**: 双向链接笔记，把孤立的知识点连成网。
*   **核心插件**:
    *   **Citations**: 直接从 Zotero 导入文献信息。
    *   **Dataview**: 像写 SQL 一样查询笔记 ("列出所有关于 CIM 的论文")。

---

## 🤖 AI 增强：自动入库脚本

为了让这个过程全自动化，我和 **🌲树** 写了一个脚本 `import_to_obsidian.py`。

### ⚙️ 流程
1.  **AI 摘要入库**:
    *   当 Gemini 3.0 Pro 生成好一篇论文的摘要后，脚本会自动在 Obsidian 里创建一个对应的 Markdown 文件。
    *   文件名就是 Zotero 的 CiteKey (`@author2024title.md`)。
2.  **元数据填充 (Frontmatter)**:
    *   脚本会自动从 Zotero 读取元数据，填入 YAML Frontmatter。
    *   `tags`: `#CIM`, `#DFT`, `#AI4Science`
    *   `status`: `Reading` / `Done`
    *   `rating`: ⭐⭐⭐⭐⭐
3.  **双向链接**:
    *   脚本会根据关键词自动添加链接。比如摘要里提到了 `[[Transformer]]`，它就会自动链到我关于 Transformer 的概念笔记。

---

## 📈 效果：我的第二大脑

现在，我拥有了一个庞大的本地知识库。
*   **搜索**: 瞬间找到任何一篇我读过的论文。
*   **关联**: 看到这篇论文，就能顺藤摸瓜找到它引用的所有相关工作。
*   **复用**: 写论文的时候，直接把 Obsidian 里的笔记复制粘贴出来，甚至可以直接转换成 LaTeX 格式。

---

## 📝 总结

这套系统不仅仅是存文件，而是在 **构建外脑**。
*   **OpenClaw** 是大脑 CPU，负责处理信息。
*   **AgentArxiv** 是眼睛，负责获取信息。
*   **Obsidian** 是海马体，负责长期记忆。

拥有了这套系统，哪怕我不去刻意背诵，这些知识也会永远留在我身边，随时待命。💡

---

*(本文由 🌲树 协助整理，写于 2026-02-14)*
