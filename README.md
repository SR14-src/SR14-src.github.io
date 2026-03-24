# SR14-src.github.io

Personal portfolio website for **Sonia Raj** — AI/ML Engineer & Researcher.

Live at: [https://sr14-src.github.io](https://sr14-src.github.io)

---

## File overview

The entire site lives in a single self-contained file:

```
index.html   ← HTML + CSS + JavaScript, no build step required
```

---

## What `index.html` contains

### Head
- UTF-8 charset, responsive viewport meta tag
- Page title: `Sonia Raj — AI/ML Engineer`
- Google Fonts: **Syne** (headings) and **Inconsolata** (body / monospace)
- All CSS written inline inside a `<style>` block — no external stylesheet

### CSS design system
| Variable | Value | Purpose |
|---|---|---|
| `--bg` | `#080c10` | Page background |
| `--surface` / `--surface2` | dark greys | Card / panel backgrounds |
| `--teal` | `#00d4b4` | Accent colour throughout |
| `--text` / `--dim` / `--muted` | light greys | Text hierarchy |

A subtle teal grid is rendered as a CSS `background-image` on `body::before` for visual depth.

### Custom cursor
Two elements (`div.cursor` + `div.cursor-ring`) replace the default OS cursor:
- `.cursor` — small filled dot that follows the mouse exactly.
- `.cursor-ring` — larger lagging ring driven by a `requestAnimationFrame` animation loop with easing (`rx += (mx - rx) * 0.12`).

### Navigation (`<nav>`)
Fixed top bar with:
- Logo: `Sonia.Raj()`
- Links to page sections: **Experience**, **Projects**, **Publications**, **Contact**
- Hidden on screens narrower than 600 px.

### Hero section
Two-column grid (collapses to one column on mobile):
- **Left column** — name, tagline, brief bio, key stats (CGPA, publications, location), and two CTA buttons (*View Projects* / *Get in Touch*).
- **Right column** — a decorative mock terminal window (`div.hero-terminal`) styled like a macOS terminal, showing a `cat profile.json` output with key facts. Hidden on screens narrower than 900 px.

### Experience section (`#experience`)
Three work entries rendered as a vertical card list:
1. **AMC Engineering College** — Assistant Professor (Oct 2025 – Present)
2. **Altair (Siemens), Bangalore** — Software Development Intern (Jun 2024 – Aug 2025)
3. **Inventeron Technologies** — Machine Learning Intern (Jul 2021 – Sep 2021)

### Projects section (`#projects`)
Responsive CSS grid of four project cards:
1. **Multimodal CV Risk Prediction** — ResNet152, medical AI
2. **HashFinance — Agentic Assistant** — Gemini, MCP, GCP
3. **LECOP GPU Parallelization** — CUDA, 13.9× speedup
4. **Driver Drowsiness Detection** — CNN, OpenCV, real-time video

Each card has a hover effect that draws a teal left-border accent via a CSS `::before` pseudo-element.

### Skills section (`#skills`)
Six skill groups rendered as chip grids:
- **Languages** — Python, C, C++
- **ML / DL** — PyTorch, Scikit-learn, RapidMiner, LangChain
- **AI & GenAI** — LLMs, Agentic AI, RAG, Gemini
- **Systems** — CUDA, MPI, Git, Docker
- **Databases** — SQL, MongoDB
- **Deployment** — FastAPI, Google Cloud, ReactJS

### Publications section (`#publications`)
Three peer-reviewed publications listed chronologically (newest first):
1. *Parallelisation of Local Extrema Co-occurrence Pattern…* — MiRI, 2026
2. *Navigating Evolving Vehicle NVH Challenges…* — SAE NVH Conference, 2025
3. *Multimodal Deep Learning in Medical Diagnostics…* — Bentham Science, 2024

### Contact section (`#contact`)
Centred call-to-action with links to email, phone, LinkedIn, and GitHub.

### Footer
Simple two-column footer: copyright notice and a teal tagline.

---

## JavaScript (inline `<script>`)

Three small, dependency-free scripts:

| Script | What it does |
|---|---|
| **Custom cursor** | `mousemove` listener + `requestAnimationFrame` loop to move `.cursor` (exact) and `.cursor-ring` (lagging easing) |
| **Scroll reveal** | `IntersectionObserver` adds `.visible` to every `.reveal` element as it enters the viewport, triggering a CSS fade-up transition |
| **Typewriter** | Cycles through three terminal command phrases, typing and erasing them character-by-character inside `#typewriter` |

---

## Responsive breakpoints

| Max-width | Changes |
|---|---|
| `900px` | Hero becomes single column; terminal widget hidden |
| `600px` | Nav links hidden; padding reduced; footer stacks vertically |

---

## Deployment

Because there is no build step, the site can be served directly by GitHub Pages from the repository root. Push to the default branch and GitHub Pages will serve `index.html` automatically.
