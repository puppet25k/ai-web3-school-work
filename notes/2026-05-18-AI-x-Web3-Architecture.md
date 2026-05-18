# 分享笔记：AI 时代 Web3 开发者需要具备的基础知识和架构能力

> 日期：2026.05.18（周一）19:00-21:00
> 分享人：Jessica / ETHPanda / tc
> 来源：AI x Web3 School 共学营（Co-Learning 线上会议）
> 来源文件：飞书截图 20260518-214255（16 张）

---

## 一、核心观点

> **AI 是用来增加效率的，但系统设计还是依赖于人脑本身**
> **AI 是效率杠杆，不是设计替代。架构决策、系统设计、边界判断仍然需要人来完成。**

**关于 AI 与 Web3 的关系：**
- AI 无法从根本上消除分布式系统的复杂性，它只是加速了代码堆砌
- 生成的错误代码同样会导致严重的资产损失
- 最终的审核与责任始终在开发者手中。**AI 是工具，系统掌控力是开发者的终极防线**

---

## 二、AI Agent 与开发工具实践

### 多 Agent 协同方案
群里讨论了几种组合方式：
- **Hermes + Claude Code + Codex**：Hermes 作为总调度，Claude Code 做主力开发，Codex 做辅助
- **直接 Hermes 调用 Claude Code**：简化链路，减少上下文切换
- **Cursor** + Hermes 对比：各有优劣，取决于任务类型

### Hermes Agent 特性（截图来源：Draken 分享）
- 支持 7 种终端后端：local / Docker / SSH / Singularity / Modal / Daytona / Vercel Sandbox
- Daytone / Modal 提供 Serverless 持久化，环境在空闲时休眠，按需唤醒
- 支持 Batch trajectory 生成和压缩，用于训练下一代 tool-calling 模型
- 安装方式：Linux/macOS/WSL2 + Windows（PowerShell，Beta）
- GitHub：https://github.com/NousResearch/hermes-agent

### AI 核心概念（Notion 笔记截图）
- **Temperature**：控制输出随机性
- **Top-K**：从概率最高的 K 个词中选择输出
- **幻觉（Hallucination）**：模型生成看似合理但实际错误的信息
- **主流模型**：ChatGPT / GPT-4 / Claude / Gemini / DeepSeek
- **国内产品**：豆包、Qwen（通义千问）、混元
- **模型开放程度**：闭源（GPT-4, Claude）→ 开放权重（LLaMA, Mistral）→ 完全开源（Stable Diffusion）

---

## 三、Web3 信任模型与架构

### 信任的演变（tc 分享）
> "以前是信任 Bank Institution（权威），现在是去中心化信任"
- 区块链不止是数据库，而是**确定的状态机**
- 解决了两个核心问题：用户付款的问题、平台收款的问题
- **本质**：执行 Smart Contract → 链上状态变更 → 无可辩驳的账本记录

### Web3 Block Chain 的定位
- Bank Institution → Web3 Block Chain 的桥梁
- 各种 Layer1 / Layer2
- 请求流：支付怎么完成的？
- 资金流：钱是怎么流转的？

### 交易关键参数（tc 幻灯片）
| 参数 | 说明 |
|------|------|
| **Gas** | 系统的动力源。EIP-1559 机制 + Blob Gas（Ethereum） |
| **Nonce** | 顺序的守护者。防止重放攻击与交易乱序执行，确保账户状态变更的原子性 |
| **Data** | 智能合约的指令集。定义复杂的业务逻辑与参数传递 |
| **跨链** | EVM / Tron / BTC / Solana 等环境各自有差异 |

---

## 四、安全：不是插件，是核心属性

> 粉丝提问："安全可以后续再考虑吗？"

- 在 Web3 世界中，由于直接和资金交互的特性，**安全不是一个可以随时添加的"插件"，而是源于设计的核心属性**
- **误区**："审计可以补" — 无法解释系统行为，就无法保证资产安全
- 实际建议（来自 Cyrus）：
  - 学习安全 → 打 CTF → 参加审计比赛
  - 但审计比赛门槛高，**建议先做开发，积累经验后再转向安全方向**

### 钱包安全
- **私钥 → 公钥 → 钱包地址**：可以根据地址反推拿到公钥吗？不行 — **地址主动交易才会暴露公钥**
- **Rabby Wallet**：在"只签名可信交易"方面做得很好（多签支持）
- 交易所普遍采用**多签**机制

---

## 五、关键概念详解

| 概念 | 说明 |
|------|------|
| **ERC-4337** | 账户抽象（Account Abstraction）标准，让钱包不再是普通 EOA，而是智能账户；Session Key、权限限额、恢复机制是 AI × Web3 的关键基础设施 |
| **Deposit Account** | 对每个 order 计算 deposit account 并给到用户 |
| **UTXO** | 比特币模型，等待 block confirmation |
| **多签（Multi-sig）** | 多个私钥共同控制一个账户，交易所通用做法 |
| **Web3 tx core params** | Nonce、Gas（EIP-1559 / blob）、fee、amount；跨链环境包括 EVM / Tron / BTC / Solana |

---

## 六、学习资源

### 系统学习路径
- [**Cyfrin Updraft**](https://updraft.cyfrin.io/career-tracks) — 国外最全的 Web3 各职位学习路径，覆盖开发、安全、审计等方向，支持中文字幕（需安装 Immersive Translate 插件）

### 入门建议
- **看书入门**（Okkotsu.eth 推荐）
- **多读代码、做项目**
- **先做开发，再转安全**（降低门槛）
- 或者看几本基础书籍

### 群友提问汇总
1. 残酷共学打卡写什么内容？
2. 如何进入 Web3 开发？自己做了 dapp 但没有实际 Web3 工作经验
3. 大陆做 Web3 的风险问题
4. Claude Pro 还要用 Hermes 吗？还是直接用 Claude Code 就好？

---

## 七、延伸思考

- AI 时代 Web3 开发者需要掌握的不仅仅是智能合约，还有跨链知识、账户抽象、Gas 机制等架构层面的理解
- 系统设计能力是 AI 无法替代的核心竞争力
- 安全不是后加的补丁，是设计之初就要考虑的核心属性
- 多 Agent 协同是一个值得探索的方向：用 Hermes 编排、Claude Code 写代码、Codex 辅助，各取所长
