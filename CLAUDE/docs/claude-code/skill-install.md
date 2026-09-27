# Skill Installation Guide (Claude Code)

Skills are folders containing a `SKILL.md` file. Claude Code loads them from:

| Scope   | Location                         | Available in      |
| ------- | -------------------------------- | ----------------- |
| Project | `<project-root>\.claude\skills\` | That project only |
| Global  | `C:\Users\<you>\.claude\skills\` | All projects      |

> Requirement: Node.js (for `npx`).

---

## 1. Install

Run from the **project root** (the folder containing `.git`).

```bash
# Impeccable
npx skills add pbakaus/impeccable

# Taste Skill (main skill only)
npx skills add https://github.com/Leonxlnx/taste-skill --skill "design-taste-frontend"

# Emil Kowalski (pick skills from the list)
npx skills add emilkowalski/skills
```

### Installer prompts

| Prompt             | Choose                                           |
| ------------------ | ------------------------------------------------ |
| Select skills      | `Space` to toggle, `Enter` to confirm            |
| Which agents       | Scroll down and check **Claude Code**            |
| Installation scope | **Project** (one repo) or **Global** (all repos) |

> ⚠ The "Universal" agents group installs to `.agents\skills\`, which Claude Code does **not** read. Always check **Claude Code** too.

---

## 2. Fix: skills installed to `.agents\skills\` only

```powershell
New-Item -ItemType Directory -Force .claude\skills
Copy-Item -Recurse -Force .agents\skills\* .claude\skills\
Remove-Item -Recurse -Force .agents   # optional, only if not using Cursor/Copilot/Codex
```

---

## 3. Manual install (no npx)

1. Clone or download the skill's GitHub repo.
2. Copy the folder that contains `SKILL.md` into `.claude\skills\` (project) or `~\.claude\skills\` (global).
3. Restart Claude Code.

---

## 4. Verify

```powershell
dir .claude\skills
```

Then restart Claude Code and type `/`. Installed skills appear as slash commands.

---

## 5. Update

```bash
npx skills update                 # all skills installed via npx skills
npx impeccable update             # Impeccable (if installed via its own CLI)
```

---

## Tips

- Commit `.claude\skills\` so the skills come with the repo on other machines.
- Don't mix too many design skills at once; conflicting rules produce inconsistent output.
- Skills run with full agent permissions. Review a skill before installing.
