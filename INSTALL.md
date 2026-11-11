# Install

You install this kit globally for each agent the user selects.

Kit is the directory that contains this file. Agent dir is the config directory of an agent the user selects.

Every destination is global. Use each selected agent's global configuration and pass `-g` to every skills command.

## Rule

Every destination in Destinations and Global rules is a link to its source. A link cannot diverge from the kit, so the kit stays the single source and no copy needs a merge. A second copy of a kit file is the mistake this rule prevents.

1. Link the destination when it is absent. Create a parent directory when it is absent.
2. Leave the destination when it is a link to the source.
3. Keep the destination when it is a regular file or a directory. Add the path to Conflicts. Do not delete it.
4. Keep the destination when it is a link to another path. Add the path and its target to Conflicts.
5. When a link fails, add the path to Conflicts. Do not copy in its place.

Never write a copy of a kit file beside a destination, such as a `.bak`, `.orig`, `.old`, or `*~` file. Report the path and the difference instead.

Do not edit a destination. Edit its source.

## Destinations

| Source | Global dest |
| --- | --- |
| `kit/subagents/SCOUT.md` | `~/<agent dir>/agents/scout.md` |
| `kit/subagents/SIDEKICK.md` | `~/<agent dir>/agents/sidekick.md` |

Some agents also store per-agent settings, such as a model, a tool list, and a timeout, in the agent file. A link then removes that file's own content. Add the path to Conflicts and tell the user to paste the Scout and Sidekick text into the existing profile file.

## Steps

1. Set kit to the directory that contains this file.
   Done: `kit/subagents/SCOUT.md` exists.
2. Ask the user which agents they use.
   Done: every selected agent is named.
3. Link each source in Destinations to each selected agent's global dest. Use the Rule.
   Done: each dest is a link, a skip, or a Conflicts entry.
4. Go to heading Global rules and apply it.
   Done: the Global rules completion line is met.
5. Go to heading MCP and apply it.
   Done: the MCP completion line is met.
6. Go to heading Skills and apply it.
   Done: the Skills completion line is met.
7. Print Linked, Skipped, and Conflicts.
   Done: every dest from steps 3 to 6 is in exactly one list.

A kept `scout.md` or `sidekick.md` that is not a link to the kit does not carry these rules. Report that path in Conflicts.

## Global rules

Each agent reads its own global instructions file. The install links the kit rules into the global file of each agent the user uses. When the user picks no agent, skip this section.

1. Use the agents selected in Steps.
2. Use the Rule to link `kit/AGENTS.md` to the global dest of each picked agent.

| Agent | Dest |
| --- | --- |
| Factory Droid | `~/.factory/AGENTS.md` |
| pi | `~/.pi/agent/AGENTS.md` |
| opencode | `~/.config/opencode/AGENTS.md` |
| Codex | `~/.codex/AGENTS.md` |
| Claude Code | `~/.claude/CLAUDE.md` |
| Gemini CLI | `~/.gemini/GEMINI.md` |
| Amp | `~/.config/amp/AGENTS.md` |
| Crush | `~/.config/crush/CRUSH.md` |
| Qwen Code | `~/.qwen/QWEN.md` |
| Cursor | None |

Do not create `~/.codex/AGENTS.override.md`. That file shadows the linked file. When that file exists, add its path to Conflicts.

Some agents read a second instructions file in the same directory, such as `AGENTS.md` next to `GEMINI.md` or `CLAUDE.md`. Both files reach the agent, and the table names only one. Link the second file to the same source, or add its path to Conflicts.

Cursor has no global instructions file. When the user picks Cursor, tell them to paste the rules into Settings → Rules. Add Cursor to Skipped.

Done: each picked agent is a link, a skip, or a Conflicts entry. Each agent the user did not pick stays untouched.

## MCP

MCP dest is the global MCP config file that each selected agent reads. Use `~/<agent dir>/mcp.json`, or another global path when that agent reads MCP config from there.

Read `kit/mcp.json`. Root key is the key that the dest format uses for the server map. Most agents use `mcpServers`.

1. Create the dest file with `{ "<root key>": {} }` when it is absent.
2. Take the server map from `kit/mcp.json`. If that file has key `mcpServers`, use that object. If it does not, use the root object.
3. Add a kit server key when that key is absent from dest. When you add `exa`, set header `x-api-key` to a reference to env var `EXA_API_KEY`. Use the env var syntax that the dest format uses.
4. Keep a key when it already exists. Add dest to Conflicts when a kit key exists and differs.
5. When you compare `exa`, treat any reference to env var `EXA_API_KEY` as a match, such as `${EXA_API_KEY}` or `${env:EXA_API_KEY}`.

Report when `EXA_API_KEY` is unset.

Done: dest contains every key from the kit server map, or Conflicts lists dest.

## Skills

Run every command globally for every agent selected in Steps. Add `-a` followed by every selected agent ID, for example `-a droid claude-code`.

The skills CLI installs copies. The Rule does not apply to them. The first command installs the skills in `kit/skills/` from GitHub. To refresh a copy after you edit a kit skill, push the change and run `npx skills update -g`. The other commands install external skills.

```sh
npx skills add enemigos/skills --skill adhd cold-email cli-design coding-standards humanize naval nuke research so to-draft to-slices to-trello vercel yo -g -y
npx skills add mattpocock/skills --skill codebase-design domain-modeling grill-me grill-with-docs grilling handoff improve-codebase-architecture wizard writing-for-agents -g -y
npx skills add vercel/ai@ai-sdk -g -y
npx skills add vercel-labs/agent-skills --skill writing-guidelines vercel-react-best-practices -g -y
npx skills add cloudflare/skills --skill cloudflare workers-best-practices -g -y
npx skills add raphaelsalaja/userinterface-wiki@userinterface-wiki -g -y
npx skills add superdesigndev/treg --skill treg -g -y
npx skills add Jakubantalik/transitions.dev --skill transitions-dev -g -y
npx skills add cursor/plugins --skill thermo-nuclear-code-quality-review deslop -g -y
npx skills add motiondivision/ai-kit --skill motion -g -y
npx skills add emilkowalski/skills --skill find-animation-opportunities mobile-native break-ui -g -y
npx skills add haowjy/creative-writing-skills --skill creative-writing-craft -g -y
npx skills add dmmulroy/skills --skill bro -g -y
npx skills add dmmulroy/better-result --skill adopt-better-result -g -y
npx skills add supabase/agent-skills --skill supabase supabase-postgres-best-practices -g -y
npx skills add jakubkrehel/skills --skill afk better-writing better-interface state-machine -g -y
npx skills add vercel-labs/agent-browser --skill agent-browser -g -y
npx skills add lucasmarkes/hairline -g -y
npx skills add caldoai/skills --skill untangle-codebase -g -y
```

Done: each command exits 0 and its installation summary covers every selected agent, or Conflicts records the command and the exit status.

If the user names a subset, run only the matching commands. Keep the same global flag and selected agent IDs.

Go to heading Grill when the user asks which grill skill to use.

## Grill

| Situation | Skill |
| --- | --- |
| No repo, or the idea is not about this codebase | `grill-me` |
| A change in a repo, or a repo with no domain docs | `grill-with-docs` |

`grill-me` writes no files. `grill-with-docs` writes terms to `CONTEXT.md` and hard decisions to `docs/adr/`.
