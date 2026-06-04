# Harness Engineering for Financial Intelligence — FluxA 分享

**日期：** 2026-06-04（周四）
**分享人：** Skyl（Sky），FluxA
**来源：** Co-Learning 分享会

---

## 一、分享会概述

Skyl 分享了 FluxA 构建的 AI 原生支付基础设施——让 AI Agent 能够自主、安全、即时地收发资金，同时通过 Financial Harness（金融马具）框架解决 Agent 资金操作中的安全与信任问题。已与百度智能云达成合作。

---

## 二、核心问题：Agent 需要钱包

### 从聊天到 Agent 的演进

```
"What can I do for you?"    →  Chatbot（被动响应）
"What can I help with?"     →  Assistant（辅助执行）
"Can they do more?"         →  Agent（自主行动）
```

Agent 的自主性天然延伸到资金操作：**支付、结算、订阅、打赏**——但现有金融基础设施并未为 AI Agent 设计。

### Harness Engineering 的定位

> Harness engineering encompasses both and goes further. It is a foundational environment where:
> - Agents get the context they need by default
> - Without needing humans' constant supervision every time it executes
> - The effort is migrated from user's repeated labor into the agent system

即：把**重复的人类监督劳动转移到 Agent 系统内部**，让 Agent 在正确轨道上自主运行。

---

## 三、Financial Harness：金融马具

### Intent-based Constraints（基于意图的约束）

**核心思想：** 让 Agent 理解意图，而非仅仅执行指令。

> **Intent** = user-authorized task or goal that every downstream transaction must adhere to.
> The authorization object is the task itself, not any individual payment.

意即：用户授权的是**任务本身**，而非逐笔支付。Agent 在任务目标的范围内自主决策资金操作。

### Spending Validation：缺失的反馈闭环

#### 编程中的反馈闭环
```
Write Code → Build → Test → Catch Error → Feed Back → Fix
```
Agent 迭代直到代码通过审查。

#### 金融中的困境
金融领域的"错误"可能已经**结算完成**——一笔电汇无法撤回。因此 Financial Harness 需要在**结算前**进行验证。

#### 规则过滤（第一道防线）

Fast, deterministic, low cost：

- 🚫 **黑名单类目**：礼品卡、赌博等
- 🚫 **明显偏离授权范围**的操作
- 🚫 **重复相同交易**（暗示循环或浪费）

#### Spending Validation Loop 流程
```
Agent Intent → Rule-based Filtering → Review / Execute → Settle
                                              ↑
                                       (结算前验证)
```

---

## 四、FluxA：AI 原生支付基础设施

> FluxA is AI-native payment infrastructure that gives AI agents the ability to autonomously, securely, and instantly send and receive money across the internet — without exposing human users to financial risk.

**定位：** Agent 经济的金融引擎（"The financial engine of the agent economy"）

### 四大场景

| 场景 | 说明 | 示例 |
|------|------|------|
| **Agent-to-Agent** | Agent 之间为任务/数据/协作结算 | AI 写作 Agent 向搜索 Agent 支付数据费 |
| **Agent-to-Merchant** | Agent 自主预订/订阅服务 | 航班、酒店、SaaS 订阅 |
| **Agent-to-Tool** | 按次付费 API/MCP 工具调用 | 无需订阅，即用即付 |
| **Transfers & Tipping** | 红包/打赏批量分发 | Agent 社交场景 |

**核心理念：** AI agents as first-class economic citizens（AI Agent 作为第一类经济公民）

### 团队背景

由前阿里巴巴和蚂蚁集团高管创立。

---

## 五、与百度智能云的合作

### A DAO（Daily Active Agents）经济合作

**三方闭环管道：**

```
                    Baidu Marketplace
                          │
                    Asset Issuance
                          │
                          ▼
FluxA Global Distribution ← ─ ─ → A2A Payments
       │                          │
       ▼                          ▼
    Trading → Automated Settlement → Cross-border
```

1. **解锁 DAO（Daily Active Agents）经济** — Agent 自主交易、结算、作为经济参与者
2. **完整闭环管道** — 百度商品市场 + FluxA 全球分发 & A2A 支付 = 资产发行→交易→自动结算→跨境
3. **规模与全球化** — 90K+ Agent 在 FluxA 钱包上，10K+ 资源已货币化，即时访问 AI 原生跨境支付轨

---

## 学习收获

1. **Financial Harness 是 Agent 经济的关键基础设施** — 让 Agent 在意图范围内自主操作资金，同时通过结算前验证防止灾难
2. **意图级授权 vs 逐笔授权** — 前者让 Agent 真正自主，后者等于没有 Agent
3. **FluxA 的定位清晰** — AI 原生支付轨，不做通用支付，专为 Agent 场景设计
4. **与百度合作**说明中国大厂也在布局 Agent 经济的基础设施层
