# Skill 学习

English version: [README.en.md](README.en.md)

这个仓库用于整理和沉淀面向 Cursor / Agent 的 `skill`、`harness` 和相关方法论实践。  
重点不是单纯收集提示词，而是把工程团队在真实项目中使用 AI 时的流程、约束、分解方式和推广材料沉淀成可复用资产。

## 当前内容

目前仓库里重点包含以下 skill：

- `engineering-problem-gate`
  - 企业级问题定义门禁
  - 用于在进入方案、实现或沉淀为 `skill / harness` 之前，先补齐项目背景、定义问题、做结构化分解

- `framing-problems-before-building`
  - 通用问题收敛 skill
  - 用于在需求模糊、问题没定义清楚时，先收敛目标、约束、成功标准与未知项

- `generating-skill-definitions`
  - Skill 生成与迭代参考
  - 用于起草或改进符合 Agent Skills 规范的 `SKILL.md`

- `learning-summary`
  - 学习内容整理 skill
  - 用于把零散笔记和材料整理成结构化总结

## 推荐从哪里开始

如果你是第一次看这个仓库，建议从这里开始：

1. 先看 `.cursor/skills/engineering-problem-gate/README.md`
2. 再看 `.cursor/skills/engineering-problem-gate/SKILL.md`
3. 如果要在项目里实操，再看：
   - `.cursor/skills/engineering-problem-gate/project-intake.md`
   - `.cursor/skills/engineering-problem-gate/decomposition-patterns.md`

## 这个仓库适合谁

适合以下类型的使用者：

- 想把 AI 使用方式纳入项目流程的工程团队
- 想把模糊问题先收敛再执行的人
- 想沉淀企业内 `skill / harness` 的团队
- 在做 Cursor / Agent 落地实践的人

## 使用方式

最简单的方式，是把需要的 skill 目录放进项目的：

```text
.cursor/skills/
```

或者个人目录：

```text
~/.cursor/skills/
```

## 仓库目标

这个仓库的目标不是只保存文档，而是逐步形成一套更可执行的 AI 工作框架，包括：

- 项目背景采集
- 问题定义门禁
- 第一性原理分析
- 结构化任务分解
- `skill / harness` 沉淀
- 推广、发布与团队落地材料

## 当前重点推荐

如果你只想先试一个内容，建议先试：

```text
engineering-problem-gate
```

因为它最接近真实项目使用场景，也最适合作为团队内推广的统一入口。
