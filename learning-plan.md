---
timezone: UTC+8
created: 2026-05-20
---

# 学习计划

> 根据 Handbook 结构和学员画像定制。每日学习路径分三个层级：
> - 🌱 **最小路径** — 再忙也做完
> - 🌿 **推荐路径** — 正常节奏
> - 🌳 **挑战路径** — 有余力时深入

---

## 阶段一：补齐 Web3 基础（Week 1-2）

> Web3 新手：先建立对网络、钱包、合约的基本直觉。

| 日期 | 主题 | 最小 | 推荐 | 挑战 |
|------|------|------|------|------|
| 5/20 | 网络（Network） | 读 Handbook → Network | + 搭 RPC 节点 | 分析 Etherscan 区块 |
| 5/21 | 密码学（Cryptography） | 读 Handbook → Cryptography | + 用 ethers.js 签名 | 写签名/验签脚本 |
| 5/22 | 钱包（Wallet） | 读 Handbook → Wallet | + 创建测试钱包 | 做一笔测试交易 |
| 5/23 | 智能合约（Smart Contract） | 读 Handbook → Smart Contract | + 用 Remix 部署 | 写一个简单合约 |
| 5/24 | Account Abstraction | 读 Handbook → AA | + 对比 EOA vs CA | + 了解 ERC-4337 |
| 5/25 | 复习 + 实践 | 整理笔记到 repo | + 完成模块 B 任务 | 画知识图谱 |

## 阶段二：AI 基础深化（并行）

> AI 已有基础，重点补全未知的模块。

| 主题 | 状态 | 计划 |
|------|------|------|
| LLM / Prompt / Context | ✅ 已了解 | 略读 Handbook 确认 |
| RAG | 🔜 待读 | Handbook + 实验 |
| Agent | ✅ 已参加分享会 | 继续动手实践 |
| Frameworks | 🔜 待探索 | LangChain / LangGraph 对比 |
| MCP | 🔜 待读 | Handbook + 实践 |
| Evaluation / Fine-tuning / Inference | 📌 后续探索 | Week 3-4 |

## 阶段三：AI × Web3 Bridge（Week 3-4）

> 进入交叉区域，以原型驱动。

1. **Chain-aware Context** — Agent 如何读取链上状态
2. **Web3 Tool Use** — Agent 调用合约/RPC/钱包工具
3. **Agent Workflow** — 自动化 vs Human-in-the-loop
4. **Agent Wallet** — Session Key、权限隔离
5. **Machine Payment** — 小额支付结算
6. **Verifiable AI** — 可验证输出

## 阶段四：项目实践（Week 4+）

> 选择一个前沿赛道做可展示原型。

候选方向：
- Agent 自动支付 / 结算原型
- 钱包权限管理工具
- AI + 链上数据分析
- Hackathon 项目

## 每周产出

| 周次 | 产出 |
|------|------|
| Week 1 | Web3 基础笔记 + 测试钱包/交易 |
| Week 2 | 最小合约 + RAG 实验 |
| Week 3 | Bridge 概念笔记 + 工具调用原型 |
| Week 4 | 项目原型 |
