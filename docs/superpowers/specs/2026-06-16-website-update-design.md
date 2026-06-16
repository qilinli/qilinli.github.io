# Academic Website Update — Design Spec

**Date:** 2026-06-16
**Goal:** Bring `qilinli.github.io` up to date with the current CV (`files/CV-Qilin.pdf`). Fix bugs, add a News section, expand publications, add a Research page (grants/awards/service), and remove leftover template cruft. No visual/theme redesign.

**Source of truth:** `files/CV-Qilin.pdf` (dated April 29, 2026).

---

## 1. Profile & bio

### `_config.yml`
- `title`: `"Qilin Li / Dr"` → `"Qilin Li / Senior Lecturer"` (or keep "Dr"; reflect Senior Lecturer role).
- `description` (line 14 & author bio line 27): replace `"Machine learning researcher working on structural engineering"` with a broader line, e.g. `"AI researcher working on intelligent infrastructure and structural health monitoring"`.
- `author.avatar`: `"QILIN LI-21-1080.jpg"` → `"Qilin-17-crop.png"` (newly added photo in `images/`).

### `_pages/about.md`
- Intro: "a lecturer at Curtin University" → "a **Senior Lecturer** at Curtin University".
- Broaden the research framing to include agentic AI/LLMs, digital twins, vision-based SHM, and ML surrogate modelling (currently only "spatial-temporal simulation … in structural engineering").
- Fix typos (line 16): "world-class **structral** dynamics lab" → "structural"; "**Central for Infrastructral** Monitoring and Protection" → "**Centre for Infrastructural** Monitoring and Protection (CIMP)" (matches CV's official name).

---

## 2. News section (homepage)

Add a `News` section near the top of `_pages/about.md` (before "My research"), reverse-chronological, ~7–8 dated items drafted from the CV. Draft content (user edits afterward):

- **2026** — Awarded an **ARC DECRA** (A$510,000) for *Next-Generation Agentic AI for Intelligent Infrastructure Monitoring*.
- **Jan 2026** — Promoted to **Senior Lecturer** at Curtin University.
- **2025** — Awarded the **National Road Safety Action Grant** (A$641,436) for AI-assisted sustainable road barrier design.
- **2025** — Awarded a **Curtin Trailblazer EMCR Grant** for an AI-empowered digital twin for reclaimers.
- **2025** — Guest Editor, *Buildings* special issue: *AI-Powered Structural Health Monitoring*.
- **2024** — Awarded an **ARC Linkage Grant** (A$415,380) on damage detection via infrastructure digital twins.
- **2024** — Co-led the **CSIRO Next-Gen AI Graduate Program** (A$350,000) with WA Police.
- **2024** — Curtin Academy **iSoLT Teaching Innovation Grant**.

(Style: simple `<ul>` or markdown list with bold dates; keep it lightweight and consistent with the page.)

---

## 3. Publications (`_publications/`)

**Scope:** CV "Top 10" + every 2024–2025 journal paper as individual entry files (~26 total, of which 1 conference). Keep the existing "find my articles on Google Scholar" link at the top of `_pages/publications.html`.

### Entry format
Match existing files (YAML front matter: `title`, `collection`, `category`, `permalink`, `excerpt`, `date`, `venue`, `paperurl`, optional `slidesurl`, `citation`; body = short summary + recommended citation). Use:
- `category: manuscripts` → renders under "Selected Journal Articles".
- `category: conferences` → renders under "Conference Papers" (currently defined in `_config.yml` but unused).

### Ordering
Filename date controls order (page renders `reversed`, newest first). Use `YYYY-01-NN` synthetic dates so 2025 papers appear first, then 2024, etc.

### Links policy
`paperurl` must point to the correct publisher page. During implementation, look up each by exact title (DOI/publisher URL). Where a link can't be verified, fall back to a Google Scholar search link — never leave a wrong/duplicate URL. ISSN sanity check: `S0045-7949…` = Computers & Structures, `S0141-0296…` = Engineering Structures.

### Fix existing 6 files
| File | Paper | Venue | Link issue |
|---|---|---|---|
| `2024-01-02-BGN.md` | BLEVE loading w/ GNN | Reliability Eng. & System Safety 241 (2024) 109639 | `paperurl` wrong (points to a C&S PII) — fix |
| `2023-01-02-CGN.md` | Struct. dynamic responses w/ GNN | Computers & Structures 289 (2023) 107188 | PII likely correct — verify, keep if right |
| `2024-01-03-FGN.md` | Blast fragmentation RC slabs (GNN) | Engineering Structures 308 (2024) 118009 | `paperurl` (Eng.Struct PII) likely correct — verify |
| `2023-01-03-FTT.md` | GBDT→Transformer blast loading | Engineering Structures 276 (2023) 115310 | `paperurl` & `slidesurl` both wrong (point to MVD) — fix both |
| `2023-01-01-MVD.md` | Multi-view diffusion | IEEE TIP 32 (2023) 4610–4620 | OK — verify |
| `2024-01-01-MaskFormer.md` | Transformer semantic segmentation | Structural Health Monitoring 23.2 (2024) 1170–1183 | `paperurl` wrong (C&S PII; SHM is SAGE) — fix |

Also refresh each citation to full author list per CV (several currently say "Li, Qilin, et al.").

### New entries to add

**Top 10 (not yet on site):**
- Semisupervised learning on graphs with an alternating diffusion process — IEEE TNNLS 32.7 (2020) 2862–2874.
- Affinity learning via a diffusion process for subspace clustering — Pattern Recognition 84 (2018) 39–50.
- Structural damage detection and localization via an unsupervised anomaly detection method (Liu, Li Q., …) — Reliability Eng. & System Safety 252 (2024) 110465.
- Out-of-plane full-field vibration displacement measurement with monocular computer vision (Shao, …, Li Q., …) — Automation in Construction 165 (2024) 105507.
- Prediction of BLEVE blast loading using CFD and ANN (J. Li, Li Q., …) — Process Safety & Environmental Protection 149 (2021) 711–723.

**2024–2025 journal papers:**
- A multi-task ML approach for data-efficient prediction of blast loading — Engineering Structures 326 (2025) 119577.
- Advancements in 3D displacement measurement … monocular vision with moving cameras — Measurement 242 (2025) 116060.
- Robust 3D vessel trajectory monitoring … (Shao, …, Li Q., …) — Ocean Engineering 332 (2025) 121429.
- DIMMC: a 3D vision approach for structural displacement … moving camera (Shao, …, Li Q., …) — Engineering Structures 338 (2025) 120566.
- A probability-based risk assessment of secondary fragments … (Z. Wang, Li Q., …) — Structural Safety 114 (2025) 102565.
- Diffusion process with structural changes for subspace clustering (Zhu, Li Q., …) — Pattern Recognition 158 (2025) 111066.
- A novel exploration of diffusion process based on multi-type Galton–Watson forests (Zhu, Li Q., …) — Mathematics 12.22 (2024) 3462.
- Prediction and interpretability of accidental explosion loads from hydrogen-air mixtures … (Hu, …, Li Q., …) — Int. J. Hydrogen Energy 66 (2024) 135–147.
- Prediction of BLEVE-induced response of road tunnel using Transformer w/ modified self-attention (SAMT) (Cheng, …, Li Q.) — Engineering Structures 314 (2024) 118415.
- 3DGEN: a framework for generating custom-made synthetic 3D datasets for civil SHM (Shao, …, Li Q., …) — Structural Health Monitoring (2024).
- Structural damage identification using physics-guided residual neural networks (Wang, …, Li Q., …) — Engineering Structures 318 (2024) 118703.
- 3D displacement measurement using a single camera and mesh deformation neural network (Shao, …, Li Q., …) — Engineering Structures 318 (2024) 118767.
- Fragment prediction of RC wall under close-in explosion using Fragment Graph Network (FGN) (Z. Wang, Li Q., …) — Computers & Structures 305 (2024) 107556.
- 3D surface segmentation from point clouds via quadric fits based on DBSCAN clustering (Xie, …, Li Q.) — Pattern Recognition 154 (2024) 110589.

**Conference (`category: conferences`):**
- EdgeConvFormer: An Unsupervised Anomaly Detection Method for Multivariate Time Series (Liu, Li Q., …) — ICPR 2024, Springer, 367–382.

---

## 4. New "Research" page

### `_data/navigation.yml`
Insert a "Research" link after "Publications": **Publications · Research · Talks · Teaching · CV**.

### `_pages/research.md`
`layout: archive`, `permalink: /research/`, `author_profile: true`. Four sections (markdown headings + lists):

1. **Research Interests** — agentic AI & LLMs for infrastructure; vision-based structural health monitoring; data-driven structural dynamics & blast simulation (GNNs/Transformers); digital twins; ML surrogate modelling & graph/diffusion learning.

2. **Grants** (role · period · amount):
   - ARC DECRA — *Next-Generation Agentic AI System for Intelligent Infrastructure Monitoring* — Principal Investigator — 2026–2028 — **A$510,000**.
   - National Road Safety Action Grant (Dept. of Infrastructure/Transport) — *AI-Assisted Design of Sustainable Road Barriers* — CI — Mar 2025–Jun 2027 — **A$641,436**.
   - ARC Linkage — *Damage Detection & Quantification using Infrastructure Digital Twins* — CI — Aug 2024–Aug 2027 — **A$415,380**.
   - CSIRO Next Gen AI Graduate Program (w/ WA Police) — *Effective & Ethical Use of AI in Law Enforcement* — PI — Mar 2025–Jun 2029 — **A$350,000**.
   - Curtin Trailblazer EMCR Grant — *AI-Empowered Multi-Modality Digital Twin for Reclaimers* — PI — Jun 2025–Jun 2026 — **A$20,000**.
   - *(Note: CI on competitive grants totalling over A$2M.)*

3. **Awards & Honors:** ARC DECRA (2026); Trailblazer EMCR Grant (2025); Curtin Academy iSoLT Teaching Innovation Grant (2024); Third Prize, ICSHM 2022 international competition (2023); Chancellor's Commendation, PhD (2020); RTP Scholarship (2017); MPhil Commendation (2016).

4. **Academic Service:** Guest Editor — *Buildings* (2025) & *Mathematics* (2024–26); Early-Career Editorial Board — *Urban Lifeline* (2024–26); Organising Committee — CIMP1-2025; Reviewer for 20+ Q1 journals in AI/ML/SHM/structural engineering.

---

## 5. CV page fix (`_pages/cv.md`)

Replace the broken embed (`height="50px"`) with:
- A prominent **"Download CV (PDF)"** button/link to `/files/CV-Qilin.pdf` (reliable fallback; embeds fail on mobile).
- A full-height inline embed (`width="100%"`, `height` ~`1000px`) with fallback text/link for browsers that can't render it inline.

---

## 6. Cleanup (approved)

Delete leftover template demo content:
- `files/paper1.pdf`, `paper2.pdf`, `paper3.pdf`, `slides1.pdf`, `slides2.pdf`, `slides3.pdf`.
- `_posts/` demo posts (2012-08-14, 2013-08-14, 2014-08-14, 2015-08-14, 2199-01-01-future-post).
- `_portfolio/portfolio-1.md`, `_portfolio/portfolio-2.html`.
- Unused demo images in `images/` (e.g. `image-alignment-*`, `foo-bar-*`, `paragraph-*`, `3953273590_*`, `500x300.png`, `bio-photo*.jpg`, `editing-talk.png`, `profile.png`). Keep all images referenced by content (`Qilin-17-crop.png`, `FGN-flowchart.png`, `mvd-flowchart.png`, favicon/site-logo/manifest assets).

**Verify before deleting:** grep each candidate image for references; do not delete anything still referenced.

---

## Out of scope
- Visual/theme redesign, colors, fonts, layout changes.
- Blog/posts feature (nav stays without it).
- Teaching entries — left unchanged (ISEC2000 intentionally not added).
- Pre-2023 individual publications (covered by the Google Scholar link).

## Acceptance
- Site builds (Jekyll) with no broken Liquid/links.
- CV page shows a usable PDF + working download link.
- Publications page lists ~26 papers under correct categories with correct `paperurl`s (no duplicates/wrong links).
- Research page reachable from nav with grants/awards/service populated.
- Homepage shows News + updated Senior Lecturer bio + new photo.
- No template demo files remain; no content references a deleted asset.
