# Railgun & Kohaku：EVM 上的隐私世界

> **学习日期：** 2026-05-25
> **来源：** @0xMalingshu Co-Learning 分享（冬天の馬鈴薯🥔，Co-CTO @Zzyzx_labs）
> **原文：** [X 长文](https://x.com/0xMalingshu/status/2016137832465682514)
> **标签：** #隐私 #ZK #Railgun #Kohaku #Ethereum #PPOI

---

## TL;DR

- **Kohaku** — 让隐私交易变简单的开发工具包，把 Railgun 的 4 步流程封装成一行 `transfer`
- **Railgun** — EVM 上的完全匿名系统，用 **UTXO 模型** 隐藏金额、发送者、接收者
- **PPOI（清白证明）** — ZK 证明资金来源干净，合规与隐私不冲突
- **Broadcaster + Waku** — 隐藏 IP 地址的 P2P 路由机制

---

## 一、为什么需要链上隐私？

Ethereum 三大隐私痛点：

| 痛点 | 说明 |
|------|------|
| 🔓 **交易透明** | 所有人的交互公开透明——在区块链上「裸奔」 |
| 🖥️ **RPC 中心化** | 发交易时暴露 IP 和钱包地址给 RPC 节点 = 变相 KYC |
| 🎯 **代币发现风险** | MetaMask / 钱包自动发现会向中心化服务器泄露数据 |

理想的钱包应具备：交易匿名化（Railgun） + 本地运行节点 + 轻客户端 + IP 隐藏（Waku/Tor）

---

## 二、Kohaku：Ethereum 隐私工具箱

Kohaku 是一个面向开发者的工具包（Viem 风格封装），包含三个组件：

| 组件 | 状态 | 说明 |
|------|------|------|
| **Railgun** | ✅ 可用 | 老牌隐私项目（2022 启动） |
| **Privacy Pool** | 🔄 开发中 | 隐私池 |
| **Tornado** | 🔄 开发中 | 非 Tornado Cash，不同项目 |

**核心价值：** 原生 Railgun 需 4 步操作（Gas 估算 → Broadcaster 费用 → 生成 Proof → 打包），Kohaku 封装成一步 `transfer`，大幅降低开发门槛。

---

## 三、Railgun：EVM 上的完全匿名系统

### 为什么选 UTXO 模型而不是 Account 模型？

| 维度 | Account 模型 | UTXO 模型（Railgun） |
|------|-------------|-------------------|
| **隐私** | 余额更新透明，难以切断地址关联 | 只有「票据」（Note），可加密隐藏 |
| **并发稳定性** | 余额变动会 invalidate 已有 ZK Proof | Note 互相独立，不受他人交易影响 |

### 0zk 地址

进入 Railgun 隐私世界的入口，三大用途：接收资金（Shield） → 隐私转账 → 隐私跨合约交互

```
0zk 地址 = Spending Key（控制权） + Viewing Key（观察权）
```

- **Spending Key（私钥）：** 控制资产的权力，永不分享
- **Viewing Key（观察密钥）：** 仅可查看不可动用，可分享给审计/税务机构

### 核心架构

**ZK 电路（三个子电路）：**
1. **Tree Circuit** — 证明 Note 存在性和 nullifier 有效性
2. **Action Circuit** — 处理代币转换
3. **Tx Circuit** — 验证多个 Action 的一致性和整体逻辑

**Broadcaster + Waku（网络隐私）：**
- **Broadcaster** — 代用户广播交易到链上，隐藏发送者身份
- **Waku** — P2P 消息路由（类似 Tor），消息经无数节点跳转，Broadcaster 只知道来自 P2P 邻居

---

## 四、操作流程

### Shield（入金）
资产从公开 0x 地址 → 0zk 地址。入金不生成 ZK Proof、不走 Broadcaster + Waku。仅支持 ERC-20（不支持原生 ETH）。

### Unshield（出金）
4 步流程：计算 Gas → 计算 Broadcaster 费用 → 生成 ZK Proof & Nullifier → 发送与监听

### 隐私转账
0zk 地址之间转移，**强烈建议使用 Broadcaster**，否则隐私性大减。

### 跨合约交互（隐私 DeFi）
```
User → Adapt → Railgun Core（验证+代币转换）→ Adapt → 外部合约（如 Uniswap）→ Adapt → Railgun Core（存回）
```
Adapt 分离职责，提升可组合性和可维护性。

---

## 五、PPOI：合规与隐私不冲突

**Private Proofs of Innocence（清白证明）** — 不良交易预防系统。

**数据来源：** Elliptic（链上分析）+ ScamSniffer（钓鱼监控）+ PureFi（合规分析）+ SlowMist（安全审计）+ Chainalysis Sanctions Oracle（制裁名单）

**运作流程：**
1. Shield 入金 → **1 小时观察期**（只能原路返回，确保名单有足够时间更新）
2. 自动生成 ZK 证明：*"这笔资金不在现有黑名单中"*
3. 证明随币流动：Alice → Bob → Carl 持续传递
4. 名单共享给 Broadcaster、CEX 或审查方

> 资金来源不干净 → Broadcaster 拒绝服务 | 资金干净 → 可向 CEX/执法机关证明清白

---

## 六、局限性

| 问题 | 说明 |
|------|------|
| 🔴 **Gas 贵** | UTXO 隐私系统的代价，不适合小额交易 |
| 🐢 **证明生成慢** | Wasm 约 1-2 秒，老设备更慢 |
| ⏳ **同步慢** | 需下载链上所有 Railgun 事件，用 Viewing Key 逐个解密 Note |
| 👥 **流动性依赖** | 用户越多越安全，流量差则隐私性下降 |
| ⚖️ **合规风险** | 监管（Tornado Cash 前车之鉴） |

---

## 七、对比：Tornado Cash vs Railgun

| 维度 | Tornado Cash | Railgun |
|------|-------------|---------|
| **隐私等级** | 发送者-接收者不可关联 | 完全匿名 |
| **功能范围** | 切断地址关联 | 隐私转账 + 隐私 DeFi → 隐私世界 |
| **资金池** | 固定面额（0.1/1/10 ETH） | 任意金额 |
| **Note 管理** | 自行保存 Note，丢失即无法提款 | Viewing Key 体系，自动管理 |
| **扩展性** | 有限 | Adapt 桥接 DeFi 交互 |

---

## 八、RAIL 治理代币

> RAIL 是治理代币，非使用隐私系统的必要条件，也非隐私代币。

**质押收益：**
- 每次 Shield/Unshield 扣除 0.25% 分给活跃治理者
- 国库每两周发放 2% 给活跃治理者（年化约 52%）

**治理流程：** 提案发起（30 天支持期，需 50 万票）→ 投票（3 天）→ 否决期（1 天）→ 执行（7 天窗口）

1 RAIL = 1 票。支持提案不减投票权。委托投票后奖励归委托人（⚠️ 不要委托）。

---

## 一句话总结

> **Railgun 让我们在区块链上把「衣服」穿回去，拿回自由和权利。**
> **Kohaku 让我们能更好地穿衣服。**
> **PPOI 告诉世界：合规与隐私并不冲突。**

尽管 Railgun 还不够快、不够便宜，但万里长征已经迈出第一步。

---

*整理于 2026-05-25 · AI x Web3 School 共学营 Co-Learning*
