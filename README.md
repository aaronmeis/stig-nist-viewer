# STIG · NIST Viewer

**A learning resource** for navigating NIST SP 800-53, DISA STIGs, DoD Zero Trust, and RMF/cATO concepts using a generic classified AI lab scenario.

[![Live demo](https://img.shields.io/badge/demo-github.io-38bdf8?style=flat-square)](https://aaronmeis.github.io/stig-nist-viewer/)
[![License: MIT](https://img.shields.io/badge/license-MIT-a78bfa?style=flat-square)](LICENSE)
[![Learning resource](https://img.shields.io/badge/type-learning%20resource-34d399?style=flat-square)](#learning-resource)
[![HTML](https://img.shields.io/badge/stack-single%20file%20SPA-111a2e?style=flat-square)](#)

### Live site

**https://aaronmeis.github.io/stig-nist-viewer/**

---

## Learning resource

This project is an **educational / study aid** only.

| It is | It is not |
|--------|-----------|
| A way to explore how NIST, STIGs, Zero Trust, and RMF relate | Official NIST, DISA, or DoD guidance |
| A generic lab scenario for self-study and literacy | An accreditation package or ATO artifact |
| Offline-friendly and company-agnostic | Affiliated with any employer, contractor, or product vendor |

Standards names (NIST, DISA, DoD, Kubernetes, and similar) appear for **descriptive, educational reference** only. No company branding, employer content, or proprietary material is included.

**Not legal, security, or accreditation advice.** For real assessments, use current publications from [NIST](https://csrc.nist.gov/), [cyber.mil STIGs](https://www.cyber.mil/stigs/), and your authorizing officials.

---

## Why it exists

Compliance literacy for air-gapped / high-side AI environments means holding several frameworks in mind at once:

| Stack | Role in the study map |
|--------|------------------------|
| **NIST SP 800-53 Rev 5** | Control catalog (~1,193+ controls, 20 families) |
| **DISA STIGs / SRGs** | Product baselines derived from 800-53 |
| **DoD Zero Trust** | Seven-pillar architecture lens |
| **RMF / cATO** | Authorization and continuous monitoring concepts |

The SPA uses a **fictional, generic classified AI lab** with a *data-in / no-data-out* scenario constraint so learners can cross-link families, STIG stacks, and Zero Trust pillars without wading through full official catalogs.

---

## Features

| View | What you get |
|------|----------------|
| **Overview** | Counts, learning disclaimer, quick paths, featured diagram |
| **Diagrams** | Inline SVG maps: compliance stack, air-gap flow, RMF, Zero Trust, workloads |
| **Architecture layers** | Ingress → updates → train/infer → security → hybrid → lifecycle |
| **NIST families** | All 20 SP 800-53 Rev 5 families; lab-critical study filter |
| **Key controls** | Curated controls with scenario notes and verify prompts |
| **DISA STIGs** | OS, Kubernetes, Container Platform, App SRG, Boundary/CDS |
| **Zero Trust** | Seven DoD pillars → mapped controls |
| **Crosswalk** | Scenario need → NIST → STIG → ZT |
| **RMF & cATO** | Seven RMF steps + continuous ATO study notes |
| **Study checklist** | Common evidence themes (`localStorage` progress) |

### UX

- Instant **search** (`/` focuses the box)
- **Detail drawer** with cross-links (control ↔ family ↔ STIG ↔ pillar ↔ layer)
- Severity and family **filters**
- **No build, no backend, no API keys** — open the HTML file or use GitHub Pages
- Dark layout suited to dense reference reading

---

## Quick start (local)

```powershell
git clone https://github.com/aaronmeis/stig-nist-viewer.git
cd stig-nist-viewer
start index.html
```

Or double-click `index.html`. No Node, Python, or Docker required. Works offline.

---

## Repository layout

```
stig-nist-viewer/
├── index.html      # Entire SPA (UI + embedded study data + logic)
├── README.md
├── LICENSE
└── .nojekyll       # GitHub Pages: serve files as-is
```

All study data is embedded in `index.html` so the page stays portable for offline demos.

---

## Scenario themes (educational)

The map covers common **public-domain** compliance and architecture themes, including:

- Cross Domain Solutions / data diodes / content disarm concepts  
- Air-gap update pipelines and software bill of materials (SBOM)  
- Kubernetes and container hardening themes aligned with STIG/SRG ideas  
- Workload segmentation (training vs inference)  
- Impact Level (IL) cloud concepts at a high level  
- Media sanitization concepts (e.g. public NSA / NISPOM-oriented practice themes)

No proprietary processes, customer data, or organization-specific policy is included.

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
- Not legal, contractual, or accreditation advice  
- Not affiliated with NIST, DISA, DoD, or any private company  

For production work, always pull current STIG releases and your organization’s approved overlays.

---

## GitHub Pages

| | |
|--|--|
| **URL** | https://aaronmeis.github.io/stig-nist-viewer/ |
| **Source** | `main` branch → `/` |

Pushes to `main` refresh the site after GitHub finishes the Pages build.

---

## Extending (optional)

Ideas that fit a learning resource:

1. Import public STIG XCCDF samples for rule-ID study cards  
2. Add more scenario controls (e.g. deeper Kubernetes themes)  
3. Export study-checklist progress as JSON  
4. Optional light theme  

Keep the zero-build story unless there is a strong reason to split the file.

---

## License

MIT — see [LICENSE](LICENSE).

NIST, DISA, DoD, and related names are used for educational reference only. This project is **not affiliated with** NIST, DISA, the U.S. Department of Defense, or any commercial employer or vendor.
