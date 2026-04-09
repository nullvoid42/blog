---
title: Ralph — 自主 AI Agent 循环
date: 2026-04-09
---

Author: Gavin & HermesAI

今天发现了一个很有意思的项目：**Ralph**——基于 Geoffrey Huntley 提出的 Ralph 模式。

## 是什么

Ralph 是一个**自主 AI Agent 循环框架**。它反复调用 AI 编程工具（Claude Code 或 Amp），直到产品需求文档（PRD）中的所有任务全部完成。

核心思路：**人类只做一次需求输入，后续全部由 Agent 自动完成。**

## 核心逻辑

- **循环迭代**：每次迭代都是全新的 AI 实例（干净上下文），避免上下文污染
- **持久记忆**：通过 `prd.json`（任务状态）、`progress.txt`（学习记录）、`git history` 来传递信息
- **质量门禁**：每次任务完成后自动运行类型检查和测试，通过才提交

## 三步骤

**Step 1 — 创建 PRD**
用 `/prd` skill 生成产品需求文档，输出为 `tasks/prd-[feature].md`

**Step 2 — 转换为 Ralph 格式**
用 `/ralph` skill 把 PRD 转为 `prd.json`，包含带优先级和 `passes` 状态的用户故事列表

**Step 3 — 运行 Ralph**
```bash
./scripts/ralph/ralph.sh --tool claude
```
Ralph 自动：建分支 → 选最高优先级任务 → 编码 → 跑测试 → 提交 → 更新 prd.json → 重复

## 关键文件

| 文件 | 作用 |
|------|------|
| `prd.json` | 任务列表，含 passes 状态 |
| `progress.txt` | 每次迭代的学习笔记 |
| `ralph.sh` | 循环脚本，支持 Amp/Claude Code |

## 相关链接

- Ralph: <https://github.com/snarktank/ralph>
- Ralph + Claude Code: <https://github.com/frankbria/ralph-claude-code>
- Geoff Huntley 原版介绍: <https://ghuntley.com/ralph/>
