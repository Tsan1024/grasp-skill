# Grasp

English | [简体中文](README.zh-CN.md)

Build a clear mental map of an unfamiliar field, then check your understanding through focused questions.

## Start here

After installation, name the topic and say you are a beginner:

```text
$grasp Help me understand Agent Memory. I'm a beginner—start with the big picture.
```

No special configuration is needed. With no depth specified, Grasp starts with a short overview, then offers a core question to check understanding. Examples use Codex's `$grasp`; in Claude Code use `/grasp`. See [installation](#installation) if you have not installed it yet.

## Choose your depth

These are natural-language requests, not fixed command modes. Times describe approximate reading or study effort, not generation time or a promise of mastery. If you need the answer delivered within a deadline, say that separately.

| What you need | What to ask for | What changes |
|---|---|---|
| A first look | A 5-minute version | The core problem, a small map, one example, and a few key ideas |
| A quick overview (default) | A 5–15-minute version | Main relationships, essential mechanisms, and boundaries |
| More explanation | A 30-minute version | More examples and comparisons of why different approaches exist |
| A systematic map | About 1–3 hours of study material | Development, representative sources, assumptions, disagreements, and selective deeper reading |

Copy any of these and replace the topic:

```text
$grasp Give me a 5-minute introduction to Agent Memory. Keep only the main ideas; skip the understanding check for now.
```

```text
$grasp Give me a 30-minute guide to Agent Memory. Focus on why the main approaches exist and explain their differences with examples.
```

```text
$grasp Build a systematic map of Agent Memory with about two hours of study material. Include representative sources and separate essentials from optional details.
```

## Check whether you understand

The check is independent of the guide's length. Grasp normally starts with one question; answer in your own words and it will choose the next question based on your response. Expect roughly 3–5 exchanges covering purpose, relationships, and a simple new situation. You can stop or skip at any time.

```text
I have finished reading. Ask me one core question at a time to check whether I understand the main ideas. Give feedback after I answer.
```

If you already studied elsewhere:

```text
$grasp Check my understanding of databases. Here is what I have learned: [paste your notes or explanation].
```

The final feedback explains what your answers demonstrate and what is still uncertain. It does not certify expertise.

## Continue without starting over

Stay in the same conversation and say what you need:

| Situation | Example follow-up |
|---|---|
| Too abstract | “Explain this with one everyday example and fewer terms.” |
| A relationship is unclear | “Where does retrieval fit in the memory lifecycle?” |
| Ready to go deeper | “Expand the update mechanism; keep the rest brief.” |
| Want current developments | “Check recent sources and show what changes this map.” |
| Want a saved note | “Save the map and the points I confused as Markdown.” |
| A visual would help | “Create an HTML guide with a diagram and expandable details.” |

For your first use, try a short overview, answer the core questions, then expand the one part that remains unclear. You do not need to specify every preference in the first prompt.

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
