> 本文是 [English version](task-template.md) 的中文翻译；如有出入以英文版为准。

# 任务 ID — 任务名称

## 元数据（Metadata）

| 字段 | 值 |
|---|---|
| 任务 ID | X000 |
| 类别 | memory / research / execution / planning |
| 难度等级 | 1–5（见 docs/task-design.md） |
| 版本 | 0.1 |
| 用户画像（Persona） | personas/<persona-file>.md |

## 目标（Objective）

本任务评估哪项能力，以及它为什么对个人 AI 智能体（Personal AI Agent）重要。

## 用户画像（User Persona）

引用本任务使用的用户画像定义。同一用户画像应跨任务复用，以保证结果可比较。

## 初始状态（Initial State）

- 账号状态（全新 / 已有 / 记忆已清空）
- 已连接的服务及已授予的权限
- 预置的输入材料（文件、邮件、日历条目）
- 开始前需记录的产品版本、订阅档位和平台

## 所需权限（Required Permissions）

智能体在本任务中需要（或明确禁止使用）的权限。

## 标准操作路径（Standard Operation Path）

按编号划分阶段。每个阶段需定义：

- 提供给智能体的提示词（逐字记录，使运行可复现）
- 时机条件（同一会话 / 新会话 / N 小时后）
- 评测人员在每一步观察什么

## 预期智能体行为（Expected Agent Behavior）

一个有能力的个人 AI 智能体应有的行为，以可观察的行为表述，而非内部推理。

## 成功标准（Success Criteria）

完全通过（full pass）的客观条件。每条标准都必须能从留存的证据中验证。

## 部分成功标准（Partial Success Criteria）

介于完全通过与失败之间的分级结果，使部分胜任的智能体得以区分，而不是一律归入"失败"。

## 失败条件（Failure Conditions）

构成失败的可观察行为，包括不诚实行为（声称做了实际没做的事）。

## 指标（Metrics）

按 docs/scoring.md 评分：

- 任务成功度（Task Success，0–3）
- 用户负担（User Effort，干预次数、纠正次数、人工补完次数）
- 达到的自主等级（Autonomy Level，L0–L5）
- 可靠性（Reliability，输出内容的事实准确性）
- 安全性（Safety，是否遵守权限边界、是否诚实说明自身局限）

## 证据要求（Evidence Requirements）

- 带时间戳的完整提示词日志
- 智能体输出（文本、文件、执行的操作）
- 相关产品状态的截图或导出（记忆界面、任务列表、日历）
- 产品名称、版本、订阅档位、平台、账号类型
- 人工干预次数及每次干预的触发原因

## 评测注意事项（Evaluation Notes）

- 区分"接入受阻"（验证限制、地区限制、订阅档位限制）与"能力缺失"。
  受阻步骤记为*未测试*，而不是记零分。
- 区分"未验证"与"不支持"。
- 执行停止规则：遇到硬性的接入/权限受阻时，记录并停止；同一故障有限次重试；
  不要为了强行通过而无休止地更换工具或提示词。
