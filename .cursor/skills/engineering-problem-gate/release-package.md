# Engineering Problem Gate 发布清单

## 发布目标

本文件用于标准化 `engineering-problem-gate` 的公司内发布。  
适用于首次发布、版本升级、小范围试点、项目级推广。

## 建议版本命名

推荐使用简单版本号：

- `v0.1`：初版试点
- `v0.2`：补充角色字段或案例
- `v0.3`：补充流程门禁或结构化分解
- `v1.0`：形成稳定对外推广版本

## 每次发布建议包含的文件

```text
engineering-problem-gate/
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

## 打包前检查清单

- [ ] `SKILL.md` 已更新到最新版本
- [ ] `project-intake.md` 与当前项目推广方式一致
- [ ] `role-fields.md` 包含当前希望覆盖的角色
- [ ] `decomposition-patterns.md` 有最新示例
- [ ] `installation-guide.md` 中安装路径正确
- [ ] `email-template.md` 中联系人/渠道信息已替换
- [ ] `presentation-script.md` 中宣讲内容与当前版本一致
- [ ] 目录内没有无关临时文件

## 推荐打包文件名

```text
engineering-problem-gate-v0.1.zip
engineering-problem-gate-v0.2.zip
engineering-problem-gate-v1.0.zip
```

## 发布说明模板

每次发布时，建议同时附一段简短的 release note：

```markdown
## Engineering Problem Gate [版本号]

### 本次更新
- [更新点 1]
- [更新点 2]
- [更新点 3]

### 适用范围
- [适用团队或项目]

### 安装方式
- 项目级：复制到 `.cursor/skills/engineering-problem-gate/`
- 个人级：复制到 `~/.cursor/skills/engineering-problem-gate/`

### 建议优先试用场景
- [场景 1]
- [场景 2]
- [场景 3]
```

## 首次发布建议文案

```markdown
## Engineering Problem Gate v0.1

### 本次更新
- 新增企业内问题定义门禁主流程
- 新增项目启动背景采集模板
- 新增多角色字段扩展
- 新增第一性原理与结构化分解参考
- 新增推广介绍、安装说明和邮件模板

### 适用范围
- 适合试点团队与重点项目先使用

### 安装方式
- 项目级：复制到 `.cursor/skills/engineering-problem-gate/`
- 个人级：复制到 `~/.cursor/skills/engineering-problem-gate/`

### 建议优先试用场景
- 模糊任务
- 新项目启动
- 跨角色协作
- 准备沉淀为 skill / harness 的任务
```

## 发布渠道建议

建议至少覆盖以下 3 个渠道：

1. 邮件
2. 项目群 / IM 群
3. 内部知识库 / Wiki

如果希望正式推广，再加：

4. 项目启动会
5. 团队周会 / 月会

## 建议发布节奏

### 第一次发布

- 先发试点版
- 明确适用对象和试用范围
- 不强调“全面强制”，先收集反馈

### 第二次发布

- 根据反馈补充角色字段和示例
- 优化安装说明和最小使用方式

### 稳定版发布

- 固定最小门禁字段
- 明确项目级安装为默认方式
- 开始考虑将稳定规则下沉为 harness

## 反馈收集建议

每次发布后，建议至少收集这 4 类反馈：

- 哪些步骤最有帮助
- 哪些步骤太重
- 哪些角色字段缺失
- 哪些场景最容易体现价值

## 推荐负责人分工

如果正式在公司内推广，建议至少明确：

- 内容负责人：维护 skill 内容
- 试点负责人：收集团队试用反馈
- 发布负责人：统一版本和分发
- 方法负责人：判断哪些规则值得下沉为 harness
