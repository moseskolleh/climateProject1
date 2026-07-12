# West Africa Climate Risk Research Agenda

Ten PhD-level research proposals that turn climate science into decisions in West Africa — warnings, design standards, forecasts and plans across cities, farms, grids and health systems.

**🌍 Website:**[ https://moseskolleh.github.io/climateproject1/](https://moseskolleh.github.io/climateProject1/) *(GitHub Pages — see [Enabling the website](#enabling-the-website))*

## The portfolio

Every project answers a decision-maker's question, targets a West African user, and defines a minimum viable thesis with explicit decision gates and fallbacks.

| # | Project | One-line pitch | Duration | Budget |
|---|---------|----------------|----------|--------|
| 1 | [Climate-Proof Rainfall Design Standards](proposals/01-extreme-rainfall-design-standards.md) | Non-stationary extreme-value statistics turned into the IDF curves and design tables engineers in Lagos, Accra and Freetown actually use | 30 mo | $75k |
| 2 | [Landslide Early Warning for Freetown](proposals/02-landslide-early-warning.md) | Bias-corrected susceptibility mapping coupled with rainfall thresholds into an operational warning system for Sierra Leone's NDMA | 42 mo | $135k |
| 3 | [Do AI Weather Models Work for West Africa?](proposals/03-ai-downscaling-west-africa.md) | The first systematic benchmark of AI weather models for the West African monsoon, plus generative km-scale downscaling | 36 mo | $110k |
| 4 | [Humid Heat & Health in Freetown](proposals/04-humid-heat-health-warning.md) | A 50-sensor humid-heat network powering an impact-based heat-health warning system co-run with Freetown City Council | 30 mo | $90k |
| 5 | [Compound Coastal Flood Risk](proposals/05-compound-coastal-flooding.md) | First quantification of rainfall × storm-tide dependence for Gulf of Guinea megacities, with sea-level rise and district risk atlases | 36 mo | $105k |

### Extension track

Five further projects that extend the portfolio into agriculture, attribution science, nowcasting, energy and air quality — each reusing the core portfolio's methods, data and partners.

| # | Project | One-line pitch | Duration | Budget |
|---|---------|----------------|----------|--------|
| 6 | [When to Plant: Planting-Window Forecasts](proposals/06-planting-window-forecasts.md) | The first systematic skill, calibration and value analysis of subseasonal monsoon-onset and dry-spell forecasts for smallholder planting decisions | 36 mo | $85k |
| 7 | [Whose Weather? Extreme-Event Attribution](proposals/07-extreme-event-attribution.md) | A validated rapid-attribution capability for the world's most under-attributed region, built for the loss-and-damage era | 36 mo | $80k |
| 8 | [Six Hours Ahead: Satellite-Only Nowcasting](proposals/08-satellite-nowcasting.md) | Deep-learning nowcasting of extreme rain from geostationary satellites — the only nowcasting path for a radar-sparse continent | 36 mo | $95k |
| 9 | [Powering Through: Hydropower Inflow Risk](proposals/09-hydropower-climate-risk.md) | Non-stationary inflow and firm-energy analysis for Akosombo, Kainji and Bumbuna — the dams that anchor national grids | 36 mo | $90k |
| 10 | [Breathing the Harmattan: Dust & Health](proposals/10-harmattan-dust-health.md) | Ground-truthed verification of operational dust forecasts and a co-designed dust-health advisory pilot in three cities | 30 mo | $75k |

**Recommended starting project: #1** — shortest timeline, lowest budget, established methods with a genuine frontier element, and the clearest path from result to real-world change. **Recommended first extension: #6** — it fills the portfolio's agriculture gap and reaches the most people per dollar.

## How the portfolio fits together

The ten projects cover every decision horizon of climate risk with shared data and methods:

- **Decades ahead — build and plan:** design standards (P1), compound-flood planning (P5), hydropower and energy planning (P9)
- **Weeks ahead — decide:** planting-window forecasts for agriculture (P6)
- **Days ahead — warn people:** landslide warnings (P2), heat-health warnings (P4), dust-health advisories (P10)
- **Hours ahead — act:** satellite-only nowcasting of extreme rain (P8)
- **The forecast engine underneath:** AI-model skill and downscaling (P3)
- **Looking back — was it climate change?** rapid extreme-event attribution (P7)

The connections are deliberate: P1's non-stationary rainfall statistics feed P5, P7 and P9; P2, P3, P5 and P8 share extreme-rainfall event catalogues; P3 and P8 share verification and GPU infrastructure at different lead times; P4 and P10 share the low-cost-sensor and health-partnership playbook; P8's nowcasts are the trigger layer for P2's and P4's warnings.

## What changed in the rethink

This repository previously held five proposals plus several rounds of review documents. The 2026 redesign rebuilt the portfolio around one test — *does this change a decision in West Africa?* — and around what is scientifically current:

- **Kept and sharpened:** extreme-precipitation EVT (now Project 1, the flagship).
- **Evolved:** landslide susceptibility mapping became a full early warning system (P2); urban heat island mapping became a humid-heat health warning system (P4) — in both cases the static map was demoted from deliverable to input.
- **Replaced:** classical CMIP6 statistical downscaling (48 months, $140k, HPC-gated) → AI weather-model evaluation and generative downscaling (P3); the global interpretable climate emulator (no regional user, shaky XAI framing) → compound coastal flood risk (P5).
- **Removed:** the overlapping review/comparison/presentation documents. They are preserved under [`archive/`](archive/) for provenance.
- **Extended:** five further projects (P6–P10) were added after the redesign, applying the same decision-first test to agriculture, attribution, nowcasting, energy and air quality.

## Repository structure

```
├── README.md                  # This file
├── proposals/                 # The ten current proposals (one file each)
├── docs/                      # GitHub Pages website source
├── archive/                   # Superseded 2025 proposals and review documents
└── LICENSE                    # MIT
```

## Enabling the website

The site is a self-contained static page in [`docs/`](docs/). To publish it:

1. Merge this branch into `main`.
2. In the repository settings, open **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*, choose branch **`main`** and folder **`/docs`**, then save.

GitHub serves it at `https://moseskolleh.github.io/climateproject1/` within a couple of minutes. (Alternatively, the included workflow in `.github/workflows/pages.yml` deploys automatically on every push to `main` if you set the Pages source to *GitHub Actions* instead.)

## Funding targets

CREWS · Adaptation Fund · WASCAL Graduate Studies Program · UKRI (international development schemes) · NORAD · Wellcome Trust (climate & health, for P4/P10) · African Development Bank ClimDev special fund · Green Climate Fund readiness (P7/P9) · CGIAR/AICCRA (P6) · World Bank ESMAP (P9)

## Open science

All projects commit to FAIR outputs: datasets on Zenodo (CC-BY-4.0), code on GitHub (MIT), preprints on EarthArXiv, and operational tools hosted with regional institutions (ACMAD/WASCAL) for sustainability beyond the PhD.

## License

MIT — see [LICENSE](LICENSE).
