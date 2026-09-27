# Impeccable

**Author:** Paul Bakaus · **Repo:** github.com/pbakaus/impeccable · **Docs:** impeccable.style

A single design skill with 24 commands and 61 detector rules that catch common "AI-generated" UI patterns (Inter everywhere, purple-to-blue gradients, nested cards, gray text on colored backgrounds). Built on top of Anthropic's `frontend-design` skill.

---

## Install

```bash
npx skills add pbakaus/impeccable      # skill only
npx impeccable install                 # skill + auto design-check hook (recommended)
npx impeccable update                  # update
```

Claude Code plugin alternative:

```
/plugin marketplace add pbakaus/impeccable
```

---

## Syntax

```
/impeccable <command> <target>
/impeccable <plain description>        # e.g. /impeccable redo this hero section
```

Type `/impeccable` alone to list all commands.

---

## Start here (once per project)

| Command                | Purpose                                                                                  |
| ---------------------- | ---------------------------------------------------------------------------------------- |
| `/impeccable init`     | Asks about your product and writes `PRODUCT.md` (audience, purpose, constraints, voice). |
| `/impeccable document` | Generates `DESIGN.md` from existing code (colors, type, components).                     |

---

## Commands

### Plan & build

| Command   | What it does                                               |
| --------- | ---------------------------------------------------------- |
| `craft`   | Full plan-then-build flow with visual iteration            |
| `shape`   | Plan UX/UI before writing code                             |
| `extract` | Pull reusable components and tokens into the design system |

### Review (read first, safest)

| Command    | What it does                                             |
| ---------- | -------------------------------------------------------- |
| `critique` | UX review: hierarchy, clarity, emotional resonance       |
| `audit`    | Technical checks: accessibility, performance, responsive |

### Refine

| Command    | What it does                                           |
| ---------- | ------------------------------------------------------ |
| `polish`   | Final pass and design-system alignment before shipping |
| `bolder`   | Amplify a boring design                                |
| `quieter`  | Tone down an overly loud design                        |
| `distill`  | Strip down to the essentials                           |
| `typeset`  | Fix fonts, hierarchy, sizing                           |
| `layout`   | Fix layout, spacing, visual rhythm                     |
| `colorize` | Introduce strategic color                              |
| `clarify`  | Improve unclear UX copy                                |

### Robustness

| Command    | What it does                                    |
| ---------- | ----------------------------------------------- |
| `harden`   | Error handling, i18n, text overflow, edge cases |
| `onboard`  | First-run flows, empty states, activation paths |
| `adapt`    | Adapt for different devices / screen sizes      |
| `optimize` | Performance improvements                        |

### Motion & delight

| Command     | What it does                          |
| ----------- | ------------------------------------- |
| `animate`   | Add purposeful motion                 |
| `delight`   | Add moments of joy                    |
| `overdrive` | Add technically extraordinary effects |

### Live browser mode

| Command    | What it does                                             |
| ---------- | -------------------------------------------------------- |
| `live`     | Iterate on elements visually in the browser              |
| `generate` | Auto-generate variants of a named element in the browser |

### Utility

| Command         | What it does                                           |
| --------------- | ------------------------------------------------------ |
| `pin <command>` | Creates a standalone shortcut (`pin audit` → `/audit`) |

---

## Examples

```
/impeccable critique AuthRequiredModal
/impeccable audit the dashboard
/impeccable harden the login form
/impeccable polish settings page
```

---

## Workflow (existing project, e.g. SAAMS)

### Syntax breakdown

```
/impeccable   layout        the dashboard
└─ skill ─┘   └ command ┘   └── target ──┘
```

| Part            | Meaning                                                |
| --------------- | ------------------------------------------------------ |
| `/impeccable`   | Tinatawag ang skill (laging pareho)                    |
| `layout`        | Ang command, kung ano ang gagawin (see Commands above) |
| `the dashboard` | Ang target, kung aling page o component ang aayusin    |

---

### 1. Setup (isang beses lang)

```
/impeccable init
/impeccable document
```

- `init`: tatanungin ka tungkol sa project (para saan, sino ang users) at gagawa ng `PRODUCT.md`. Sagutin nang maayos; dito nakasalalay kung gaano babagay ang mga suggestion.
- `document`: babasahin ang code at gagawa ng `DESIGN.md` (kulay, fonts, components na gamit na), para hindi lumayo sa existing style.

### 2. I-review ang isang page o component

```
/impeccable critique the dashboard
/impeccable audit the dashboard
```

- `critique`: design at UX (hierarchy, linaw, dating)
- `audit`: technical (accessibility, responsive, performance)

> Walang binabago dito; findings lang. Basahin muna.

### 3. Ayusin gamit ang specific na command

Piliin ang akma sa lumabas sa review:

```
/impeccable layout the dashboard      # spacing, alignment
/impeccable typeset the dashboard     # fonts, sizes
/impeccable clarify the dashboard     # labels, messages
/impeccable harden the login form     # errors, empty data, mahabang text
/impeccable adapt the dashboard       # mobile view
```

### 4. Final pass

```
/impeccable polish the dashboard
```

### 5. Commit, tapos lumipat sa susunod na page

```bash
git add .
git commit -m "Polish dashboard UI"
```

---

### Buod

```
init → document → (bawat page: critique/audit → fix → polish → commit)
```

### Bagong page mula sa simula

```
/impeccable shape the reports page    # plano muna bago mag-code
/impeccable craft the reports page    # build na may visual iteration
```

---

### Tips

- **Isang page o component lang bawat ikot.** Kapag buong app agad, malabo ang resulta at mahirap i-review.
- **Mag-commit bago mag-fix o mag-polish** para madaling bumalik.
- Kapag naka-auto mode ang Claude Code, diretso itong mag-e-edit. I-review ang mga binago bago mag-commit (`Shift+Tab` para palitan ang mode).
- Madalas gamitin ang isang command? I-pin ito: `/impeccable pin audit` → `/audit` na lang.
- Para sa `live` mode, kailangang tumatakbo ang dev server (`npm run dev`).

---

## CLI (no AI needed)

```bash
npx impeccable detect src/                 # scan a folder for anti-patterns
npx impeccable detect index.html           # scan a file
npx impeccable detect http://localhost:5173  # scan a running page
npx impeccable detect --json .             # JSON output (CI)
```

---

## Notes

- Commit `PRODUCT.md`, `DESIGN.md`, and `.impeccable/config.json`.
- Add Impeccable's `.gitignore` block (see repo README) to ignore screenshots and cache in `.impeccable/`.
- Commit your work before `polish` or other editing commands so changes are easy to revert.
