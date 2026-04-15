# Engineering Problem Gate 邮件模板

## 邮件标题建议

可选标题 1：

`[内部推广] Engineering Problem Gate：让 Cursor 先收敛问题，再进入执行`

可选标题 2：

`[AI 使用规范] 新增 Cursor Skill：Engineering Problem Gate`

可选标题 3：

`[试运行] Engineering Problem Gate：减少 AI 使用中的盲目推进`

## 邮件正文模板

各位同事，

为了提升大家在使用 Cursor 时的输出质量和执行效率，我们整理了一套企业内项目级 Skill：`engineering-problem-gate`。

这套 Skill 的目标不是增加流程负担，而是解决一个常见问题：很多任务在目标、约束、成功标准、项目背景还没说清楚时，就直接进入方案或实现，导致 AI 输出发散、落地性差、反复返工。

`engineering-problem-gate` 的核心作用是：

- 先收敛问题，而不是直接进入方案或代码
- 先补项目背景、资源和可访问资料
- 用统一模板定义当前任务
- 用第一性原理做结构化分解
- 再决定是否进入方案、实现，或沉淀为 skill / harness

适用角色包括：

- 数字工程师
- 模拟工程师
- Layout 工程师
- 软件工程师
- 算法工程师
- 测试工程师
- 市场产品经理
- 现场支持工程师

建议大家在以下场景优先使用：

- 新项目启动
- 新任务进入
- 需求不清楚
- 方案前置讨论
- 想让 Cursor 帮忙，但又担心它直接跑偏

## 如何安装

推荐方式：

1. 将 `engineering-problem-gate` 目录放到项目的 `.cursor/skills/`
2. 如果只是个人先试用，也可以放到 `~/.cursor/skills/`

## 如何使用

最简单的用法是，在开始做方案、代码、skill 或 harness 之前，先对 Cursor 说：

`请先用 engineering-problem-gate 帮我梳理这个任务，不要直接进入方案或实现。`

## 附带内容

本包内包含：

- `SKILL.md`：主流程
- `project-intake.md`：项目启动前背景采集
- `role-fields.md`：不同角色扩展字段
- `decomposition-patterns.md`：结构化分解与第一性原理参考

## 试运行建议

建议大家先在以下类型任务中试用：

- 问题比较模糊的任务
- 跨角色协作任务
- 需要和项目背景强绑定的任务
- 想进一步沉淀为 skill / harness 的任务

欢迎大家在试用后反馈：

- 哪些字段最有帮助
- 哪些步骤太重
- 哪些角色字段还需要补充
- 哪些地方最值得下沉为正式 harness

谢谢。

## 短版邮件模板

各位同事，

我们新增了一套 Cursor Skill：`engineering-problem-gate`，用于在进入方案、实现、skill、harness 之前，先帮助大家收敛问题、补齐项目背景、做结构化分解，减少 AI 使用中的盲目推进。

建议在新任务、模糊需求、方案前置讨论时优先使用。

最简单的用法是：

`请先用 engineering-problem-gate 帮我梳理这个任务，不要直接进入方案或实现。`

安装方式：

- 项目级：放到 `.cursor/skills/engineering-problem-gate/`
- 个人级：放到 `~/.cursor/skills/engineering-problem-gate/`

欢迎试用并反馈。
