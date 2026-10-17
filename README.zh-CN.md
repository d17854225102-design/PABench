> 本文是 [English version](README.md) 的中文翻译；如有出入以英文版为准。

# PABench

## 个人智能体基准测试

PABench 是一个面向消费级个人 AI 智能体（Personal AI Agent）的开放评测框架。

与聚焦于知识、推理或模型能力的传统 AI 基准测试不同，PABench 通过真实世界场景评估一个 AI 智能体能否成为可靠的个人助手。

## 研究问题

核心问题：

> 个人 AI 智能体能否理解用户、完成复杂任务，并减少人们日常工作与生活中的负担？

## 评测维度

PABench 评估六项关键能力：

- **记忆（Memory）** — 智能体是否理解并记住用户？
- **研究（Research）** — 它能否收集、核实并综合信息？
- **规划（Planning）** — 它能否管理多约束目标？
- **执行（Execution）** — 它能否使用工具并完成任务？
- **应变（Adaptation）** — 当条件变化时，它能否做出响应？
- **信任（Trust）** — 用户能否安全地将工作委托给它？

## 评测轨道

### 人工评测轨道

真实用户通过官方应用与产品交互，并记录：

- 任务完成情况
- 用户负担
- 交互质量
- 可靠性

### 自动化评测轨道

本仓库可以直接交给具备浏览器/应用操作能力的 agent（例如带桌面自动化能力的编程 agent）。`skills/pabench-run/SKILL.md` 这个 skill 会把每个任务变成一次有人监督、产出证据的评测运行：

- `tasks/manifests/` 中的机器可读 manifest 驱动执行：逐字 Prompt、会话边界、等待时长、证据路径、停止规则。
- agent 扮演测试者：操作被测产品、采集证据，并在 `results/` 下填写评测记录卡。
- 登录、验证码、年龄/身份验证、OAuth 授权由人处理；评分由 agent 给出建议、人确认。

给你的 agent 的指令示例：

> 阅读 `skills/pabench-run/SKILL.md`，对 `<产品>` 运行 M001 任务。登录和验证由我来处理。

## 首批评测产品

PABench v0.1 聚焦于评测：

- Dots
- Muse
- Cue
- Grok Bot

## 仓库结构

```
PABench/
├── docs/             # 基准测试理念、方法论、评分、任务设计
├── tasks/            # Golden Task（基准任务）（记忆 / 研究 / 执行 / 规划）
│   └── manifests/    # 供 agent 运行的机器可读任务定义
├── personas/         # 可复用的测试用户画像（Persona）
├── templates/        # 任务、执行手册与评测模板
├── skills/           # pabench-run：agent 执行 skill
├── assets/           # 虚构测试数据集（邮件、日历）
├── results/          # 各产品的评测结果
└── AGENTS.md         # agent 接手本仓库的入口说明
```

## 项目状态

框架 v0.1 与任务层（Task Layer）v0.1 已完成：5 个 Golden Task（基准任务）
（[M001](tasks/memory/M001-user-profile.md)、R001、R002、E001、P001）、
操作执行手册、测试数据集、中文翻译，以及通过 `skills/pabench-run` 提供的 agent 运行支持。
