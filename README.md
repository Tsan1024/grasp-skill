# Grasp

English | [简体中文](README.zh-CN.md)

Build a clear mental map of an unfamiliar field, then check your understanding through focused questions.

## Usage examples

```text
$grasp Help me understand Agent Memory in ten minutes. I'm a beginner—start with the big picture.
```

```text
$grasp Help me understand linguistics from scratch. Start with the big picture.
```

```text
$grasp I just read an introduction to databases. Ask me a few core questions, one at a time, to check my understanding.
```

## What you get

- A plain-language definition: what the field is and why it exists.
- A concrete example that connects unfamiliar concepts to a familiar situation.
- A mental map of the main parts and how they relate.
- An explanation of why major approaches emerged and where their limits lie.
- A few core concepts or trade-offs, with details you can leave for later.
- An understanding check, typically 3–5 exchanges with one question at a time, covering purpose, causal relationships, and application to a simple new situation.

The guide is delivered in the conversation by default. Markdown is available when you want to save it; HTML can be generated when diagrams or interaction would help. You can skip the check. Feedback and reference explanations come after your answers.

Grasp helps you build an initial understanding. A guide and a few questions do not establish expertise.

## When to use it

Use Grasp when first approaching a research field, technical system, complex product, humanities topic, or industry. For practical skills, it helps you understand the component skills and feedback loops; specific procedures, professional judgment, and proficiency still require focused study and practice.

## Browsing and sources

Stable fundamentals can be explained directly. When you request research, current information, or a specific source—or when key facts are uncertain—Grasp uses the search capabilities available in your environment to verify them. If browsing is unavailable, it identifies what remains unverified. Model release frequency does not guarantee that a particular fact is up to date.

## Installation

### Ask your agent

Paste this into an agent that can access GitHub and install local skills:

```text
Install the grasp skill from https://github.com/Tsan1024/grasp-skill
for this agent at the user level. Use its supported skill installer
or skill directory, then verify that grasp is discoverable.
```

Reading the link for one conversation is not persistent installation. A chat interface without filesystem or skill-installation capabilities may only use the instructions in the current conversation.

### Use the Skills CLI

Requires Node.js/npm and Git. Install at the user level and select your agent:

```bash
npx skills add Tsan1024/grasp-skill --skill grasp -g
```

For an explicit target:

```bash
# Codex
npx skills add Tsan1024/grasp-skill --skill grasp -g -a codex

# Claude Code
npx skills add Tsan1024/grasp-skill --skill grasp -g -a claude-code
```

Omit `-g` for a project installation. Add `-y` to accept installer prompts in automation. Preview discovery without installing:

```bash
npx skills add Tsan1024/grasp-skill --list
```

The CLI handles agent-specific paths. See the [official installer documentation](https://github.com/vercel-labs/skills#install-a-skill).

### Compatibility and local verification

Checked on macOS with Node.js 25.8.2 and Skills CLI 1.5.23 on September 5, 2026:

| Target | Verified installation behavior |
|---|---|
| Codex | Project installation and user-level installation succeeded; installed content matched the repository. |
| Claude Code | Project installation created a working link to the skill. |
| Cursor, Gemini CLI, GitHub Copilot, OpenCode | The installer selected the shared project skill directory and wrote the matching skill files. |
| Windsurf | Listed by the installer, but our multi-target check did not create its expected directory; installation remains unverified. |

These are file-installation checks, not end-to-end tests of loading or teaching quality in each client. User-level installation for targets other than Codex has not been tested. Other agents listed in the [installer's compatibility table](https://github.com/vercel-labs/skills#supported-agents) may also work, but are not verified here.

Grasp uses basic `SKILL.md` instructions with optional Codex UI metadata. It requires no additional runtime services or other skills.

### Manual fallback

<details>
<summary>Copy the skill into your agent's skill directory</summary>

Clone the repository, then copy the `grasp/` folder into your client's supported personal or project skill directory. For example, a manual Codex installation can use `~/.codex/skills/` (or `$CODEX_HOME/skills/` when configured):

```bash
git clone https://github.com/Tsan1024/grasp-skill.git
mkdir -p ~/.codex/skills
cp -R grasp-skill/grasp ~/.codex/skills/
```

Check that the destination does not already contain a customized `grasp` before copying. Other clients use different directories; follow their documentation.

</details>

## Invoke Grasp

Use `$grasp` in Codex or `/grasp` in [Claude Code](https://code.claude.com/docs/en/skills). In other clients, use their skill selector or ask naturally: “Use the grasp skill to help me understand databases.” Explicit invocation syntax varies by client.

Reload skills or start a new session if the installed skill is not discovered. Responses follow your language.

## File structure

```text
grasp/
├── SKILL.md
└── agents/openai.yaml
```

The one-question-at-a-time interaction was inspired by `grill-me`. Grasp adapts it to a short check of big-picture understanding, with feedback after each answer.
