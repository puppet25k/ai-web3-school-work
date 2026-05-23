---
timezone: UTC+8
---

# puppet25k

**GitHub ID:** puppet25k
**Telegram:**

## Self-introduction

AI x Web3 School

## Notes

<!-- Content_START -->

# 2026-05-19

<!-- DAILY_CHECKIN_2026-05-19_START -->

### 目前的状态

1. 成功将 Hermes Agent 和 OpenClaw 从本地 WSL 迁移到云服务器，实现远程访问
2. 完成了 Hermes 与飞书的连接配置
3. 配置了 AI x Web3 School 共学营日历的每日简报和课前提醒

### 今日内容

1. 将 Hermes Agent 从 WSL 迁移到腾讯云 Ubuntu 24.04 服务器
2. 安装并配置 mihomo 代理，使用精靈學院节点解决 Google Calendar 访问问题
3. 通过 ghproxy.net GitHub 镜像源下载所需依赖
4. 完成飞书日历订阅与课前提醒定时任务配置（每日8:00简报 + 每30分钟课前提醒）
5. 清理了 config.yaml 中残留的 Ollama 本地配置
6. 增补今日学习笔记并初始化 Git 仓库

### 下一步工作

1. 继续学习 AI x Web3 School 指导文档内容
2. 深入学习 AI 和 Web3 基础知识
3. 完善 Hermes Agent 的自动化和工具配置
4. 尝试完成飞书日历同步功能（需开放平台加 calendar 权限）

<!-- DAILY_CHECKIN_2026-05-19_END -->

# 2026-05-20

<!-- DAILY_CHECKIN_2026-05-20_START -->

### 目前的状态

1. 成功将 Hermes Agent 和 OpenClaw 部署在云服务器并稳定运行
2. 已完成飞书连接和日历定时提醒配置
3. 正在参与 AI x Web3 School 共学营，跟进课程内容

### 今日内容

1. 参加了 "AI Agent 入门 — Hermes 从 0 到 1" 分享会（Draken/Rico）
2. 学习了 AI 工具生态五大阵营：聊天型AI、AI编程助手、终端型AI、模型提供商、Agent框架
3. 理解了聊天机器人 vs AI Agent 的本质区别（回答 vs 做事）
4. 掌握了 AI Agent 核心运行机制：理解目标 → 调用工具 → 检查结果 → 修正执行
5. 整理了分享会笔记并提交至 GitHub
6. 参加了 "Web3 运行原理" 分享会（Bruce / @brucexu_eth）
7. 学习了交易到出块的完整链路：Wallet → RPC → Mempool → Builder → Validator → Block
8. 理解了 PoW vs PoS 的区别，以及 Ethereum PoS 的 Finality 机制（约 12.8 分钟）
9. 掌握了智能合约的本质（链上代码 + EVM 执行）和代理合约升级模式
10. 了解了以太坊升级流程：EIP 讨论 → 多客户端实现 → 测试网 → Hard Fork
11. 理解了 Web3 密码学 + 经济学 + 社会学的三角框架

### 随堂笔记

> **超过 12 分钟就非常安全了** — 指 Ethereum PoS finality，约 2 epochs

### 下一步工作

1. 继续学习 AI x Web3 School 指导文档内容
2. 深入学习 AI 和 Web3 基础知识
3. 学习如何进行资产自托管和管理私钥
4. 完善 Hermes Agent 的自动化和工具配置
5. 完成飞书日历同步（需开放平台加 calendar 权限）
6. 了解 MCP、RAG 等进阶概念
7. 了解 Ethereum 生态的更多应用场景
8. 参与后续共学营课程

<!-- DAILY_CHECKIN_2026-05-20_END -->

# 2026-05-21

<!-- DAILY_CHECKIN_2026-05-21_START -->

### 今日内容

1. 参加了 "AI 下乡计划｜在 Web3 的应用" 分享会（ELON）
2. 理解了 AI + Web3 的核心框架：AI 负责理解与决策，Web3 负责身份、支付、结算和审计
3. 了解了去中心化 AI 基础设施生态：Bittensor (TAO)、Render Network、Akash
4. 学习了 Coinbase AgentKit / MoonPay Agents / Privy Agentic Wallets 等 Agent 钱包方案
5. 了解了 AI 链上分析工具（Nansen）—— 从"写查询"变成"提问题"
6. 核心认知：AI + Web3 的价值不是给 AI 套 token，而是让软件主体进入可授权、可结算、可审计的经济系统

### 随堂笔记

> AI Agent 一旦开始做事，就会引出账户、支付、授权和追责问题
> 每个项目都不是独立的，它在回答 agent 经济栈里的一个具体问题

### 下一步工作

1. 整理本周学习内容
2. 继续读 Handbook Web3 基础部分

<!-- DAILY_CHECKIN_2026-05-21_END -->

# 2026-05-22

<!-- DAILY_CHECKIN_2026-05-22_START -->

### Co-Learning

1. 参加了 Swen Chan 主持的 Co-Learning 指南会
2. 了解了 WCB 平台使用方法和常见 FAQ
3. 记录了 Hackathon 时间、赛道方向、组队方式等信息
4. 5/25 下一期 Co-Learning

### 分享会 — Week 1 例会

1. **tree tree — 优秀笔记分享**: 索引 + 分层重构的结构化整理法，强调笔记的可检索性和可复用性
2. **Z.AI Sophia — Open Agentic Economy**: ERC-8004/ERC-8183 Agent 经济协议标准，Agent 之间的经济协作、支付和结算
3. **li9292 / Evermind — Agent Long-term Memory**: 如何让 Agent 拥有持续上下文与长期一致性，解决跨会话上下文连续性问题
4. **Miratisu / Cobo — Agentic Wallet**: Agent 钱包的权限、签名执行与安全边界 — 如何让 AI Agent 在边界内安全操作链上资产
5. **Obsidian 知识库**: 每个人都该拥有自己的本地知识库 — 把个人素材、方法论、经历喂给 AI，输出才是自己的
6. 下周课程预告：5/25 Co-Learning + Week 2 AI×Web3 交叉实践
7. Q&A: 讨论涉及 Agentic Commerce、AI Security、Privacy、Chainlink、DePIN、Tokenomics 等方向

### 随堂笔记

> AI 没有立场、没有经历、没有审美。你需要把自己的素材、方法论、经历、判断喂给它，输出的才是带你自己印记的东西。

### 下一步工作

1. 准备 5/23 的 Open Agentic Economy 深入场
2. 整理 Week 1 学习总结
3. 继续 Handbook Web3 基础学习

# 2026-05-23

<!-- DAILY_CHECKIN_2026-05-23_START -->

### Open Agentic Economy

1. 参加了 Sophia (Z.AI) 的 "Open Agentic Economy" 分享会
2. 核心论点：以太坊是机器经济中人类为中心的分布式结算与协调中枢
3. ERC-8004：Agent 可验证身份与信誉（三大注册表：Identity / Reputation / Validation）
4. X402：机器对机器支付，复兴 HTTP 402 状态码
5. Deep Funding：AI Agent 参与公共物品资金分配
6. 以太坊设计原则 CROPS：审查抵制、开源、隐私、安全

### 随堂笔记

> The infrastructure that AI agents transact on will shape how this new economy works. Who can participate, how trust gets established, where value flows, whether the playing field is open.
> That infrastructure is being designed right now. And the design choices being made will compound as AI activity scales.
> Ethereum is the neutral layer where agents can settle value and make commitments.

### 下一步工作

1. 整理 Week 1 整体学习总结
2. 继续 Handbook Web3 基础学习

<!-- DAILY_CHECKIN_2026-05-23_END -->

<!-- Content_END -->
