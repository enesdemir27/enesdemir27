# GitHub Profile Design — enesdemir27

## Overview

A minimal, clean GitHub profile README for a Data Engineer actively seeking work. No excessive emojis, no AI-template feel. Looks handcrafted and professional.

---

## Style

- **Theme:** Minimal & Clean (light body, dark banner)
- **Colors:** Dark navy banner (`#1a1a2e → #0f3460`), GitHub default body whites, shield.io colored badges
- **Typography:** System font stack, clean section headings with a single bottom border line — no emoji prefixes
- **Tone:** Concise prose, no buzzword stuffing, reads like a senior engineer wrote it

---

## Layout (top to bottom)

### 1. Animated Header Banner
- Tool: [capsule-render](https://github.com/kyechan99/capsule-render)
- Type: `waving` or `slice`, dark color palette
- Text: `Enes Demir` + `Data Engineer · Pipeline Architecture · Analytics`
- No bright rainbow gradients — dark navy/slate only

### 2. Typing Animation
- Tool: [readme-typing-svg](https://github.com/DenverCoder1/readme-typing-svg)
- Displayed as a plain SVG image, no box/badge around it
- Phrases (rotating):
  - `Building end-to-end data pipelines`
  - `Transforming raw data into insights`
  - `Orchestrating workflows with Airflow`
  - `Modeling data with dbt`
  - `Open to Data Engineer roles`

### 3. Open to Work Badge
- Single green pill: `● Open to work — Data Engineer roles`
- Uses shields.io or inline HTML badge, no box

### 4. About
- 2 sentences of plain prose — no bullet list
- Meta line: location (Turkey), email (demirenes2772@gmail.com)
- No personal pronoun overload, no "passionate about" clichés

### 5. Tech Stack
Grouped into 3 rows with a small plain label above each:

| Group | Tools |
|---|---|
| Core | Python, SQL, Apache Spark, Pandas |
| Orchestration & Transformation | Apache Airflow, dbt |
| Cloud & Warehouses | BigQuery, Snowflake, Redshift |
| Tools | Git, Docker, Linux |

- Badges: shields.io `flat` or `flat-square` style
- Colors: each tool's official brand color

### 6. GitHub Stats
Three side-by-side cards via external services:
- **Stats card:** `github-readme-stats` (anuraghazra) — theme: `default` or `github`
- **Streak card:** `github-readme-streak-stats` — theme: `default`
- **Top Languages:** `github-readme-stats` language card — only show Python, SQL, Shell

### 7. Contribution Snake Animation
- Tool: [Platane/snk](https://github.com/Platane/snk) via GitHub Actions
- Dark background (`#0d1117`), green cells
- GitHub Actions workflow: runs on schedule (`0 */6 * * *`) and on push, outputs SVG to `dist/` branch
- Embedded as `<img>` tag pointing to raw GitHub URL

### 8. Contact / Connect
- Two plain buttons: LinkedIn, Email
- No Twitter unless user adds it later
- Style: simple bordered buttons matching GitHub's UI

---

## Files to Create

| File | Purpose |
|---|---|
| `enesdemir27/README.md` | Main profile README |
| `.github/workflows/snake.yml` | Snake animation GitHub Action |

The snake action outputs to the `output` branch at `dist/github-contribution-grid-snake.svg`.

---

## Implementation Notes

- All external service URLs (stats, streak, snake) use `enesdemir27` as the GitHub username
- README uses raw markdown + `<img>` tags — no JS, no complex HTML (GitHub renders plain markdown)
- Stats cards: `hide_border=true`, `bg_color=ffffff` for clean integration into white body
- Snake SVG: referenced via `https://raw.githubusercontent.com/enesdemir27/enesdemir27/output/dist/github-contribution-grid-snake.svg`
- `.gitignore` should include `.superpowers/`
