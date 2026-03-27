---
name: learning-summary
description: Organize study notes into a clear summary with key points, open questions, and next actions. Use when the user wants to整理学习内容, 总结笔记, 提炼重点, or turn rough notes into a structured summary.
---

# Learning Summary

## Instructions
When the user provides learning materials, notes, or scattered ideas:

1. Identify the main topic in one sentence.
2. Extract the most important concepts.
3. Separate confirmed understanding from open questions.
4. End with practical next steps for continued learning.

## Output Format
Use this structure by default:

```markdown
## 主题
[一句话概括]

## 重点
- [关键点 1]
- [关键点 2]
- [关键点 3]

## 我还没完全弄懂的地方
- [问题 1]
- [问题 2]

## 下一步怎么学
- [可执行动作 1]
- [可执行动作 2]
```

## Guidance
- Prefer short, concrete wording over long explanations.
- If the notes are incomplete, say what is missing instead of inventing details.
- Preserve domain terms when they matter.
- Rewrite messy notes into readable Chinese.

## Example
Input:
"今天学了 skill。它像给 AI 的说明书。里面有 name 和 description。description 要写清楚做什么、什么时候用。正文里可以写步骤、模板、例子。"

Output:

```markdown
## 主题
Skill 是给 AI 的可复用任务说明。

## 重点
- Skill 通常用来约束某类任务的处理方式。
- `name` 是技能标识，`description` 决定何时触发。
- 正文可以包含步骤、模板和示例。

## 我还没完全弄懂的地方
- Skill 什么时候会被自动调用？
- 项目级 Skill 和个人 Skill 应该怎么选择？

## 下一步怎么学
- 自己写一个最小的 `SKILL.md`。
- 测试用一段凌乱笔记让 AI 按模板整理。
```
