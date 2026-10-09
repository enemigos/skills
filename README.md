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
npx skills update -g
```

## Skills

| Skill | What it does |
| --- | --- |
| `cold-email` | Write cold emails that get replies from busy people. |
| `naval` | Apply Naval Ravikant models to wealth, leverage, deals, and decisions. |
| `nuke` | Review changes or architecture with three Oracle reviews: Defects, Standards, Complexity. |
| `research` | Run research with background Librarians and save one cited report. |
| `so` | Restate the user's intent in plain words before continuing. |
| `to-pr` | Create a draft PR that targets `main`. |
| `to-trello` | Turn a conversation or rough idea into short Trello cards. |
| `vercel` | Run a Linear product design and Vercel design engineering review before launch. |

Some skills read rules from `~/.dud/rules/` and use the Oracle and Librarian subagents. See [agents](https://github.com/enemigos/agents) for those files.
