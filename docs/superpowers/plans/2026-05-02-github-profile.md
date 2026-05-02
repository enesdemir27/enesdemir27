# GitHub Profile Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a minimal, professional GitHub profile README for a Data Engineer (enesdemir27) with animated banner, typing SVG, tech stack badges, GitHub stats cards, contribution snake, and a contact section.

**Architecture:** A single `README.md` in the `enesdemir27/enesdemir27` special repo, composed entirely of markdown + `<img>` tags pointing to external SVG/image services (capsule-render, readme-typing-svg, shields.io, github-readme-stats, github-readme-streak-stats, and the snake SVG). A GitHub Actions workflow generates the snake SVG on a schedule and pushes it to the `output` branch.

**Tech Stack:** GitHub Markdown, shields.io, capsule-render API, readme-typing-svg API, github-readme-stats API, github-readme-streak-stats API, Platane/snk GitHub Action

---

## File Map

| File | Action | Purpose |
|---|---|---|
| `README.md` | Create | Main profile page |
| `.github/workflows/snake.yml` | Create | Generates snake SVG every 6h and on push |
| `.gitignore` | Create | Excludes `.superpowers/` |

---

### Task 1: Repo scaffold + .gitignore

**Files:**
- Create: `README.md` (stub)
- Create: `.gitignore`

- [ ] **Step 1: Create stub README.md**

```markdown
# enesdemir27
```

- [ ] **Step 2: Create .gitignore**

```
.superpowers/
```

- [ ] **Step 3: Verify files exist**

```bash
ls -1
# Expected: README.md  .gitignore  docs/
```

- [ ] **Step 4: Commit**

```bash
git add README.md .gitignore
git commit -m "chore: init profile repo scaffold"
```

---

### Task 2: Animated header banner

**Files:**
- Modify: `README.md`

The banner uses the capsule-render API. The URL is constructed as a query string — no signup required, rendered as a plain `<img>` tag.

- [ ] **Step 1: Replace README.md with banner section**

```markdown
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,100:0f3460&height=200&section=header&text=Enes%20Demir&fontSize=48&fontColor=e6edf3&fontAlignY=38&desc=Data%20Engineer%20%C2%B7%20Pipeline%20Architecture%20%C2%B7%20Analytics&descAlignY=58&descColor=8b949e&descSize=16" width="100%" />
</p>
```

- [ ] **Step 2: Verify URL renders**

Open this URL in a browser and confirm a dark waving banner appears with the correct text:
```
https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,100:0f3460&height=200&section=header&text=Enes%20Demir&fontSize=48&fontColor=e6edf3&fontAlignY=38&desc=Data%20Engineer%20%C2%B7%20Pipeline%20Architecture%20%C2%B7%20Analytics&descAlignY=58&descColor=8b949e&descSize=16
```

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: add animated header banner"
```

---

### Task 3: Typing animation + Open to Work badge

**Files:**
- Modify: `README.md`

- [ ] **Step 1: Add typing SVG and OtW badge after banner**

Append after the banner `<p>` block:

```markdown
<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=16&pause=1200&color=57606A&center=true&vCenter=true&width=500&lines=Building+end-to-end+data+pipelines;Transforming+raw+data+into+insights;Orchestrating+workflows+with+Airflow;Modeling+data+with+dbt;Open+to+Data+Engineer+roles" alt="Typing SVG" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Open%20to%20Work-Data%20Engineer%20roles-2da44e?style=flat-square&labelColor=dafbe1&color=2da44e" />
</p>
```

- [ ] **Step 2: Verify typing URL renders**

Open in browser — confirm the phrases cycle through correctly:
```
https://readme-typing-svg.demolab.com?font=Fira+Code&size=16&pause=1200&color=57606A&center=true&vCenter=true&width=500&lines=Building+end-to-end+data+pipelines;Transforming+raw+data+into+insights;Orchestrating+workflows+with+Airflow;Modeling+data+with+dbt;Open+to+Data+Engineer+roles
```

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: add typing animation and open to work badge"
```

---

### Task 4: About section

**Files:**
- Modify: `README.md`

- [ ] **Step 1: Add About section**

```markdown
## About

I design and build end-to-end data pipelines — from raw ingestion to analytics-ready tables. Focused on clean architecture, reliable orchestration, and helping data teams move faster.

📍 Turkey &nbsp;·&nbsp; demirenes2772@gmail.com
```

- [ ] **Step 2: Commit**

```bash
git add README.md
git commit -m "feat: add about section"
```

---

### Task 5: Tech stack badges

**Files:**
- Modify: `README.md`

Each badge uses shields.io with `style=flat-square` and official brand colors. All badge URLs are static — no auth needed.

- [ ] **Step 1: Add Tech Stack section**

```markdown
## Tech Stack

**Core**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-E38C00?style=flat-square&logo=amazondynamodb&logoColor=white)
![Apache Spark](https://img.shields.io/badge/Apache%20Spark-E25A1C?style=flat-square&logo=apachespark&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)

**Orchestration & Transformation**

![Apache Airflow](https://img.shields.io/badge/Apache%20Airflow-017CEE?style=flat-square&logo=apacheairflow&logoColor=white)
![dbt](https://img.shields.io/badge/dbt-FF694A?style=flat-square&logo=dbt&logoColor=white)

**Cloud & Warehouses**

![BigQuery](https://img.shields.io/badge/BigQuery-4285F4?style=flat-square&logo=googlebigquery&logoColor=white)
![Snowflake](https://img.shields.io/badge/Snowflake-29B5E8?style=flat-square&logo=snowflake&logoColor=white)
![Redshift](https://img.shields.io/badge/Redshift-8C4BFF?style=flat-square&logo=amazonredshift&logoColor=white)

**Tools**

![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
```

- [ ] **Step 2: Verify a sample badge URL**

Open in browser — confirm it renders a colored flat-square badge:
```
https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white
```

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: add tech stack badges"
```

---

### Task 6: GitHub Stats cards

**Files:**
- Modify: `README.md`

Cards render dynamically from the public github-readme-stats and streak-stats APIs. `hide_border=true` and `bg_color=ffffff` keep them clean on GitHub's white body. Stats and streak cards are side-by-side using an HTML table; the languages card goes below.

- [ ] **Step 1: Add GitHub Stats section**

```markdown
## GitHub Stats

<table>
  <tr>
    <td>
      <img src="https://github-readme-stats.vercel.app/api?username=enesdemir27&show_icons=true&hide_border=true&bg_color=ffffff&title_color=0969da&icon_color=0969da&text_color=24292f&hide=prs,issues,contribs" />
    </td>
    <td>
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=enesdemir27&hide_border=true&background=ffffff&ring=0969da&fire=f85149&currStreakLabel=0969da" />
    </td>
  </tr>
</table>

<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=enesdemir27&layout=compact&hide_border=true&bg_color=ffffff&title_color=0969da&text_color=24292f&langs_count=5" />
```

- [ ] **Step 2: Verify stats URL**

Open in browser — confirm it shows stats for enesdemir27 (may show zeroes if no public repos yet, that's fine):
```
https://github-readme-stats.vercel.app/api?username=enesdemir27&show_icons=true&hide_border=true&bg_color=ffffff&title_color=0969da&icon_color=0969da&text_color=24292f
```

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: add github stats cards"
```

---

### Task 7: Contribution snake GitHub Action

**Files:**
- Create: `.github/workflows/snake.yml`
- Modify: `README.md`

The action runs Platane/snk, generates a dark-themed snake SVG from the contribution graph, and pushes it to the `output` branch under `dist/`. The README then embeds it via raw URL.

- [ ] **Step 1: Create workflow directory**

```bash
mkdir -p .github/workflows
```

- [ ] **Step 2: Create snake.yml**

```yaml
name: Generate Snake Animation

on:
  schedule:
    - cron: "0 */6 * * *"
  workflow_dispatch:
  push:
    branches:
      - main

jobs:
  generate:
    runs-on: ubuntu-latest
    steps:
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: enesdemir27
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark

      - uses: crazy-max/ghaction-github-pages@v3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

- [ ] **Step 3: Add snake image to README.md**

Append a new section after GitHub Stats:

```markdown
## Contribution Activity

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/enesdemir27/enesdemir27/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/enesdemir27/enesdemir27/output/github-contribution-grid-snake.svg" />
  <img alt="contribution snake" src="https://raw.githubusercontent.com/enesdemir27/enesdemir27/output/github-contribution-grid-snake.svg" />
</picture>
```

- [ ] **Step 4: Commit**

```bash
git add .github/workflows/snake.yml README.md
git commit -m "feat: add snake animation workflow and embed SVG"
```

---

### Task 8: Contact section + footer wave banner

**Files:**
- Modify: `README.md`

- [ ] **Step 1: Add Connect section and closing wave banner**

```markdown
## Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-enesdemir27-0a66c2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/enesdemir27)
[![Email](https://img.shields.io/badge/Email-demirenes2772@gmail.com-0969da?style=flat-square&logo=gmail&logoColor=white)](mailto:demirenes2772@gmail.com)

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,100:0f3460&height=80&section=footer" width="100%" />
</p>
```

- [ ] **Step 2: Update LinkedIn URL**

Replace `https://linkedin.com/in/enesdemir27` with the actual LinkedIn profile URL if it differs from the username.

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "feat: add contact section and footer wave"
```

---

### Task 9: Push to GitHub and enable Actions

**Prerequisites:** The `enesdemir27/enesdemir27` repo must exist on GitHub (create it via github.com/new — repo name must match username exactly, tick "Add README" is optional since we have one).

- [ ] **Step 1: Add GitHub remote**

```bash
git remote add origin https://github.com/enesdemir27/enesdemir27.git
```

- [ ] **Step 2: Push main branch**

```bash
git push -u origin main
```

- [ ] **Step 3: Trigger snake workflow manually**

Go to: `https://github.com/enesdemir27/enesdemir27/actions`

Click **Generate Snake Animation** → **Run workflow** → **Run workflow**.

Wait ~60 seconds, then verify the `output` branch exists and contains `github-contribution-grid-snake.svg`.

- [ ] **Step 4: Verify profile looks correct**

Open `https://github.com/enesdemir27` — confirm all sections render: banner, typing, badge, about, stack, stats, snake, contact, footer wave.

---

## Post-launch

- If stats cards show "not found", the repo may be private — go to github-readme-stats settings or wait a few minutes for the cache to populate.
- Streak stats may show 0 on day 1; push a commit to start the streak counter.
- Snake SVG will be blank until the Action runs successfully at least once.
