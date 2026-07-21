# STIG · NIST Viewer

**Navigate NIST SP 800-53, DISA STIGs, DoD Zero Trust, and RMF/cATO for a classified AI lab — in one offline-friendly SPA.**

[![Live demo](https://img.shields.io/badge/demo-github.io-38bdf8?style=flat-square)](https://aaronmeis.github.io/stig-nist-viewer/)
[![License: MIT](https://img.shields.io/badge/license-MIT-a78bfa?style=flat-square)](LICENSE)
[![HTML](https://img.shields.io/badge/stack-single%20file%20SPA-111a2e?style=flat-square)](#)

### Live site

**https://aaronmeis.github.io/stig-nist-viewer/**

---

## Why this exists

Security packages for aerospace / defense AI labs span many documents at once:

| Stack | Role |
|--------|------|
| **NIST SP 800-53 Rev 5** | Control catalog (~1,193+ controls, 20 families) |
| **DISA STIGs / SRGs** | Product baselines derived from 800-53 |
| **DoD Zero Trust** | Seven-pillar architecture lens |
| **RMF / cATO** | Authorization and continuous monitoring |

This viewer turns a **Classified AI Lab data-architecture deep dive** into a searchable, cross-linked navigator — optimized for briefings, package building, and assessor prep, not as a replacement for official STIG XML or the full NIST catalog.

**Design constraint baked in:** *no data leaves the lab* (high-side / air-gap posture).

---

## Features

| View | What you get |
|------|----------------|
| **Overview** | Counts, constraint banner, quick paths |
| **Architecture layers** | Ingress → updates → train/infer → security → hybrid → lifecycle |
| **NIST families** | All 20 SP 800-53 Rev 5 families; lab-critical filter |
| **Key controls** | Curated controls with lab notes, verify steps, severity |
| **DISA STIGs** | OS, Kubernetes, Container Platform, App SRG, Boundary/CDS |
| **Zero Trust** | Seven DoD pillars → mapped controls |
| **Crosswalk** | Mission need → NIST → STIG → ZT |
| **RMF & cATO** | Seven RMF steps + continuous ATO guidance |
| **Assessor checklist** | Evidence items with progress saved in `localStorage` |

### UX

- Instant **search** (`/` focuses the box)
- **Detail drawer** with cross-links (control ↔ family ↔ STIG ↔ pillar ↔ layer)
- Severity and family **filters**
- **No build, no backend, no API keys** — open the HTML file or use GitHub Pages
- Dark, dense layout suited to compliance work

---

## Quick start (local)

```powershell
# clone
git clone https://github.com/aaronmeis/stig-nist-viewer.git
cd stig-nist-viewer

# open in browser (Windows)
start index.html
```

Or simply double-click `index.html`. No Node, Python, or Docker required.

---

## Repository layout

```
stig-nist-viewer/
├── index.html      # Entire SPA (UI + data + logic)
├── README.md
├── LICENSE
└── .nojekyll       # GitHub Pages: serve files as-is
```

All catalog data is embedded in `index.html` so the page stays portable for air-gapped demos.

---

## Source material

Structured from:

> **Classified AI Lab Data Architecture: Design, Compliance, and Lifecycle Framework**  
> (PDF/MD deep dive — NIST · DISA STIG · Zero Trust · RMF · NCDSMO/diode · lifecycle)

Themes covered in the map:

- Cross Domain Solutions / data diodes / CDR  
- Air-gap DevSecOps & SBOM pipelines  
- Kubernetes & container STIG compliance  
- Workload segmentation (training vs inference)  
- IL5/IL6 hybrid cloud constraints  
- NSA PM 9-12 / NISPOM media sanitization  

---

## Keyboard shortcuts

| Key | Action |
|-----|--------|
| `/` | Focus search |
| `Esc` | Close detail panel |

---

## What this is *not*

- Not an official DISA STIG content dump or XCCDF browser  
- Not a complete NIST 800-53 control export  
- Not legal or accreditation advice — use with your ISSO/AO and current STIGs from [cyber.mil](https://www.cyber.mil/stigs/)

For production assessments, always pull the current STIG releases and your organization’s overlays (e.g. MAC-2 Classified).

---

## GitHub Pages

This repo is published from the `main` branch root:

| | |
|--|--|
| **URL** | https://aaronmeis.github.io/stig-nist-viewer/ |
| **Source** | `main` → `/` (Deploy from branch) |

After a push to `main`, Pages usually updates within a minute or two.

---

## Contributing / extending

Ideas that fit cleanly:

1. Import a STIG XCCDF/ZIP and merge rule IDs into the control cards  
2. Add more lab-specific controls (e.g. full Kubernetes STIG rule set)  
3. Export assessor checklist progress as JSON  
4. Optional light theme toggle  

PRs welcome. Keep the single-file (or zero-build) story unless there is a strong reason to split.

---

## License

MIT — see [LICENSE](LICENSE).  
NIST, DISA, and DoD names are used for descriptive reference only; this project is not affiliated with NIST, DISA, or the U.S. Department of Defense.
