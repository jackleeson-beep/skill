# Engineering Problem Gate v0.1

## 发布说明

`engineering-problem-gate` 是一套面向企业工程团队的 Cursor Skill。  
它的目标是让工程师在使用 AI 时，先补齐项目背景、先定义问题、先做结构化分解，再决定是否进入方案、实现，或沉淀为 `skill / harness`。

这套 Skill 主要用于减少以下问题：

- 问题没想清楚就直接进入执行
- 项目背景和资源没有先给 AI
- 任务颗粒太大，AI 很难稳定完成
- 不同角色使用 AI 时上下文和方法不一致

## v0.1 包含内容

- `SKILL.md`
  - 主流程
  - 定义问题门禁、阶段判断、结构化分解、沉淀判断

- `project-intake.md`
  - 项目启动前背景采集模板

- `role-fields.md`
  - 多角色扩展字段

- `decomposition-patterns.md`
  - 第一性原理与结构化分解参考

- `README.md`
  - 首页说明与使用顺序

- `rollout-intro.md`
  - 对内推广简介

- `installation-guide.md`
  - 打包、安装与推广方式说明

- `email-template.md`
  - 邮件模板

- `presentation-script.md`
  - 内部宣讲稿

- `release-package.md`
  - 发布清单与版本管理模板

## 适用范围

适用于以下角色：

- 数字工程师
- 模拟工程师
- Layout 工程师
- 软件工程师
- 算法工程师
- 测试工程师
- 市场产品经理
- 现场支持工程师

适合以下场景优先试用：

- 新项目启动
- 新任务进入
- 模糊需求澄清
- 方案前置讨论
- 跨角色协作
- 准备沉淀为 `skill / harness` 的任务

## 推荐使用方式

最简单的用法是，在开始做方案、代码、skill、harness 之前，先对 Cursor 说：

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

## 试点建议

建议先在以下类型任务中试用：

- 问题比较模糊的任务
- 需要和项目背景强绑定的任务
- 跨角色协作任务
- 希望后续沉淀为 `skill / harness` 的任务

建议先小范围试点，再逐步推广到项目级使用。

## 压缩包

本次发布压缩包建议文件名：

```text
engineering-problem-gate-v0.1.zip
```

## 一句话介绍

`engineering-problem-gate` 是一个“先收敛问题、再分解任务、最后才进入执行”的企业级 Cursor Skill，用来减少工程师使用 AI 时的盲目推进，让输出更贴项目、任务更可执行。
