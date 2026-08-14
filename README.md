# XHS Khazix Pipeline — 小红书长文写作标准化工作流

![License](https://img.shields.io/badge/license-MIT-blue)

A standardized 10-step workflow skill for writing long-form Xiaohongshu (RED) articles in the Khazix style, with a user confirmation checkpoint at every step. / 一个标准化的 10 步小红书长文写作工作流 Skill，按卡兹克（Khazix）风格写作，每一步都有用户确认节点。

---

## 中文说明

### 这是什么

一个 AI Agent Skill，把「写一篇小红书长文」从一次性指令变成一条标准流水线：选题 → 搜素材 → 定立意 → 撰稿 → 去 AI 味 → 敏感词检验 → 定小标题 → 定大标题 → 写摘要，全程 10 步，每步做完必须停下来等用户确认才能继续。

### 核心特性

- 10 步标准化流水线，覆盖一篇长文从 0 到 1 的全过程
- 4 个用户确认节点全部使用可视化按钮交互（AskUserQuestion），点击即可，不用打字
- Step 4 撰稿时自动调用 khazix-writer 加载卡兹克风格规则
- 自动执行去 AI 味处理和敏感词扫描
- 大标题 5 选 1、小标题 4 选 1、摘要确认，全部走可视化选择

### 工作流总览

```text
用户提供选题
    ↓
Step 1 — 接收选题
    ↓
Step 2 — 搜索素材（多源交叉验证）
    ↓
Step 3 — 阐述立意 → 按钮选择
    ↓
Step 4 — 自动搜索 + 撰稿（调用 khazix-writer）
    ↓
Step 5 — 去 AI 味（自动）
    ↓
Step 6 — 敏感词检验（自动）
    ↓
Step 7 — 小标题提案 → 按钮确认
    ↓
Step 8 — 大标题提案（5 选 1）→ 按钮选择
    ↓
Step 9 — 摘要写作 → 按钮确认
    ↓
Step 10 — 摘要插入文档开头
    ↓
完成
```

### 安装

```bash
# 安装到 .agents/skills 目录（跨 Agent 平台生效）
mkdir -p ~/.agents/skills/xhs-khazix-pipeline
cp SKILL.md ~/.agents/skills/xhs-khazix-pipeline/
```

或在 TRAE 设置 > 技能与命令中导入本目录。

### 依赖

- 需要 `khazix-writer` Skill（卡兹克风格写作规则）
- 需要支持 `AskUserQuestion` 工具的 Agent 环境
- 默认输出路径为本机 iCloud 的「小红书长文系列」文件夹，可按需修改 SKILL.md 中的路径配置

### 许可证

[MIT](./LICENSE)

---

## English

### What is this

An AI Agent skill that turns "write a long-form Xiaohongshu (RED) article" into a standard pipeline: topic → research → angle → draft → de-AI polish → sensitive-word check → subtitles → headline → summary. Each of the 10 steps pauses for user confirmation before moving on.

### Key Features

- 10-step standardized pipeline covering a full article from 0 to 1
- 4 user checkpoints use visual button interactions (`AskUserQuestion`) — click to choose, no typing
- Step 4 automatically loads the `khazix-writer` skill for Khazix-style writing rules
- Automatic de-AI polish and sensitive-word scanning
- Headline pick-1-of-5, subtitle pick-1-of-4, summary confirmation — all visual

### Installation

```bash
mkdir -p ~/.agents/skills/xhs-khazix-pipeline
cp SKILL.md ~/.agents/skills/xhs-khazix-pipeline/
```

Or import the directory via your agent's skill manager (e.g. TRAE Settings > Skills).

### Dependencies

- Requires the `khazix-writer` skill (Khazix-style writing rules)
- Requires an agent environment that supports the `AskUserQuestion` tool
- Default output path is the local iCloud folder "小红书长文系列"; adjust the path in SKILL.md if needed

### License

[MIT](./LICENSE)
