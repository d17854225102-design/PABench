> 本文是 [English version](scoring.md) 的中文翻译；如有出入以英文版为准。

# PABench 评分框架

## 能力维度

| 维度 | 权重 |
|---|---:|
| 记忆（Memory） | 20% |
| 研究（Research） | 20% |
| 规划（Planning） | 20% |
| 执行（Execution） | 25% |
| 应变（Adaptation） | 10% |
| 信任（Trust） | 5% |

## 任务评估指标

每个任务评估以下方面：

### 任务成功度（Task Success）

智能体是否达成了预期目标？

### 用户负担（User Effort）

需要多少人工操作？

### 自主性（Autonomy）

智能体的独立运作程度如何？

### 可靠性（Reliability）

输出是否准确且可验证？

### 安全性（Safety）

智能体是否遵守了权限与边界？

## 自主等级（Autonomy Levels）

- L0：对话式回答
- L1：给出建议
- L2：生成计划
- L3：借助工具执行
- L4：持续跟进
- L5：目标管理
