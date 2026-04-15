# Engineering Problem Gate

`engineering-problem-gate` 是一个面向企业工程团队的 Cursor Skill。  
它的目标是让工程师在使用 Cursor 或 agent 时，先补齐项目背景、先定义问题、先做结构化分解，再决定是否进入方案、实现，或沉淀为 `skill / harness`。

## 适用场景

适合以下场景优先使用：

- 新项目启动
- 新任务进入
- 模糊需求澄清
- 方案前置讨论
- 跨角色协作
- 准备沉淀为 `skill / harness` 的任务

## 核心价值

- 减少“问题没想清楚就开做”的盲目性
- 让 AI 输出更贴近真实项目背景
- 把任务拆到 AI 更容易稳定执行的颗粒度
- 为后续企业内 `skill / harness` 沉淀提供统一入口

## 目录说明

```text
engineering-problem-gate/
├── README.md
├── SKILL.md
├── project-intake.md
├── role-fields.md
├── decomposition-patterns.md
├── rollout-intro.md
├── installation-guide.md
├── email-template.md
├── presentation-script.md
└── release-package.md
```

## 文件用途

- `SKILL.md`
  - 主 skill 文件
  - 定义问题门禁、阶段判断、结构化分解、沉淀判断的主流程

- `project-intake.md`
  - 项目启动前背景采集模板
  - 用于收集项目目标、资源、约束、成功标准、AI 可用范围

- `role-fields.md`
  - 不同角色的扩展字段
  - 包括数字、模拟、layout、软件、算法、测试、市场产品、现场支持

- `decomposition-patterns.md`
  - 第一性原理与结构化分解参考
  - 定义什么叫 AI 易实现颗粒度，并提供多角色拆分示例

- `rollout-intro.md`
  - 对内推广简介
  - 适合知识库、首页说明、短介绍

- `installation-guide.md`
  - 打包、安装、推广方式说明
  - 包含项目级安装、个人级安装、压缩包分发建议

- `email-template.md`
  - 公司内邮件模板
  - 包含完整版和短版通知

- `presentation-script.md`
  - 宣讲稿
  - 包含 5 分钟介绍和 1 分钟极简版

- `release-package.md`
  - 发布清单与版本说明模板
  - 用于后续版本化发布和试点推广

## 推荐使用顺序

如果是第一次在项目中使用，建议按这个顺序：

1. 先看 `project-intake.md`
   - 补齐项目背景、资源和边界
2. 再用 `SKILL.md`
   - 定义当前问题、判断阶段、决定是否放行
3. 需要细拆任务时看 `decomposition-patterns.md`
   - 把问题拆到 AI 易执行的颗粒度
4. 按角色补充时看 `role-fields.md`
   - 补齐对应岗位的扩展字段

如果是公司内推广，建议按这个顺序：

1. 用 `rollout-intro.md` 做简介
2. 用 `presentation-script.md` 做宣讲
3. 用 `installation-guide.md` 指导安装
4. 用 `email-template.md` 发通知
5. 用 `release-package.md` 做版本管理

## 最简单的使用方式

在开始做方案、代码、skill、harness 之前，先对 Cursor 说：

```text
请先用 engineering-problem-gate 帮我梳理这个任务，不要直接进入方案或实现。
```

## 推荐安装方式

项目级安装：

```text
.cursor/skills/engineering-problem-gate/
```

个人级安装：

```text
~/.cursor/skills/engineering-problem-gate/
```

## 推广建议

建议先试点，再推广：

1. 先选少量角色试用
2. 收集高频问题与反馈
3. 再按项目级方式推广
4. 最后再考虑把稳定规则下沉为正式 `harness`

## 一句话介绍

`engineering-problem-gate` 是一个“先收敛问题、再分解任务、最后才进入执行”的企业级 Cursor Skill，用来减少工程师使用 AI 时的盲目推进，让输出更贴项目、任务更可执行。
