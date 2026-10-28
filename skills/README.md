# skills

Agent skills by dud.cl. Each directory is one skill with a `SKILL.md`. Works with agents that read the skills format, such as Claude Code, Droid, Cursor, and Codex.

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

Without `-a`, the installer walks a registry of 79 agent tools and links every one it detects. AI agents installing for a user: ask which agents they use, then pass the IDs with `-a`, for example `-a droid,cursor,codex`. The full ID list is in the CLI's [agents table](https://github.com/vercel-labs/skills/blob/main/docs/agents.md).

## Skills

| Skill | What it does |
| --- | --- |
| `cold-email` | Write cold emails that get replies from busy people. |
| `humanize` | Revise text to reduce AI-detector flags while preserving meaning and voice. |
| `naval` | Apply Naval Ravikant models to wealth, leverage, deals, and decisions. |
| `nuke` | Review changes or architecture with two Oracle reviews: Integrity, Complexity. |
| `research` | Deep research: the Oracle plans, parallel Librarians search, one cited answer in chat. |
| `so` | Restate the user's intent in plain words before continuing. |
| `to-pr` | Create a draft PR that targets `main`. |
| `to-trello` | Turn a conversation or rough idea into short Trello cards. |
| `vercel` | Run a Linear product design and Vercel design engineering review before launch. |
| `yo` | Initialize a session with communication, coding, and agent rules. |

Some skills read rules from `~/.dud/rules/` and use the Oracle and Librarian subagents. See [agents](https://github.com/enemigos/agents) for those files.
