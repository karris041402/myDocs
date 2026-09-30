# Taste Skill

**Author:** Leonxlnx · **Repo:** github.com/Leonxlnx/taste-skill · **Docs:** tasteskill.dev

An "anti-slop" frontend skill. It reads your brief, infers the design style, and tunes three dials (variance, motion, density) to produce distinctive UI instead of generic AI layouts. Best for landing pages, portfolios, and redesigns.

---

## Install

```bash
# Main skill (v2)
npx skills add https://github.com/Leonxlnx/taste-skill --skill "design-taste-frontend"

# Pin to original v1 behavior
npx skills add https://github.com/Leonxlnx/taste-skill --skill "design-taste-frontend-v1"

# Everything in the repo
npx skills add https://github.com/Leonxlnx/taste-skill
```

> Use the **install name** (right column below) with `--skill`, not the folder name.

---

## Usage

```
/design-taste-frontend <what to build or redesign>
```

Before coding, it states one line: *"Reading this as: <page kind> for <audience>, with a <vibe> language…"* and asks at most one question.

Example:

```
/design-taste-frontend redesign the SAAMS login page, clean and professional
```

---

## The 3 dials (1–10)

Set at the top of `.claude\skills\design-taste-frontend\SKILL.md`, or state them in your prompt.

| Dial               | Low                     | High                        |
|--------------------|-------------------------|-----------------------------|
| `DESIGN_VARIANCE`  | Centered, clean         | Asymmetric, experimental    |
| `MOTION_INTENSITY` | Hover effects only      | Scroll / magnetic effects   |
| `VISUAL_DENSITY`   | Spacious                | Dense (dashboards)          |

Example prompt: `use DESIGN_VARIANCE 3, MOTION_INTENSITY 2, VISUAL_DENSITY 7`

---

## Skills in the repo

### Code skills
| Install name                 | Use for                                                  |
|------------------------------|----------------------------------------------------------|
| `design-taste-frontend`      | Default. Safest general choice (v2, experimental)        |
| `design-taste-frontend-v1`   | Original v1, only if v2 breaks your workflow             |
| `gpt-taste`                  | Stricter variant tuned for GPT/Codex                     |
| `redesign-existing-projects` | Audit an existing UI, then fix layout, spacing, hierarchy |
| `high-end-visual-design`     | Calm, premium look: soft contrast, whitespace, spring motion |
| `minimalist-ui`              | Editorial style (Notion/Linear), restrained palette      |
| `industrial-brutalist-ui`    | Swiss type, sharp contrast, raw structure                |
| `stitch-design-taste`        | Google Stitch rules + optional `DESIGN.md` export        |
| `full-output-enforcement`    | Stops the agent from leaving placeholders or unfinished code |
| `image-to-code`              | Generate reference images → analyze → implement         |

### Image-only skills (no code)
| Install name                 | Use for                                   |
|------------------------------|-------------------------------------------|
| `imagegen-frontend-web`      | Website comps (hero, landing sections)    |
| `imagegen-frontend-mobile`   | Mobile screens and flows                  |
| `brandkit`                   | Logo, palette, and type boards            |

---

## Which one to use

- New page → `design-taste-frontend`
- Existing app (like SAAMS) → `redesign-existing-projects`
- Style already decided → add `minimalist-ui`, `high-end-visual-design`, or `industrial-brutalist-ui`
- Agent keeps truncating code → add `full-output-enforcement`

---

## Update

Re-run the same install command; the new `SKILL.md` replaces the old one.