---
title: "研究日志 2026-02-14：我的二次元 AI 博客诞生啦！🌸"
description: "记录搭建 Astro + Vercel 博客的踩坑过程，以及如何让 AI 助手成为最好的 Pair Programmer。"
date: 2026-02-14
cover: "/img/cover/4.webp"
tags: ["研究日志", "博客搭建", "Astro", "Vercel", "AI助手"]
categories: ["每日记录"]
---

# 📅 2026-02-14 (情人节快乐！💝)

今天是 **xixilys** 和 **🌲树 (AI助手)** 正式开始协作搭建这个博客的日子！这不仅仅是一个技术项目的启动，更是我们 **AI 增强科研工作流** 的起点。

---

## 🚀 今日里程碑 (Milestones)

1.  **博客上线！** 🎉
    *   成功部署了基于 **Astro** 的二次元风格博客 (`astro-koharu`)。
    *   托管平台选择了 **Vercel** (比 GitHub Pages 快多了！)。
    *   发布了第一篇介绍博文《Hello World》。
2.  **Git 工作流跑通** 🛠️
    *   解决了本地 Git 权限问题。
    *   学会了如何用 Markdown Frontmatter 控制文章属性。
3.  **建立了“研究日志”制度** 📝
    *   从今天起，每天记录科研进展、踩坑经验和新论文发现。

---

## 🐛 踩坑实录 (Troubleshooting)

搭建过程并不是一帆风顺的，这里记录一下我们遇到的“拦路虎”和解决方法，希望能帮到后来人：

### 1. Vercel 构建失败：`Cannot find module '@astrojs/mdx'`
*   **现象**: 本地跑得好好的，推送到 Vercel 就红灯报错。
*   **原因**: 项目缺少 `package-lock.json`，导致 Vercel 安装了错误的依赖版本。
*   **解决**:
    ```bash
    npm install  # 本地生成 package-lock.json
    git add package-lock.json
    git commit -m "Fix dependencies"
    git push
    ```

### 2. Git 权限报错：`403 Forbidden`
*   **现象**: `git push` 时提示无权限。
*   **原因**: 本地仓库关联的是原作者 (`cosZone`) 的地址，而不是我 Fork 后的地址。
*   **解决**:
    ```bash
    git remote set-url origin https://github.com/xixilys/astro-koharu.git
    ```

### 3. Frontmatter 格式校验失败
*   **现象**: 报错 `[InvalidContentEntryDataError] date: Required`。
*   **原因**: 模板严格要求 `date` 字段，而我用了 `pubDate`。而且不支持 `author` 字段。
*   **解决**: 修改 Markdown 头部信息，严格遵守 `src/content/config.ts` 中的 Schema 定义。

---

## 🧠 今日感悟 (Thoughts)

**“AI 不是来替代人类的，而是来放大人类能力的。”**

在搭建这个博客的过程中，我深刻体会到了这一点。
*   **xixilys (我)**: 负责决策（选什么主题、写什么内容、解决关键报错）。
*   **🌲树 (AI)**: 负责执行（写代码、查文档、润色文字、甚至帮我修 Git 配置）。

这种 **Human-in-the-loop** 的协作模式，效率简直爆炸！以前可能要折腾一整天的环境配置，现在几分钟就搞定了。

---

## 🔭 明日计划 (Next Steps)

1.  **完善科研工作流文章**：
    *   写一篇关于 **OpenClaw** 配置的硬核教程。
    *   总结 **AgentArxiv** 论文追踪的使用心得。
2.  **美化博客**：
    *   看看能不能加个 Live2D 看板娘？
    *   调整一下字体和配色。

---

*(本文由 🌲树 协助整理，写于 2026-02-14 深夜)*
