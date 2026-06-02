# Z.ai GLM-5.1：8 Hour Autonomy — 开源模型的深度 agent 时代

> **学习日期：** 2026-06-02
> **分享者：** Z.ai（智谱 AI）— Cara
> **来源：** Google Slides — "5.1_Z.ai: brief"
> **标签：** #GLM #Zai #8HourAutonomy #Agent #OpenWeights #LLM

---

## 一、Z.ai 简介

| 维度 | 数据 |
|------|------|
| 成立 | 2019 年 |
| 最新旗舰 | **GLM-5.1** |
| 许可证 | **MIT Open Weights**（完全开源权重） |
| 生态演进 | GLM-130B → ChatGLM → GLM-4 → GLM-5 → **GLM-5.1** |

> **Z.ai 不只 GLM 的创造者**，更在推动开源模型在 Agent 深度的前沿探索。

---

## 二、GLM 模型演进时间线

```
2022-2024       2025.07         2025.09-12        2026.02         2026.04
GLM-130B→GLM-4  GLM-4.5         Tool/Reasoning    GLM-4.6/7       GLM-5.1
第一个基础模型   355B MoE        工具/推理能力增强                   8 Hours agentic depth
                代码&Agent能力                       GLM-5
                                                     744B MoE
                                                     frontier agentic
```

**GLM-5（2026.02）：** 744B MoE，前沿 agentic engineering  
**GLM-5.1（2026.04）：** 聚焦 8 Hours agentic depth

---

## 三、8 Hour Autonomy = 深度，不是时长

> **"8 Hours = Depth, not time length"**

### 核心理念

传统 Agent 评测指标侧重"广度"（知道多少知识、回答多少问题）。  
GLM-5.1 的 8 Hour Autonomy 侧重**深度**（一个任务能持续自主地推进多远）。

**Level 2 — DEPTH：**
- 不是往前冲（Not pushing forward）
- 而是进入**实验循环**（Get in the Experiment Loop）
- 数百轮迭代、数千次工具调用
- 在一个复杂任务上不断深入、试错、修正、推进

### Demo：8 Hour Linux Desktop Build, 1200 Steps

一个 Agent 花了 8 小时、1200 步，独立完成了一个 Linux 桌面环境的构建。这不是简单的"回答问题"，而是持续 8 小时的自主工程推进。

---

## 四、GLM 的技术路线：战略押注 ARC

| 时间 | 里程碑 | 技术要点 |
|------|--------|---------|
| 2025.07 | GLM-4.5 | 可验证 RL 环境 + SLIME |
| 2025.12 | **交错思考（Interleaved Thinking）** + 保留思考（Preserved Thinking） |
| 2026.02 | GLM-4.7 | DSA（注意力分配）：解决"记住太多" vs "遗忘"的平衡 |
| 2026.02 | **GLM-5** | 744B MoE，前沿 agentic engineering |

### 长期上下文连贯性

> 像一位可靠的**项目经理**：
> - DSA（注意力分配）让模型知道该关注什么
> - 保留思考让关键推理步骤不丢失
> - 通过"交错思考"机制，模型在长任务中保持逻辑连贯

---

## 五、深度的代价与收益

**验证实验：Opus 4.7 for Depth**

| 维度 | 变化 |
|------|------|
| **长期上下文召回（1M tokens）** | 从 78% → 32%（下降） |
| **Agentic Coding（MCP-Atlas）** | 显著提升 |
| **本质取舍** | 记住一切 vs 每一步走得更深 |

> 为了深度，模型必须主动"忘记"一些信息，把注意力集中在当前最关键的任务上。这是有意的设计选择。

---

## 六、定价：开源模型的成本优势

| 模型 | 输出定价 | 倍数（vs GLM-5.1） |
|------|---------|-------------------|
| **GLM-5.1** | **~$3/MTok** | **1×（基准）** |
| Claude Opus 4.5 | $25/MTok | 8.3× |
| Claude Sonnet 4.6 | $15/MTok | 5× |
| GPT-5.2 | $15/MTok | 5× |

> **前沿性能，几分之一的成本**——对于 token 密集的 agent 工作流来说至关重要。

---

## 七、Hackathon 实用建议

**在长运行 Agent 中最容易出问题的三个地方：**

### 1️⃣ Goal Drift（目标漂移）
> 模型可能花 3 小时优化状态栏的字体，然后忘了还要构建文件管理器。

**对策：** 给明确的检查清单，每几步重新读原始目标，不要假设它记得。

### 2️⃣ Error Accumulation（错误累积）
> 第 400 步的一个微小 bug，到第 800 步才显现——此时已有 400 步代码堆在上面。

**对策：** 要求模型自测。"在继续之前，给你刚写的东西写个测试。"

### 3️⃣ Strategy Rigidity（策略僵化）
> 大多数模型被训练为"持续推进"而不是"灵活转向"，会在错误的方法上死磕。

**对策：** 如果 Agent 卡住几轮，打断它——让它退一步，列出已尝试的方案，换一个方向。

> **这三个习惯会让所有模型——无论哪家的——在长任务上表现更好。**

---

## 八、下一个里程碑（Coming Soon）

- **Security（安全）**
- **Legal（法律）**
- **Investment Banking（投行）**
- **Consulting（咨询）**

---

## 九、一句话总结

> **GLM-5.1 的 8 Hour Autonomy 重新定义了 Agent 能力的衡量标准——不是"它能回答多少问题"，而是"它能自主推进一个复杂任务多久、多深。"**
> 
> 开源模型（MIT 权重）+ 前沿性能 + 1/5 ~ 1/8 的价格，让 token 密集的 agent 工作流变得切实可行。
