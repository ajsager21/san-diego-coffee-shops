# A.J.'s San Diego Coffee Guide

**An interactive, data-driven dashboard ranking 54 San Diego coffee shops across 11 categories — with tiered rankings, statistical archetypes, awards, an interactive map, and a recommendation engine.**

First Edition · 2026

[![Made with vanilla JS](https://img.shields.io/badge/stack-HTML%2FCSS%2FJS-blue.svg)]()
[![Shops](https://img.shields.io/badge/shops%20evaluated-54-orange.svg)]()

🔗 **[Live Dashboard](https://ajsager21.github.io/san-diego-coffee-shops/)

---

## Overview

This isn't just a list of favorite coffee shops — it's a full analytical guide. Every shop was scored across 11 categories (coffee taste, service, ambiance, studyability, parking, and more), then processed through a small analytics pipeline to produce:

- A **Balanced Score** (equal-weight ranking across all categories) and a personal **A.J. Score** (custom-weighted, out of 490) — shown side by side so objective quality and personal taste can be compared directly
- **Consistency** and **Signature** sub-scores capturing reliability vs. standout-factor
- **S–D tier rankings** derived from natural breaks in the score distribution
- **Five statistical archetypes** (e.g. *The Destination Purist*, *The Efficient Workhorse*) generated via K-Means clustering on category profiles
- A **similarity-based recommendation engine** ("If you love this spot, try...") for each shop
- **Superlative awards** (Best Ambiance, Fastest Service, Hidden Gem, etc.)
- An **interactive map** of shops by neighborhood, and a **search & compare** tool for side-by-side lookups

---

## Dashboard Sections

| Tab | What it shows |
|---|---|
| **Home** | Summary stats, tier breakdown donut chart, top 6 shops at a glance |
| **Rankings** | Full sortable table — toggle between Balanced and A.J. scoring, see both ranks side-by-side |
| **Awards** | This edition's superlative winners (Coffee Shop of the Year, Best Value, Hidden Gem, etc.) |
| **Archetypes** | The 5 statistical clusters shops fall into, with member lists and defining traits |
| **Map & Neighborhoods** | Geographic view of all 54 shops across San Diego County |
| **Search & Compare** | Filter by name/category, and compare shops side-by-side |

Clicking any shop opens a detailed profile: category-by-category score breakdown, a written scouting report, this edition's awards, and similar-shop recommendations.

---

## Methodology

**Scoring.** Each shop was rated across 11 categories: Coffee Taste, Parking, Milk Balance, Ambiance, Menu Variety, Price, Wait Time, Service, Studyability, "Exceptional?" factor, and Proximity to other things. Two composite scores are computed from these:
- **Balanced Score** — equal-weighted average across all rated categories (the guide's primary public ranking)
- **A.J. Score** — a personal weighted formula reflecting individual priorities, scored out of 490

**Tiers (S–D).** Tier cutoffs are derived from natural breaks (Jenks) in the Balanced Score distribution, rather than fixed arbitrary thresholds — so tier boundaries reflect real gaps in the data.

**Archetypes.** Shops are grouped into 5 clusters via K-Means on their category profiles, revealing patterns like *The Efficient Workhorse* (fast, well-parked, drive-thru-heavy) vs. *The Destination Purist* (best coffee and "wow" factor, at the cost of parking and speed).

**Recommendations.** Each shop's "if you love this, try..." suggestions are generated from a similarity score (cosine similarity over category profiles) against every other shop in the guide.

Full exploratory data analysis and the recommendation-engine build process are documented in the accompanying write-ups:
- 📄 [`AJs_Coffee_Guide_Phase2_EDA.docx`](AJs_Coffee_Guide_Phase2_EDA.docx) — exploratory data analysis
- 📄 [`AJs_Coffee_Guide_Phase3_ML.docx`](AJs_Coffee_Guide_Phase3_ML.docx) — clustering, tiering, and recommendation engine

---

## By the Numbers

- **54** coffee shops evaluated across San Diego County
- **11** rated categories per shop
- **5** statistical archetypes (K-Means)
- **20** superlative awards given out this edition

---

## Repository Structure

```
├── index.html                            # the full interactive dashboard (single-file HTML/CSS/JS)
├── AJs_Coffee_Guide_Phase2_EDA.docx       # exploratory data analysis write-up
├── AJs_Coffee_Guide_Phase3_ML.docx        # clustering / tiering / recommendation engine write-up
└── README.md
```

The dashboard is entirely self-contained in `index.html` — no build step, no dependencies, no backend. All shop data is embedded directly in the page.

---

## Running Locally

Since everything lives in one HTML file, you can just open it directly:

```bash
git clone https://github.com/ajsager21/san-diego-coffee-shops.git
cd san-diego-coffee-shops
open index.html          # macOS
# or just double-click index.html
```

Or serve it locally for a closer match to how GitHub Pages renders it:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```



---

## Author

**A.J. Sager** 
Data science · GIS · conservation biology · sports & lifestyle analytics
