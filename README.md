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

Send this to your agent:

```text
Install the grasp skill from https://github.com/Tsan1024/grasp-skill
for this agent at the user level, then verify that it is discoverable.
```

Your agent needs access to GitHub and the ability to install local skills.

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
