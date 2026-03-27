---
name: generating-skill-definitions
description: 根据用户需求起草或迭代符合 Agent Skills 规范的 SKILL.md（含 name/description/正文结构）。适用于用户说「做一个 skill」「生成 skill」「把流程固化成 skill」「评审 skill 是否合格」「skill 怎么写」等场景。中英混合描述均可；输出默认中文说明 + 可复制粘贴的 YAML 与 Markdown 正文。
---

# 生成与迭代 Skill 定义

本 skill 将 [Datawhale agent-skills-with-anthropic 教程](https://github.com/datawhalechina/agent-skills-with-anthropic) 中的实践要点，整理为**可执行的生成流程**。目标是：产出的 skill **易触发、易维护、token 友好**。

## 与 Tools / MCP / Subagents 的分工（先对齐预期）

- **Skills**：封装**可重复的工作流**与领域知识（本 skill 专注于此）。
- **Tools**：底层能力（读写文件、执行命令等）；skill **不替代**工具，而是教 agent **何时、如何**用工具完成流程。
- **MCP**：连接外部系统与数据；skill 可说明「在拿到 MCP 数据后如何加工」，但连接本身由 MCP 承担。
- **Subagents**：并行子任务、隔离上下文；skill 适合描述**主流程**；需要并行时再由编排层拆分子代理。

## 生成前：用 5 个问题收敛范围（必做）

在写任何 `SKILL.md` 之前，先确认（信息不足则追问用户）：

1. **单一职责**：这个 skill 只做一件事还是多件事？若多件事，应拆成多个 skill。
2. **触发场景**：用户通常怎么说才会需要它？列出 **关键词/短语**（写入 `description`）。
3. **输入**：用户会提供什么（文本、路径、日志、代码、表格）？
4. **输出**：固定结构是什么（标题、表格、检查清单）？
5. **自由度**：任务是否脆弱、必须严格按脚本顺序？（决定高/中/低自由度，见下）

## YAML 元数据规则（与 Cursor / Agent Skills 一致）

### `name`

- 小写字母、数字、连字符；**建议动名词**（动词 + `-ing`），如 `analyzing-time-series`、`generating-practice-questions`。
- **与文件夹名一致**；尽量短；避免含糊的 `helper`、`utils`。

### `description`（最关键）

好 `description` 必须同时包含：

- **做什么**（能力）
- **何时用**（触发场景 + **关键词**）
- 如有必要：**输入/输出/使用条件**的简短提示

长度注意：常见上限约 **1024 字符**（以你当前环境文档为准）。

技巧：把「用户会说的词」写进 description，可显著提高触发率。

### 可选字段（按需）

- `license`、`compatibility`、`metadata` 等按规范添加；不要为凑字段而写。

## 正文结构（建议默认骨架）

1. **Instructions**：分步、可执行；复杂流程用编号步骤。
2. **Input**：支持的格式与提取要点（若适用）。
3. **Output Format**：固定模板（Markdown 代码块给出可复制模板）。
4. **Examples**：至少 1 个「输入片段 → 期望输出结构」。
5. **Constraints**：禁止编造、不确定项单独列出、术语表（若领域强约束）。
6. **渐进式披露**：`SKILL.md` 保持精简（建议 **≤500 行**）；长规范放 `references/`，**只从 SKILL.md 做一级链接**。

## 可选目录（按需创建）

| 目录 | 用途 |
|------|------|
| `scripts/` | 需确定性、重复执行的代码；在 SKILL.md 中写明是**执行**还是**仅阅读**；脚本需依赖说明与错误信息。 |
| `references/` | 长文档、API、政策；单文件保持主题单一；**超过约 100 行**建议在文件顶部加目录。 |
| `assets/` | 输出模板、图片、schema、样例数据等静态资源。 |

## 自由度等级（写入正文，便于维护）

| 等级 | 何时用 | 写法 |
|------|--------|------|
| 高 | 多种合法路径、强依赖上下文 | 原则 + 检查清单 |
| 中 | 有首选模式、允许变体 | 伪代码 / 模式 + 注意点 |
| 低 | 顺序敏感、易错、需一致结果 | 明确脚本与固定步骤 |

## 交付物格式（本 skill 的输出约定）

当用户要求「生成 skill」时，默认输出三部分：

1. **设计摘要**：一句话职责、触发词、为何不分拆/要分拆。
2. **目录建议**：是否只需 `SKILL.md`，或需要 `references/` / `scripts/` / `assets/`。
3. **完整可粘贴内容**：从 `---` 开始的 **frontmatter + Markdown 正文**。

## 生成后自检清单（必跑）

- [ ] `name` 与建议文件夹名一致，且为动名词风格。
- [ ] `description` 含 **做什么 + 何时用 + 关键词**。
- [ ] 正文有 **Output Format** 与至少 **一个 Example**。
- [ ] 无过深嵌套引用；长内容已计划放 `references/`。
- [ ] 范围是否过大？过大则建议拆 skill 或拆 reference 文件。

## 参考来源

- 中文整理与案例：[datawhalechina/agent-skills-with-anthropic](https://github.com/datawhalechina/agent-skills-with-anthropic)
- 开放标准总览：[Agent Skills 规范与生态](https://agentskills.io/)（与 Cursor 等兼容实现并存）
