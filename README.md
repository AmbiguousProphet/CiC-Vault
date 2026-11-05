# CiC-Vault

A template for organizing and running chats with Claude is Claude (CiC).

A Claude Code setup for adult roleplay and fiction writing, built as an Obsidian vault. Obsidian is the viewer and editor; Claude Code reads and writes the same notes.

**New here? Read [GUIDE.md](GUIDE.md)** for setup, note types, age variants, play controls and troubleshooting.

## What's here

| Path | What it is |
|---|---|
| `CLAUDE.md` | The base instructions: scope, craft, bracket controls, vault rules. Loaded every session. |
| `.claude/skills/vault-session/` | Starts, sets up, resumes, saves and logs stories; runs the cast scope check; keeps the style library. |
| `.claude/scripts/vault.py` | Creates notes from templates, loads notes without Obsidian-only blocks, prints cast and state, lints the vault. Python 3, standard library only. |
| `.claude/hooks/` + `.claude/settings.json` | Session start loads the active story; viewer commands answer without a model turn; lore entries load when mentioned; status line shows the story and last beat. |
| `Templates/` | Character, roleplay profile, user persona, story bio, adult file, setting, story. |
| `Style/reference.md` | Your Keep and Avoid examples, logged in play with `[keep]` and `[avoid]`. |
| `story-profile.md` | Your defaults, style, kinks, limits and finished stories. Built on first use. |

## Setup

1. Make a new **private** repo from this template (*Use this template → Create a new repository*, visibility Private), or download it and push it to an empty private repo. Vaults hold explicit material; keep them out of public repos.
2. Open the folder in Obsidian. Optional: set Settings → Templates → folder to `Templates`, and install Obsidian Git to sync.
3. Open the folder in Claude Code and send `prepare for fictional roleplay`, or `[setup]`. The first run builds your profile and asks whether to keep, trim or add to the default **Open** list in `CLAUDE.md`. The **Out of scope** list stays as shipped.
4. The sample (`Characters/Mara Quill`, `Characters/Tobias Rook`, `Settings/Saltmarrow.md`, `Stories/Harbor Debt.md`) shows each note type filled in. Try `[cast Harbor Debt]`, then delete it or keep it.

**About scope.** `CLAUDE.md` tells Claude what the vault is for, and the vault's script enforces the age and stage rules on its own. Claude still uses its own judgment, so the Open list describes what this setup is built for, not a promise of what any session will write.

## Tests

`python3 -m unittest discover tests` checks the age gate: adult files refused for child and teen profiles, under-18 ages caught, and lint errors on a broken vault.

## Moving an existing vault in

- Put your old templates in `Templates/Legacy/`. Notes made from them load cleanly, because the script strips guidance lines from every template it finds.
- Rename `universe` to `world` in frontmatter, and add `age` and `body_age` to profiles (and to character pages where they hold in every story). Nonhumans get a `mind` line.
- Run `python3 .claude/scripts/vault.py lint` and fix what it reports.

## In play

Bracket commands are listed in `CLAUDE.md`. The ones you'll use most: `[setup]`, `[save]`, `[rewind]`, `[tone: harsher]`, `[cast]`, `[state]`, `[keep]`.

**Free commands.** Send one of these as the whole message and a hook answers it without a model turn: `[cast]`, `[state]`, `[show <note>]`, `[list <type>]`, `[lint]`, `[lore <text>]`.

**The active story** is the most recently edited story note with `status: active`. Set others to `paused` to switch.

**Lore.** Bullets under a setting's `## Lore entries` load into the conversation once per session when their key comes up, for the active story's world only. Add extra keys with slashes: `**The Tithe Court / tithe-wardens / wardens:**`.

**Hooks need Python 3** on the machine running Claude Code (`pkg install python` in Termux). Set `VAULT_AUTOPULL=0` to stop the session-start `git pull`. Hooks fail open: if one breaks, play continues without it.
