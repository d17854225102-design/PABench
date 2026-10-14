> 本文是 [English version](README.md) 的中文翻译；如有出入以英文版为准。

# PABench 评测结果

按产品组织的评测结果。每个产品目录下每个任务一个文件夹，
每次运行是一份单独的记录文件，复制自
`templates/evaluation-template.md`。

## 目录结构

```
results/
├── dots/
│   └── M001/
│       ├── 20261020-run.md        # the evaluation record
│       └── evidence/              # prompt logs, screenshots (redacted), exports
├── muse/
├── cue/
└── grok/
```

## 记录规范

1. 每次运行一个文件：`results/<product>/<task-id>/<yyyymmdd>-run.md`。
   重新测试要新建文件；绝不要覆盖历史。
2. 第 2 节（预期结果）必须在运行开始**之前**填写。
3. 结果使用固定词汇：`full pass`（完全通过）/ `partial (P1–P3)`
   （部分通过）/ `failure`（失败）/ `access blocked — not tested`
   （接入受阻——未测试）/ `not verified`（未验证）。
4. **接入受阻 ≠ 能力为零。** 如果验证、地区或套餐限制导致运行
   中止，记录中止的位置，并将剩余能力标记为未测试。
5. 证据是强制性的：每个分数都要链接到 `evidence/` 中的文件。
   提交前对截图中的个人数据进行脱敏处理。
6. 仅使用测试账号：绝不要提交真实邮件内容、真实联系人数据或
   凭据。
