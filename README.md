# Shai — Progress System v2

Interactive demo of a progress & rewards system for an AI learning app. Account-level XP, open-ended levels, multi-plan navigation, lesson-level completion.

## Run

Open `index.html` in a browser. No build, no install — React loaded via CDN.

## Live demo

**https://volzokalex.github.io/shai-xp-progress/**

## What it demonstrates

### Global progress (account level)
- **XP is global** — accumulates across all plans, never resets
- **Level is open-ended** — no cap. Names by range: Curious (1–3) → Explorer (4–6) → Prompter (7–10) → Builder (11–15) → Operator (16–20) → Optimizer (21–24) → Legend (25+)
- **Dynamic XP formula**: `XP per mission = (5950 / Total Weight) × Weight`. Weights: F=1, B=2.5, E=4.5. Each plan totals 5,950 XP regardless of composition
- **Multi-level-up**: a single Expert mission at low XP can cross several levels — rewards queue and animate one after another

### 4-tab navigation

- **Plans** — 3 plans with distinct compositions (6F/4B/2E, 3F/6B/3E, 2F/4B/6E). Tap plan → Mission Map (12 zigzag nodes) → tap mission → lesson node view. Tap lessons to complete; when all lessons done, mission completes and awards XP. `⚙ Configure Plans` opens the configurator
- **All Missions** — flat library of all 36 missions. Foundation/Builder tappable to complete. Expert missions locked with explainer popup ("capstone project — requires full plan")
- **Rewards** — global Reward Vault. Each reward is Name + Icon (custom, no auto-styling). NEW badge on unseen rewards; clears only when that specific reward is tapped
- **Certificates** — issued automatically when all 12 missions of a plan are complete. Shows plan name + issue date

### Plan Configurator
- Plan 1 / Plan 2 / Plan 3 switcher
- Each plan configurable independently (tap slots to cycle Foundation → Builder → Expert)
- Mission #12 always Expert (locked) — triggers certificate
- Locked during play; Play Again resets progress but keeps configurations

### Preserved from v1
- Dark game-like visual style
- XP fly-out animation (+X XP over progress bar)
- Level-up overlay with confetti particles and animated reward reveal
- Play Again resets progress, keeps configuration

## Tech

Single-file HTML + React 18 via CDN + Babel standalone. ~1000 lines including CSS.
