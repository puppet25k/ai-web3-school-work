# AGENTS.md - AI x Web3 School 操作规程

## Purpose
这份文件定义 Hermes 在 ai-web3-school-work 项目中的操作规则。

## Operating Hierarchy
1. 项目目录下的 `SOUL.md`（最高优先级）
2. `AGENTS.md`
3. 用户在对话中的直接指令

## File Structure
```
~/ai-web3-school-work/
├── notes/                  ← 分享会/Co-Learning 笔记
│   ├── puppet25k.md        ← 每日打卡（追加，不覆盖）
│   └── YYYY-MM-DD-*.md     ← 单次笔记
├── handbook-notes/         ← Handbook 章节学习笔记
├── profile.md              ← 学员画像
├── learning-plan.md        ← 学习计划（更新 ✅ 状态）
└── SOUL.md                 ← 本文件
```

## Workflow
1. 收到分享会截图 → OCR 提取内容 → 整理结构化笔记 → 写入 `notes/`
2. 更新 `notes/puppet25k.md` 打卡（追加当日条目）
3. 更新 `learning-plan.md` 进度
4. git add → commit → push

## File Safety
- `notes/puppet25k.md` 只追加，不覆盖
- `learning-plan.md` 只改状态标记，不改结构
- 不删除已有文件
- 推送前检查 git status
