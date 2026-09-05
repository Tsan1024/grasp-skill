# Grasp · 抓住主脉

Build a clear mental map of an unfamiliar field, then check your understanding through focused questions.

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

## 安装到 Codex

克隆本仓库，然后将 `grasp/` 文件夹复制到个人 Skills 目录。默认位置为 `~/.codex/skills/`；设置了 `CODEX_HOME` 时使用其下的 `skills/`。

```bash
git clone https://github.com/Tsan1024/grasp-skill.git
mkdir -p ~/.codex/skills
cp -R grasp-skill/grasp ~/.codex/skills/
```

复制前确认目标目录不存在，以免覆盖已有定制版本。让客户端重新加载 Skills；若当前会话未发现它，可新开会话后使用 `$grasp`。

其他支持 `SKILL.md` 的客户端可按各自的安装方式使用 `grasp/`。本仓库包含 Codex UI 元数据，不依赖额外服务、脚本或其他 Skill。回答语言跟随用户。

## 文件结构

```text
grasp/
├── SKILL.md
└── agents/openai.yaml
```

逐题追问的交互方式受到 `grill-me` 启发；这里聚焦宏观理解检验，控制轮数，并在作答后提供反馈。
