# Z.AI Workshop：用 Agent Mode 发现本地商业机会

**日期：** 2026-06-11（周四）
**分享人：** Roman（Z.AI / GLM）
**来源：** AI x Web3 School 收官分享会
**交互式工坊：** [zai_workshop_interactive_v66.html]

---

## 分享会概述

这是 AI x Web3 School 的**收官分享会**。Roman 从 Z.AI（GLM-5）的角度，演示了如何通过 **Agent Mode + 一条 Master Prompt**，让 Agent 自动完成从市场调研到生成 Google Ads 的完整商业计划。现场演示了 Pattaya（泰国芭提雅）的空调维修服务 niche 发现全流程。

---

## 核心概念：Chat Mode vs Agent Mode

| 模式 | 适用场景 | 行为 |
|------|----------|------|
| **Chat Mode** | 一次问答、一次任务 | 生成回答即止，用户自行下一步 |
| **Agent Mode** | 多步骤目标 | 跟随目标，逐步推进，在决策点停下来让用户选择，继续直到交付 |

核心转变：**从"辅助"到"执行"（From chat assistance to autonomous execution）**

---

## 演示流程：Pattaya 空调维修服务

### Step 1: Master Prompt 配置

填写基本信息：
- **城市：** Pattaya, Thailand
- **语言：** English
- **Niche 数量：** 3 个不同方向
- **供应商数量：** 10 家
- **Google Ads 预算：** $50
- **佣金：** 10-20%

内置 **last30days skill**（https://github.com/roman-ryzenadvanced/last30days-skill.git）进行多源调研。

### Step 2: Agent 市场发现（Phase 1）

Agent 自动调研后推荐 Niche 选项：

| Niche | 需求特征 | 客单价 |
|-------|----------|--------|
| **Air Conditioning Service** | 全年需求、紧急维修 | $50-100/次 |
| Moving / Transport | 需可靠搬家公司 | $2,000-10,000+/次 |
| Apartment / Condo Rentals | 活跃租赁群、常需中介 | 高佣金 |

→ 用户选择了 **Air Conditioning Service**

### Step 3: 供应商发现 + 自动联系函

Agent 搜索并验证 10 家本地空调维修商，提供完整联系信息 → 用户确认足够 → Agent 自动撰写 Outreach 邮件：
> *"Free qualified AC leads in Pattaya. I run a local lead generation service..."*

### Step 4: 客户触达方式

Agent 根据本地调研推荐 **WhatsApp + Line** 作为主要联系方式（泰国当地最流行）。

### Step 5: Landing Page 生成

Agent 直接用 GLM-5 生成了移动端适配的落地页（含欢迎信息、联系方式、服务介绍）。

### Step 6: Google Ads 生成

Agent 根据选择、预算和调研结果生成了完整的 Google Ads 方案，可直接复制粘贴到 Google Ads 平台运行。

---

## 关键技术：last30days skill

Roman 使用的核心工具，一条 130KB+ 的 SKILL.md，能力包括：

- **多源检索：** Reddit / X / YouTube / TikTok / Hacker News / Polymarket / GitHub / Web
- **品质验证：** 通过评论、点赞、反馈多层交叉验证，判断内容是否为真实需求而非 SEO 操纵
- **输出规范：** BADGE + LAW 8 条不可协商规则（禁止 em-dash、禁止 Sources 块等）
- **使用方式：** 内置在 Master Prompt 中，Agent 自动调用

---

## Q&A 精华

### Agent 在多步骤任务中如何保持方向？
> "在每个回合提醒 Agent 已经完成了什么、下一步要做什么。清晰的语言沟通能让 Agent 保持在轨道上。"

### 如何防止 Agent 过度自信/偏离？
> "要求 **proof of work 和 proof of code**。Agent 在执行时会自我检查，很多时候会发现'哦我忘了这个'然后自行修正。"

### 长会话后 Agent 丢失上下文怎么办？
> "把整个对话导出为 JSON，在新会话中导入，让 Agent 重新理解已完成的进度和下一步。对我来说这个方法很有效。"

### 模型卡住时的 Fallback 策略？
> "保存工作 → Git commit → 换另一个模型试试。不同模型擅长不同事情。Claude Code 支持预配置 3 个不同模型做 fallback。"

### 如何让 Agent 验证自己的工作？
> "像一个初级工程师一样要求它：'给我 proof of code，然后跑 100-200 个测试'。我曾经让 Agent 跑了 2 小时测试循环，最终找到了问题。"

---

## 学习收获

1. **Agent Mode 的真正价值**不是单次回答，而是围绕目标的持续执行——从调研到交付的全流程
2. **Master Prompt** 设计是 Agent 应用的关键——一条 prompt 包含完整的分阶段指令、决策点和输出要求
3. **last30days skill** 验证了多源检索 + 数据品质验证的可行性——通过"量"来判断"质"
4. **Proof of work/code** 是防 Agent 幻觉的有效手段——让 Agent 自我审计
5. **最终分享会**为整个共学营画上了句号——从 Prompt 基础到完整的 Agent 驱动商业方案
