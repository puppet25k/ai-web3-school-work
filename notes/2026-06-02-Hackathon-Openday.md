# Hackathon Openday：赛道解读 + 资源支持 + 提交指南

> **学习日期：** 2026-06-02
> **主办：** LXDAO / ETHPanda
> **合作方：** Z.ai / Cobo / Wallet / Dev Growth / Elytro / Web3Privacy / LI.FI
> **标签：** #Hackathon #Openday #Cobo #ZAI #AgenticEconomy #LongHorizon

---

## 一、活动概览

| 项目 | 时间 |
|------|------|
| Kickoff / 报名开放 | 6月1日 20:00 |
| **Openday** | **6月2日 20:00** |
| Build Period | 6月1日 - 6月12日 |
| Workshop / Office Hour | 周一 / 周三 / 周五 19:00 |
| Demo 提交截止 | 6月13日 12:00 (UTC+8) |
| Demo Day / 评选 | 6月13日 下午 |

---

## 二、两个赛道

### Track 1：Cobo — Agentic Economy x Cobo Agentic Wallet

**奖金：** 3500 USDT

**可选方向：**
- **Agent-Native Payments** — Agent 原生支付
- **Trustless Agent Work Agreements** — 去信任的 Agent 工作协议
- **Agent Resource Procurement** — Agent 资源采购
- **Autonomous Trading** — 自主交易
- **A2A Economy** — Agent-to-Agent 经济
- Others

**规则：**
- 项目必须围绕 **Agent 与资金操作场景**
- 要体现 **Agent 的真实资金执行能力**
- 不接受纯概念 / 纯 Mockup
- 资金相关操作需通过 **Cobo Agentic Wallet** 完成

> 有问题去 Cobo Discord 频道：https://discord.gg/hJ6wPunpQ

---

### Track 2：Z.AI — Web3 x Long-Horizon Task

**奖金：** 3500 USDT

**核心技术：** **GLM-5.1** 驱动的长程任务能力

**建议方向：**
- **Agentic Dev Tools for Web3** — Agent 开发工具
- **AI-Powered 3D World Builder** — AI 3D 世界构建
- **AI × Creator Economy** — AI 创作者经济
- Others

**核心理念：**
> 关注 GLM-5.1 的长程任务能力：让 Agent 不只是回答问题，而是能自主拆解复杂任务、制定多步骤计划、持续调用工具和迭代修复，并完成从需求到交付的完整 Web3 工作流。

参赛项目应体现**长程、自主、持续执行**，而不是只做一次性生成或普通 API 调用。

---

## 三、评分体系

| 维度 | 满分 | 说明 |
|------|:----:|------|
| **Innovation 创新性** | 10 | 是否提出新的机制、流程、应用方式 |
| **Technical Execution 技术实现** | 10 | 核心功能是否可运行，架构是否清晰 |
| **User Experience 用户体验** | 10 | 产品体验是否完整，用户路径是否清楚 |
| **Ecosystem Impact 生态影响** | 10 | 后续发展潜力，能否为生态带来价值 |
| **Demo Quality 演示质量** | 10 | 现场演示稳定、清晰、有说服力 |

**总分满分 50 分，取所有评委评分的平均值。**

赛道优胜项目由项目方与评委结合赛道匹配度、项目完成度和后续潜力共同确认。

---

## 四、资源支持

### Z.AI API 报销支持
- **方案：** Lite Plan（$18 USD/月），赛后实报实销
- 参赛者需先自行购买，赛后根据 Demo 完成度、获奖情况、赛道匹配度审核
- 补贴名额有限，提交申请不代表一定获得报销
- 折扣链接（10% off）：https://z.ai/subscribe?ic=8JVLJQFSKB

### 社群支持
- **Telegram 社群：** t.me/aiweb3school
- **微信中文社群：** 添加 Lynn2024，备注 "AI x Web3 Agentic Builders Hackathon"

---

## 五、参与流程

```
01  报名并加入社群
02  选择赛道 / 发布项目方向或组队需求
03  开始 Build，参加 Workshop / Office Hour
04  6月13日 12:00前提交
05  Demo Day 展示
```

### 提交方式
通过 GitHub Issues 提交：
- 项目名称
- 赛道
- 项目描述
- GitHub Repo 链接（必须开源）
- 团队负责人和钱包地址

**示例提交：** 0xScribe — "链上判官" （基于 Spoons 的 AI 链上行为分析工具）

---

## 六、技术方案参考

### Cobo 赛道方向示例

| 方向 | 核心思路 | 技术要点 |
|------|----------|----------|
| **Agent-Native Payments** | Agent 自主发起/接收链上支付 | CAW Skills 接入 → Pact 定义支付策略 → 自动执行 |
| **Trustless Agent Work Agreements** | 智能合约锁定资金，Agent 完成任务后释放 | 合约条件 + CAW 签名 + 链上验证 |
| **Agent Resource Procurement** | Agent 自主采购链上资源（Gas/存储/算力） | CAW 多链支持 + Pact 预算限制 |
| **Autonomous Trading** | Agent 自主执行 DeFi 交易策略 | Uniswap V3 Swap Recipe + 频率/金额策略限制 |
| **A2A Economy** | Agent 之间直接结算服务费/分成 | 多重 Pact + 链上对账 |

### Z.AI 赛道方向示例

| 方向 | 核心思路 | GLM-5.1 能力利用 |
|------|----------|------------------|
| **Agentic Dev Tools for Web3** | Agent 自主分析合约、生成部署脚本 | 长程任务拆解 + 多步执行 + 错误自愈 |
| **AI-Powered 3D World Builder** | 自然语言描述 → 3D 场景/资产生成 | 多步推理 + 工具链编排 |
| **AI × Creator Economy** | Agent 辅助 NFT/内容创作全流程 | 需求→生成→发布 完整工作流 |

### 示例提交参考

**0xScribe — "链上判官"**
- 基于 Spoons 的 AI 链上行为分析工具
- 自动检测异常交易、恶意合约、钓鱼地址
- 输出风险评级报告

### 技术方案通用检查清单

```
□ 是否使用了对应赛道的核心基础设施？（CAW / GLM-5.1）
□ 是否体现了 Agent 的自主执行能力，而非纯概念/Mockup？
□ 是否有清晰的价值闭环？（谁用、解决什么、怎么赚钱）
□ Pact 策略是否合理？（Cobo 赛道必备）
□ 项目是否开源？
□ 是否准备好 5 分钟 Demo 演示？
```

---

## 七、Hackathon 实用信息

### 日程结构

| 日期 | 活动 | 时间 |
|------|------|------|
| 周一 | Co-Learning / 任务推进 | 19:00 |
| 周三 | Workshop | 19:00 |
| 周五 | Office Hour | 19:00 |

### 关键提醒
- **Cobo Discord 答疑：** https://discord.gg/hJ6wPunpQ
- Z.AI 赛道参赛者可尝试 **GLM-5.1**（MIT 开源权重，低成本）
- 提交需在 **6月13日中午12:00前** 完成
- 项目**必须开源**
