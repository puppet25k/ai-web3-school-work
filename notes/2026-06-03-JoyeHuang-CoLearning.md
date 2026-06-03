# Joye Huang: Agent Engineer 成长路径与 Co-Learning 分享

**日期：** 2026-06-03
**分享人：** Joye Huang（黄得守）
**来源：** Co-Learning 分享会

---

## 分享人背景

- **身份：** 墨尔本大学本科（Computing & Software Systems），大三
- **公司：** Tezign（特赞）上海，AIGC R&D 团队，构建 atypica.ai 多智能体商业调研系统
- **同时参与：** fAIshion.ai（AI 虚拟试穿）、Goshu Tech（AI 视频编辑）
- **所在地：** 墨尔本 / 上海
- **X/Twitter：** @deshiou0604
- **LinkedIn：** deshiouhuang

## 开源贡献

| 项目 | 说明 | Stars |
|------|------|:-----:|
| **minimind-notes** | 从零构建 LLM 的极简教程——Transformer、Pretraining、SFT 核心代码与对照实验 | ⭐122 |
| **Learn-Open-Harness** | OpenHarness 零基础交互式教程——Agent Loop、Tools、Memory、Multi-Agent | ⭐9 |
| **joyehuang.me** | 个人博客，Astro 构建，12 篇高质量 Agent 技术文章 | - |

## 核心分享内容

### 1. Agent 工程入行路径

Joye 在找 Agent 岗位实习时，面试了近 10 家 AI 初创，总结出：

- **面试不是考试，是双向选择**——面试官更看重你如何思考问题，而非背诵答案
- **尽早投递**，通过实战校准自身定位
- **录下面试回放**复盘，持续改进
- **主动提问**，把创始人/面试官视为平等对话方
- Agent 岗面试核心考察：**个人项目深度 > 八股文背诵**

### 2. 技术栈能力图谱

**前端：** TypeScript, React, Next.js, Tailwind, Remotion
**后端：** Node.js, Vercel, Supabase, AWS, Stripe, Inngest
**AI & Agent：** Claude Code, LLM, Transformer, Multi-Agent, RAG, Function Calling, Prompt Engineering
**工具：** Cursor, Git, Docker, Bun, Figma

### 3. OpenHarness 理解（Agent 框架）

OpenHarness 是 HKUDS 开源的第一套 Agent Harness 模式实现（类似 Claude Code）。Joye 在其发布第二天就写出了 12 章交互式教程。

**核心概念：**
```
Harness = Tools + Knowledge + Observation + Action + Permissions
```

- **Phase A（基础）**：什么是 AI Agent → 什么是 Harness → Harness 公式
- **Phase B（核心机制）**：Agent Loop（思考→行动→观察循环）、43+ 内置工具的统一接口、三级权限系统、Hook 生命周期
- **Phase C（智能层）**：Skills（按需知识加载）、Memory（跨会话持久化）、MCP 集成（标准化外部连接）
- **Phase D（进阶）**：多智能体协作、完整流程

### 4. Hermes Agent 记忆系统分析

Joye 深入研究了 Hermes Agent 的四层记忆架构，写了长文分析：

- **L0**：工作上下文（系统提示词 + 注入记忆块，限会话内）
- **L1**：持久化记忆（memory 工具 + 文件级存储）
- **L1.5**：外部记忆插件（honcho/mem0/supermemory）
- **L2**：会话搜索（SQLite FTS5 + LLM 摘要，跨会话按需检索）
- 核心哲学：不依赖向量数据库，分层解耦

### 5. Transformer 底层理解

minimind-notes 从零构建 LLM，覆盖：
- **Attention 机制**：QKV 的数据库查询类比，Multi-Head，Softmax vs RMSNorm
- **FeedForward 网络**：SwiGLU 激活函数
- **完整 Transformer Block**：RMSNorm + RoPE + Attention + FeedForward 组装

## 学习收获

1. Agent 工程入行更看重**动手能力和项目深度**，建议从写一个简单的 Agent Harness 或参与开源 Agent 项目开始
2. OpenHarness 是理解当前 Coding Agent（Claude Code / Cursor）架构的最佳入口
3. 记忆系统是 Agent 的关键差异化能力，不依赖复杂基础设施也能实现有效记忆（如 Hermes 的 FTS5 方案）
4. 做开源 + 写博客是建立 Agent 领域影响力的有效路径
