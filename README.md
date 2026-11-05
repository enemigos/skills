# Agents

Works on all agents. My personal setup.

## Install

All skills, global:

```sh
npx skills add enemigos/skills --skill '*' -g -y
```

One skill, one project:

```sh
npx skills add enemigos/skills --skill nuke -y
```

Update installed skills:

```sh
npx skills update
```

Without `-a`, the installer walks a registry of 79 agent tools and links every one it detects. AI agents installing for a user: ask which agents they use, then pass the IDs with `-a`, for example `-a droid cursor codex`. The full ID list is in the CLI's [agents table](https://github.com/vercel-labs/skills/blob/main/docs/agents.md).

Follow [INSTALL.md](./INSTALL.md) to install the kit and the skills.

## Skills

Each directory in [skills/](./skills/) is one skill with a `SKILL.md`.

| Skill | What it does |
| --- | --- |
| `cold-email` | Write cold emails that get replies from busy people. |
| `coding-standards` | Design principles and coding standards: general and TypeScript. |
| `humanize` | Strip AI writing tells from prose while preserving facts and voice. |
| `naval` | Apply Naval Ravikant models to wealth, leverage, deals, and decisions. |
| `nuke` | Review changes or architecture with two Oracle reviews: Integrity, Complexity. |
| `research` | Deep research: the Oracle plans, parallel Librarians search, one cited answer in chat. |
| `so` | Restate the user's intent in plain words before continuing. |
| `to-pr` | Create a draft PR that targets `main`. |
| `to-trello` | Turn a conversation or rough idea into short Trello cards. |
| `vercel` | Run a Linear product design and Vercel design engineering review before launch. |
| `yo` | Initialize a session with communication, coding, and agent rules. |

The [kit](#kit) holds the Scout and Sidekick subagent files. Sidekick reads the `coding-standards` skill before editing.

## Kit

- [AGENTS.md](./AGENTS.md): main agent rules
- [ASSISTANT.md](./ASSISTANT.md): custom instructions for concise general chat in ChatGPT, Claude, and Gemini
- [mcp.json](./mcp.json): MCP servers
- [subagents/](./subagents/): Scout and Sidekick system prompts
