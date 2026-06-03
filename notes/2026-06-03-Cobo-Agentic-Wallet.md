# Cobo Agentic Wallet 开发者教程 — Co-Learning 分享

**日期：** 2026-06-03（周三）
**分享人：** Moon（Cobo）
**来源：** Co-Learning 分享会 + Cobo 开发者教程
**文档：** [Google Doc 教程](https://docs.google.com/document/d/14rwdgmao_pwOxZozwaZA97k8C-HvG_0fEi703QY8wEo/edit)

---

## 分享会概述

Moon 在本次 Co-Learning 中详细讲解了 Cobo Agentic Wallet（CAW）的开发者接入教程，涵盖从零开始的 Skills 接入、CLI 操作、API 调用到 Pact 权限系统完整流程。正值黑客松 Cobo 赛道（3500U 奖金），内容即是对参赛者的技术赋能。

## Cobo Agentic Wallet 是什么

CAW 是 Cobo 推出的 **AI Agent 原生钱包**——让 AI Agent 能够自主管理加密资产、执行链上操作（转账、合约调用、消息签名），同时通过 **Pact 权限系统** 保留人类审批控制，兼顾自主性与安全性。

**核心特性：**
- Agent 可以在 Pact 规则内**自主发起交易**
- 支持 **MPC（多方计算）** 钱包创建和签名
- **人类审批** 机制：Pact 提交后在 CAW App 上审批
- 支持多链（ETH/SOL 等）
- 提供 Skills、CLI、API、SDK 四层接入方式

---

## 接入方式（四层）

### 1. Skills 方式（推荐）

最快捷的接入方式，适用于 **Codex、Claude Code、Cursor、OpenClaw、Hermes** 等任意 Agent 框架：

```bash
npx skills add cobosteven/cobo-agentic-wallet-dev --skill cobo-agentic-wallet-dev --yes --global
```

Agent 安装后：
1. 指示 Agent 创建钱包 → 自动完成 MPC 钱包初始化
2. 下载 CAW App（Testflight）→ 指示 Agent **完成 App 配对**
3. Agent 生成 8 位配对码 → 在 App 中输入配对码完成 MPC 交互
4. **配对后 Agent 发起交易前必须先提交 Pact**，经 App 审批通过后在规则内自由交易

**开发者环境：**
- 官网：https://agenticwallet.dev.cobo.com/agentic-wallet
- Skills：https://github.com/cobosteven/cobo-agentic-wallet-dev
- Testflight（支持 Mock 登录）：https://testflight.apple.com/join/Gs397pnJ
- 注意：Mock 登录可用任意字符串，但任何人知道该字符串即可登录，勿充大额资产

**正式环境：**
- 官网：https://agenticwallet.cobo.com/agentic-wallet
- App Store：https://apps.apple.com/app/id6761912352
- Google Play：https://play.google.com/store/apps/details?id=com.cobo.agenticwallet
- Skills：https://github.com/CoboGlobal/cobo-agentic-wallet/

### 2. MCP 方式

参考文档配置 MCP Server，以 MCP 形式给 AI Agent 使用。但默认可选推荐 Skills（功能更强大）。

- MCP 文档：https://www.cobo.com/products/agentic-wallet/manual/developer/mcp

### 3. CLI 方式

安装后的目录结构：

```
~/.cobo-agentic-wallet/
├── bin/
│   ├── caw           # CAW 主执行程序
│   └── caw.meta
├── cache/
├── config/           # 默认配置文件
├── logs/
├── profiles/
│   └── profile_caw_agent_xxx/  # 每个 Agent 独立配置
│       ├── credentials/
│       ├── tss-node/
│       │   ├── cobo-tss-node
│       │   ├── configs/
│       │   ├── db/secrets.db
│       │   ├── logs/
│       │   └── recovery/
```

**创建钱包（dev 环境）：**
```bash
~/.cobo-agentic-wallet/bin/caw onboard --env dev
```
→ 返回 session_id，查询进度至 `wallet_status: "active"`

**创建 Pact 示例（Uniswap V3 交易）：**
```bash
# 定义策略
POLICIES=$(jq -c -n '[{"name":"base-eth-usdc-uniswap-v3-swap","type":"contract_call","rules":{"effect":"allow","when":{"chain_in":["BASE_ETH"],...},"deny_if":{"usage_limits":{"rolling_24h":{"tx_count_gt":1}}},"always_review":true}}]')

# 提交 Pact
caw pact submit \
  --name "Swap 0.0005 ETH to USDC on Base" \
  --intent "Swap 0.0005 ETH to USDC on Base via Uniswap V3" \
  --recipe-slugs uniswap-v3-swap \
  --policies "$POLICIES" \
  --completion-conditions "$CONDITIONS"
```

**App 审批后发起交易：**
```bash
CALLDATA=$(caw util abi encode --method "exactInputSingle(...)" --args '...')
caw tx call \
  --pact-id <pact_id> \
  --chain-id BASE_ETH \
  --contract <router_addr> \
  --calldata "$CALLDATA" \
  --value 0.0005
```

### 4. API 方式

CAW 本质是 API 的封装，可直接通过 REST API 完成所有操作。

**流程：**
1. 启动 TSS Node：`cobo-tss-node init && cobo-tss-node start --caw`
2. 创建 API Key：`POST /api/v1/principals/provision`
3. 创建钱包：`POST /api/v1/wallets`（含 main_node_id）
4. 创建地址：`POST /api/v1/wallets/{uuid}/addresses`（ETH type 兼容所有 EVM 链）
5. 发起配对：`POST /api/v1/wallets/pairs/initiate`
6. 创建 Pact：`POST /api/v1/pacts/submit`
7. 使用 Pact 的 API Key 发起交易

**开放 API 文档：** https://api-core.agenticwallet.dev.cobo.com/api/v1/docs

---

## SDK

| 语言 | 包名 | GitHub |
|------|------|--------|
| Python | `pip install cobo-agentic-wallet` | [cobo-agentic-wallet-python-sdk](https://github.com/CoboGlobal/cobo-agentic-wallet-python-sdk) |
| TypeScript | `npm install @cobo/agentic-wallet` | [cobo-agentic-wallet-typescript-sdk](https://github.com/CoboGlobal/cobo-agentic-wallet-typescript-sdk) |

SDK 除 API 封装外，提供了常用 Agent 框架的 Tools 封装。

---

## 安全机制：Pact 权限系统

Pact 是 CAW 的核心安全设计：

| 概念 | 说明 |
|------|------|
| **Pact 策略** | 定义 Agent 可以做什么（允许的链、合约、操作类型） |
| **频率限制** | 24h 内交易次数 / 金额限制 |
| **人类审批** | `always_review: true` 强制每次交易需 App 确认 |
| **Pact API Key** | 每个 Pact 生成独立 API Key，交易时必须使用 |

**工作流：** 用户意图 → Agent 生成 Pact → App 审批 → Agent 在规则内自由执行

---

## 黑客松应用

本次黑客松 **Cobo 赛道（3500U）** 主题为 **Agentic Economy × Cobo Agentic Wallet**：

- 利用 CAW 让 Agent 自主管理链上资产
- 可结合任何 DeFi 协议（Uniswap 等）实现复杂链上操作
- 需要设计合理的 Pact 策略来平衡自主性与安全性
- 项目必须**开源**，提交截止 6/13 12:00

## 小作业

1. 通过 Agent + Skills 完成任意钱包操作（转账/合约调用/消息签名）
2. 通过 API / SDK 完成任意 DeFi 操作
