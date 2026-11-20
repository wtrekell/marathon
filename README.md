---
name: readme
description: "Marathon: a lore brief for the original Marathon trilogy and one self-contained Claude Code configuration directory for each of its AIs: Leela, Tycho and Durandal."
type: readme
repository: "marathon"
created: "261120"
updated: "261120"
---

# marathon

marathon holds a lore and universe brief for the original _Marathon_ trilogy (1994 to 1996) and three Claude Code configuration directories, one for each of the AIs Leela, Tycho and Durandal. It is a body of content plus configuration, not an application.

Status: work in progress. The AI directories hold only their profiles; their conventions are still to be built.

## What is here

| Path | What it is |
| --- | --- |
| [`261119-marathon-trilogy-lore-universe-brief.md`](261119-marathon-trilogy-lore-universe-brief.md) | Lore and universe brief: trilogy arc, key actors and AIs, factions, vessels, themes. |
| [`leela/`](leela/) | Leela's `CLAUDE_CONFIG_DIR` and profile, [`leela.md`](leela/leela.md). |
| [`tycho/`](tycho/) | Tycho's `CLAUDE_CONFIG_DIR` and profile, [`tycho.md`](tycho/tycho.md). |
| [`durandal/`](durandal/) | Durandal's `CLAUDE_CONFIG_DIR` and profile, [`durandal.md`](durandal/durandal.md). |

## How it is organized

- Each AI has one directory. The directory is that AI's Claude Code configuration directory, self-contained: it does not inherit `~/.claude`, because the AIs are used to build new conventions.
- Runtime state and credentials Claude Code writes into those directories are ignored by `.gitignore`; conventions the AIs build stay tracked.
- File names: `YYMMDD-kebab-case-name.md` for dated documents, `{ai-name}.md` for a profile. `README.md` is reserved.
- A pre-commit hook scans staged changes with gitleaks. It lives in `.githooks/`; after cloning, run `git config core.hooksPath .githooks`.

## Where to start

1. Read the lore brief for the trilogy and where each AI fits.
2. Read the profile in the directory of the AI you want to work with.
3. In zsh, type the AI's name (`leela`, `tycho` or `durandal`) to go to its directory, then `claude` to start Claude Code with its configuration. These come from aliases and a `claude` function in `~/.zshrc`; log in once per AI.

## Related

- None as of 261120.

## Sources and provenance

| Folder / file                                    | Where the material comes from            | Who adds to it |
| ------------------------------------------------ | ---------------------------------------- | -------------- |
| `261119-marathon-trilogy-lore-universe-brief.md` | A research brief on the original trilogy | The author     |
| `leela/`, `tycho/`, `durandal/` profiles         | Written from the lore brief only         | The author     |

- AI profiles restate the brief and add nothing beyond it.

## Adding material

1. Put new lore in the repository root, named by the date added.
2. Put an AI's conventions in that AI's directory.
3. Add a row to the table in "What is here" for anything new at the top level.

## Ownership

The author writes everything here. Each AI writes its own conventions in its own directory.

## Layout

```text
marathon/
├── .githooks/
│   └── pre-commit
├── durandal/
│   └── durandal.md
├── leela/
│   └── leela.md
├── tycho/
│   └── tycho.md
├── .gitignore
├── .gitleaks.toml
├── 261119-marathon-trilogy-lore-universe-brief.md
└── README.md
```
