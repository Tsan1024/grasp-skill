# Grasp · 抓住主脉

[English](README.md) | 简体中文

快速理解陌生领域：先看清全貌与关键关系，再通过少量追问检验理解。

## 使用示例

```text
$grasp 帮我用十分钟理解 Agent Memory。我是小白，先抓主脉。
```

```text
$grasp Help me understand linguistics from scratch. Start with the big picture.
```

```text
$grasp 我刚读完数据库的介绍，逐个问我几个核心问题，检查是否理解。
```

## 你会得到什么

- 一句话定位：这个领域是什么，为什么存在。
- 一个具体案例：用熟悉的场景串联概念。
- 整体地图：主要部分以及它们如何关联。
- 理解主线：主要路线为什么出现，各有什么边界。
- 少数核心概念或矛盾，以及可以暂缓的细节。
- 通常 3–5 轮、每次一题的理解检验：定位、因果关系、简单场景迁移。

默认在对话里交付；需要保存时生成 Markdown，图解或交互确有帮助时按需生成 HTML。检验可以跳过，参考解释在回答后给出。

Grasp 帮助建立初步整体理解，不承诺通过一篇导览或几道题达到精通。

## 适用范围

适合初次接触研究领域、技术系统、复杂产品、人文思想或行业。对实践技能，它适合先了解子技能和反馈结构；具体操作、专业判断和熟练程度仍需要专项学习与实践。

## 联网策略

稳定基础知识可以直接解释。用户要求调研、最新信息、查阅具体来源，或关键事实不确定时，使用环境提供的检索能力查证。没有联网能力时，明确未核实的信息。模型更新频率不能保证具体事实的新鲜度。

## 安装

### 直接告诉 Agent

将下面这段话发给能够访问 GitHub 并安装本地 Skill 的 Agent：

```text
请从 https://github.com/Tsan1024/grasp-skill 安装 grasp，
安装到当前 Agent 的个人范围。使用它支持的 Skill 安装器或目录，
并确认安装后可以发现 grasp。
```

仅在一次对话里读取链接，不代表持久安装。没有文件操作或 Skill 安装能力的聊天界面，可能只能在当前对话中参考这些指令。

### 使用 Skills CLI

需要 Node.js/npm 和 Git。安装到个人范围，并选择目标 Agent：

```bash
npx skills add Tsan1024/grasp-skill --skill grasp -g
```

也可以明确指定目标：

```bash
# Codex
npx skills add Tsan1024/grasp-skill --skill grasp -g -a codex

# Claude Code
npx skills add Tsan1024/grasp-skill --skill grasp -g -a claude-code
```

去掉 `-g` 为项目级安装；自动化场景可加 `-y` 接受安装提示。只查看仓库中的 Skill 而不安装：

```bash
npx skills add Tsan1024/grasp-skill --list
```

安装器负责处理不同 Agent 的目录。详见[安装器官方文档](https://github.com/vercel-labs/skills#install-a-skill)。

### 兼容性与本地验证

2026 年 9 月 5 日，在 macOS、Node.js 25.8.2、Skills CLI 1.5.23 上验证：

| 目标 | 已验证的安装行为 |
|---|---|
| Codex | 项目级和个人级安装成功，安装内容与仓库一致。 |
| Claude Code | 项目级安装生成了可访问 Skill 的链接。 |
| Cursor、Gemini CLI、GitHub Copilot、OpenCode | 安装器选用共享的项目 Skill 目录，并写入一致的文件。 |
| Windsurf | 安装器列有此目标，但本次多目标验证未生成预期目录，安装仍未验证。 |

以上是文件安装验证，不代表逐个客户端完成了实际加载或教学效果测试。除 Codex 外，其他目标的个人级安装尚未测试。[安装器支持列表](https://github.com/vercel-labs/skills#supported-agents)中的其他 Agent 也可能适配，但本项目尚未验证。

Grasp 使用基础 `SKILL.md` 指令，附可选的 Codex UI 元数据，不依赖额外运行服务或其他 Skill。

### 手动备用方式

<details>
<summary>将 Skill 复制到 Agent 的技能目录</summary>

克隆仓库后，将 `grasp/` 文件夹复制到客户端支持的个人或项目 Skill 目录。例如手动安装到 Codex 可使用 `~/.codex/skills/`，配置了 `CODEX_HOME` 时则使用其下的 `skills/`：

```bash
git clone https://github.com/Tsan1024/grasp-skill.git
mkdir -p ~/.codex/skills
cp -R grasp-skill/grasp ~/.codex/skills/
```

复制前确认目标没有已定制的 `grasp`，避免覆盖。其他客户端的目录不同，请遵循其文档。

</details>

## 调用 Grasp

Codex 使用 `$grasp`，[Claude Code](https://code.claude.com/docs/en/skills) 使用 `/grasp`。其他客户端可通过 Skill 选择器，或直接说“用 grasp 帮我理解数据库”。显式调用语法由客户端决定。

若未发现已安装的 Skill，重新加载 Skills 或新开会话。回答语言跟随用户。

## 文件结构

```text
grasp/
├── SKILL.md
└── agents/openai.yaml
```

逐题追问的交互方式受到 `grill-me` 启发；这里聚焦宏观理解检验，控制轮数，并在作答后提供反馈。
