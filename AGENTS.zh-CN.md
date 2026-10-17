> 本文是 [English version](AGENTS.md) 的中文翻译；如有出入以英文版为准。

# AGENTS.md — PABench

PABench 是一个面向消费级个人 AI 智能体的开放基准测试。本仓库同时支持**人工执行**和 **agent 执行**的评测。

## 如果你的任务是**运行评测**

先阅读 `skills/pabench-run/SKILL.md` 并严格遵循。简要流程：

1. 选择任务：`M001`、`R001`、`R002`、`E001` 或 `P001`。
2. 阅读对应的 manifest（`tasks/manifests/<TASK-ID>.yaml`）、任务规格（spec）和执行手册（runbook）。manifest 驱动执行，spec 定义评分。
3. **逐字**发送 Prompt，遵守会话边界和等待时长，逐步采集证据。
4. 登录、验证码、身份/年龄验证、OAuth 授权交还给人处理，绝不绕过。
5. 在 `results/<product>/<task-id>/` 下填写评测记录卡。

硬性安全规则：只用测试账号；绝不发送邮件/消息；绝不预订或付款；绝不提交未脱敏的个人数据。

## 如果你的任务是**修改框架**

- 英文为权威版本；每个 `*.md` 文件都有对应的 `*.zh-CN.md` 中文翻译。修改英文文件时，必须在同一次变更中同步更新中文版。manifest（YAML）使用英文键、不做翻译；其中引用的测试 Prompt 必须与任务规格逐字一致。
- 任务规格位于 `tasks/<category>/`，操作执行手册与其同目录（`*.runbook.md`），机器可读 manifest 位于 `tasks/manifests/`。
- 三层保持一致：spec（评分）、runbook（人工步骤）、manifest（agent 步骤）。任何 Prompt 改动必须同时落到三处。
- 记录规范见 `results/README.md`。
