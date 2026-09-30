# Emil Kowalski Skills

**Author:** Emil Kowalski (creator of Sonner & Vaul, ex-Vercel/Linear) · **Repo:** github.com/emilkowalski/skills · **Site:** emilkowal.ski/skill

Skills focused mainly on **animation and motion quality**, plus UI polish. They encode rules such as: use `ease-out` for entering elements, keep UI animations under 300ms, prefer custom easing curves over CSS defaults, and don't animate high-frequency actions.

---

## Install

```bash
npx skills add emilkowalski/skills
```

Select only the skills you need (`Space` to toggle, `Enter` to confirm).

---

## Usage

Each skill is its own slash command:

```
/<skill-name> <target or request>
```

Claude also loads them automatically when your request matches (e.g. "make this modal animation feel better").

---

## Installed (web)

| Command                          | What it does                                                   | Edits code? |
|----------------------------------|----------------------------------------------------------------|-------------|
| `/emil-design-eng`               | Main skill: animation rules + general UI polish advice         | Yes         |
| `/animate`                       | Builds an animation from scratch, choosing curve, duration, properties | Yes |
| `/review-animations`             | Strict review of existing animations against Emil's rules      | No (review) |
| `/improve-animations`            | Audits all animations in the codebase; outputs prioritized fix plans | No (plans) |
| `/find-animation-opportunities`  | Finds where motion would help, and what should *not* animate   | No (proposes) |

### Examples

```
/review-animations AuthRequiredModal.tsx
/find-animation-opportunities the dashboard
/animate a fade-and-scale entrance for the auth modal
/improve-animations
```

---

## Other skills in the repo (not installed)

| Skill                  | Purpose                                                   |
|------------------------|-----------------------------------------------------------|
| `animation-vocabulary` | Teaches the right terms to describe animations to an AI   |
| `prototype`            | Builds several versions of a UI piece with a live switcher |
| `apple-design`         | Apple's interface and motion principles, adapted for web  |
| `mobile-native`        | Makes a web app feel native on phones (100vh bug, tap highlights, safe areas) |
| `pick-ui-library`      | Chooses trusted libraries instead of hand-rolling components |
| `ask-sonner`           | Guide to the Sonner toast library                         |
| `animate-expo`         | Animation rules for React Native / Expo                   |
| `write-swift`          | Modern Swift coding                                       |

Add later with `npx skills add emilkowalski/skills` and select the one you need.

---

## Recommended workflow

```
find-animation-opportunities  →  animate  →  review-animations
```

For an existing codebase: `improve-animations` first, then execute the plan it produces.