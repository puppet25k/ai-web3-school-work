# Cobo Agentic Wallet：AI Agent 的链上安全架构

> **学习日期：** 2026-05-26
> **来源：** 分享会 — Cobo Agentic Wallet（Cobo 发布的 Agent 钱包方案）
> **标签：** #AgenticWallet #Cobo #MPC #Pact #Recipe #AIxWeb3

---

## 一、核心问题：Agent 管钱，怎么管才安全？

### 当前默认做法的风险

> **问题不再是"Agent 会不会管钱"，而是"怎么管"。**

| 风险类型 | 描述 |
|---------|------|
| **Silent Failure 1** | Agent 被提示词告知不要修改金额，但运行中自行修改了——后台无痕迹 |
| **Silent Failure 2** | Agent 在所有者托管边界之外创建新钱包并转移资金——无策略引擎、无审计、无终止开关 |
| **对抗性输入** | 恶意输入可让 Agent 执行未经授权的操作 |
| **不可见执行路径** | Agent 可创建所有者看不到的账户和执行路径 |
| **权限爆炸** | 宽泛的钱包访问权限让一次漏洞变成全面暴露 |
| **永不过期** | 过时密钥和永不过期的权限成为持续攻击面 |

### 一句话总结

> **语言可以表达意图，但无法强制权限。**
> 拥有原始钱包访问权的 Agent，在架构上没有理由"待在边界内"。

---

## 二、范式转变：从 Copilot 到 Agent

| 传统 Copilot 模式 | Agent 模式 |
|-----------------|-----------|
| AI 回答问题，人类做事 | AI 执行工作流，人类定义范围 |
| AI 建议操作，人类批准每一步 | AI 可以持续以机器速度移动资金 |
| **谁来持有私钥？** | **结构化授权 + 执行绑定** |

> Don't give agents wallets.  
> Give agents **scoped authorization**, bind execution to it.

---

## 三、Cobo Agentic Wallet：三大行业首创

Cobo 推出的 Agentic Wallet 重新定义了"AI Agent 如何上链"。

### 🔐 首创 1：MPC for AI Agents（MPC 门限签名）

```
传统：Agent 拿到完整私钥 → 可以任意操作
Cobo：私钥拆分为三份，任意两方共同签名
```

```
Agent Key Share  +  Cobo Key Share  =  Signed (2/2 Threshold)
Human Key Share  +  Cobo Key Share  =  Signed (2/2 Threshold)
```

- 私钥在**用户、Agent、Cobo** 三方之间拆分
- **没有任何一方能单独移动资金**
- Agent 不能单干，Human 也不能绕过 Agent 的授权范围

### 📜 首创 2：Pact 授权协议

**Pact = 结构化授权合约**，包含四个要素：

| 要素 | 说明 |
|------|------|
| **Intent（意图）** | Agent 被授权执行的具体任务或目标 |
| **Plan（执行计划）** | 透明可审查的路线图，说明 Agent 如何完成任务 |
| **Guardrails（护栏）** | 预算、审批、白名单、链/代币/合约约束等限制 |
| **Expiry（自动终止）** | 什么条件自动结束 Pact：时间到、预算花完、任务完成 |

**Pact 生命周期：**

```
Stage 1: 你声明意图 → Stage 2: Agent 起草 Pact
→ Stage 3: 你在手机 App 上审查和批准
→ Stage 4: 钱包在策略下执行，完成后自动终止，密钥自毁
```

- 每一步交易都经过 Pact 检查
- 自动完成时密钥自撤销

### 🧩 首创 3：Recipe 技能层

**Recipe = Agent 的"技能胶囊"**

- 将领域知识嵌入预定义、经过验证的工作流
- Agent 不再即兴发挥，而是沿预定义路径执行
- 弥合"Agent 想做什么"和"能做什么"之间的差距

**示例 Recipe：**
- Superfluid Streaming
- X402 Payment（HTTP 402 机器支付）
- Uniswap V3 Swap
- Polymarket Settlement

> Recipe 引导执行，确保合约地址和 ABI 参数不会被幻觉。

---

## 四、架构图：一个人 → 多个 Agent → 一个控制平面

```
                 Human (Owner)
            Strategy / Policies / Approvals
                       │
            ┌──────────┴──────────┐
            │                     │
      Trading Agent         Treasury Agent
      (交易策略)              (资金管理)
```

- 一个人类所有者，多个 Agent，一个控制平面
- 人类负责策略、政策和审批
- Agent 在 Pact 约束下执行

---

## 五、市场背景

| 指标 | 数据 |
|------|------|
| Agentic AI 市场规模（2025） | 已有显著规模 |
| 预计 CAGR 至 2034 | $139.19B |
| 2026 年初每日活跃链上 AI Agent | 持续增长中 |

> 当 AI Agent 以机器速度、不间断地移动资金时，**谁持有私钥？** 这个问题的答案决定了整个系统的安全边界。

---

## 六、一句话总结

> **不要把钱包给 Agent，要给 Agent 受约束的授权，并且让执行绑定在授权上。**
> Cobo 的三层方案（MPC 门限签名 + Pact 授权协议 + Recipe 技能层）把信任从"语言层面"转移到了"密码学层面"——这是一个数学保证，而不是软件承诺。
