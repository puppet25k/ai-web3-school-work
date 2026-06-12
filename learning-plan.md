---
timezone: UTC+8
created: 2026-05-20
updated: 2026-06-11
---

# 学习计划

> 专注 AI 方向，Web3 仅作概念了解。Handbook AI 篇已全部完成 ✅

---

## 已完成：Handbook AI 篇（6/6 - 6/10）

| 日期 | 模块 | 状态 |
|------|------|:----:|
| 6/6 | Prompt / Context / RAG | ✅ |
| 6/7 | Agent / Frameworks / Vibe Coding | ✅ |
| 6/8 | MCP | ✅ |
| 6/9 | Evaluation | ✅ |
| 6/10 | Fine-tuning | ✅ |

## 已完成：共学营分享会

共学营已收官，累计产出 15+ 篇分享会笔记，覆盖 Agent 成长路径、CAW 钱包、FluxA 支付、Conflux 开发、Z.AI Workshop 等主题。

---

## 当前阶段：AI 深化实践

### 🌱 最小路径 — 每日 30 分钟
- 读一篇感兴趣的 AI 技术文章/论文摘要
- 整理一条知识点到 workspace-docs 知识库
- 可选：把学到的概念用自己的话写一段理解

### 🌿 推荐路径 — 每日 1-2 小时
- **Agent 动手实验：** 在本地跑 Hermes Agent / OpenClaw，尝试接入一个真实工具（如搜索、文件读写）
- **RAG 搭建：** 用本地文档建一个小型 RAG 系统，体验 Chunking → Retriever → Rerank → Citation 全流程
- **MCP 探索：** 搭一个只读 MCP Server，暴露 search_docs / get_file 两个工具
- **Prompt 工程：** 针对选定的任务写多版本 prompt，用 Eval 对比效果

### 🌳 挑战路径 — 有余力时
- 实现一个完整的 Agent 工作流：Task → Plan → Tool Call → Validate → Deliver
- 研究 open-source Agent 框架源码（OpenHarness / LangGraph）
- 跑一个 Fine-tuning 实验（LoRA on 开源模型）

---

## 可选探索方向（按兴趣选）

| 方向 | 说明 | 动手建议 |
|------|------|----------|
| **Prompt Engineering 深入** | Structured Output、Few-shot 策略、Prompt Injection 防御 | 写一个"交易风险摘要"prompt，用 Eval 测稳定性 |
| **RAG 实践** | Chunking 策略对比、Retriever 选型、Rerank 效果 | 用本地文档库搭建，对比纯向量 vs 混合检索 |
| **Agent 框架对比** | LangChain / LangGraph / OpenAI SDK / Hermes | 同一个任务用不同框架实现，对比可读性/可维护性 |
| **MCP Server 开发** | 工具协议标准化 | 写一个只读 MCP Server + 一个写入型（需权限确认） |
| **Vibe Coding 实践** | Claude Code / Codex CLI 接入本地项目 | 完成一个最小工程闭环：任务→patch→test→review |
| **Fine-tuning 实验** | LoRA / PEFT 微调开源模型 | 准备 50 条样本，对比 prompt vs few-shot vs SFT 效果 |
| **Eval 体系搭建** | Golden Set + LLM-as-Judge + Regression | 为你的 Agent/RAG 系统建立可重复运行的评测 |

---

## 每日打卡推荐格式

```
## 今日学习 - [主题]
- 做了什么 / 读了什么
- 学到了什么（用自己的话总结）
- 下一步打算

## 随堂笔记
> 一句最想记住的话
```

**打卡原则：**
- 每天至少一条，哪怕是"今天只看了 15 分钟"
- 用**自己的话**总结，而不是抄原文——能说清楚 = 真懂了
- Q 的知识库（workspace-docs）和每日打卡（puppet25k.md）保持同步

---

## Web3 基础（轻量参考）

> 仅做概念了解，不做深入学习。

| 主题 | 状态 | 说明 |
|------|:----:|------|
| Network / 区块链基础 | ✅ 已有概念 | 不再深入 |
| Cryptography | ✅ 已有概念 | 不再深入 |
| Wallet | ✅ 已有概念 | 不再深入 |
| Smart Contract | ✅ 已有概念 | 不再深入 |
| Account Abstraction | ⏸️ 暂停 | 不感兴趣，暂停 |

---

## 知识库体系（workspace-docs）

`04-knowledge/工科/计算机/AI/` — 已 8 篇 ✅

```
Prompt-Engineering
Context-Engineering
RAG
Agent
Frameworks
Vibe-Coding
MCP
Evaluation
Fine-Tuning  ← 新增
```

**下一步：** 实践过程中产生的实验笔记、框架对比、最佳实践，持续补充进对应文档。
