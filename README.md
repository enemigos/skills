# Agents

Works on all agents. My personal setup.

## Install

Always install skills globally.

All skills:

```sh
npx skills add enemigos/skills --skill '*' -g -y
```

One skill:

```sh
npx skills add enemigos/skills --skill nuke -g -y
```

Update global skills:

```sh
npx skills update -g
```

Ask which agents the user runs, then pass every selected ID with `-a`, for example `-a droid claude-code`. Without `-a`, the installer links every agent it detects. The full ID list is in the CLI's [agents table](https://github.com/vercel-labs/skills/blob/main/docs/agents.md).

Follow [INSTALL.md](./INSTALL.md) to install the kit and the skills.

## Skills

Each directory in [skills/](./skills/) is one skill with a `SKILL.md`.

| Skill | What it does |
| --- | --- |
| `adhd` | Write ADHD-friendly answers and reset explanations that were unclear or overwhelming. |
| `cold-email` | Write cold emails that get replies from busy people. |
| `cli-design` | Design and review command-line interfaces, output contracts, interaction, and safety. |
| `coding-standards` | Design principles and coding standards: general and TypeScript. |
| `humanize` | Strip AI writing tells from prose while preserving facts and voice. |
| `naval` | Apply Naval Ravikant models to wealth, leverage, deals, and decisions. |
| `nuke` | Review changes or architecture with two subagent reviews: Integrity, Complexity. |
| `research` | Deep research: you plan, parallel Scout agents search, one cited answer in chat. |
| `so` | Restate the user's intent in plain words before continuing. |
| `to-draft` | Write and publish a PR title and body for built work. |
| `to-slices` | Turn a conversation into parallel vertical-slice plans. |
| `to-trello` | Turn a conversation or rough idea into short Trello cards. |
| `vercel` | Run a Linear product design and Vercel design engineering review before launch. |
| `yo` | Initialize a session with communication, coding, and agent rules. |

The [kit](#kit) holds the Scout and Sidekick subagent files. Sidekick reads the `coding-standards` skill before editing.

## Kit

- [AGENTS.md](./AGENTS.md): main agent rules
- [ASSISTANT.md](./ASSISTANT.md): custom instructions for concise general chat in ChatGPT, Claude, and Gemini
- [mcp.json](./mcp.json): MCP servers
- [subagents/](./subagents/): Scout and Sidekick system prompts
