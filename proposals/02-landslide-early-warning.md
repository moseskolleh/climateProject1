# Project 2 — From Maps to Warnings: A Landslide Early Warning System for Freetown

**Coupling bias-corrected susceptibility mapping with rainfall thresholds to build an operational early warning capability for Sierra Leone**

| | |
|---|---|
| **Status** | Core — evolved from the previous static susceptibility project |
| **Duration** | 42 months |
| **Budget** | $135,000 |
| **Study area** | Freetown Peninsula, Sierra Leone (transferable nationally) |
| **Core methods** | Ensemble ML with sampling-bias correction, rainfall intensity–duration thresholds, satellite precipitation nowcasting |
| **Primary partners** | National Disaster Management Agency (NDMA), Sierra Leone Meteorological Agency, Njala University |

---

## 1. Why this project

The August 2017 Regent landslide killed more than 1,100 people in Freetown. Rapid unplanned hillside settlement, deforestation and intensifying rainfall make a repeat event a question of *when*, not *if*. Susceptibility maps alone do not save lives — people cannot evacuate a map. What Sierra Leone lacks is the coupling of **where** slopes can fail (susceptibility) with **when** they are likely to (rainfall thresholds), delivered as actionable warnings through an agency with a mandate to act.

This project's predecessor treated the dynamic warning component as an optional add-on. The rethink inverts that: **the early warning system is the deliverable**, and the susceptibility map is one input to it.

## 2. Research questions

1. Can spatial point-process modelling correct the road-and-settlement sampling bias that contaminates landslide inventories in data-sparse tropical regions — demonstrated first on synthetic data where the true susceptibility is known?
2. What rainfall intensity–duration thresholds discriminate landslide-triggering storms from non-triggering ones on the Freetown Peninsula, and how much skill do satellite precipitation products (IMERG early-run) retain at those thresholds?
3. What warning lead time and false-alarm rate can a coupled susceptibility × threshold system achieve, and is that operationally acceptable to NDMA?

## 3. Data

- **Landslide inventory:** multi-source compilation (field mapping, Sentinel-2/PlanetScope change detection, historical reports, community mapping), target 300–800 events with date control for a triggering subset.
- **Predictors:** SRTM/Copernicus DEM derivatives, geology, soil, land cover (ESA WorldCover), road/settlement proximity.
- **Rainfall:** IMERG (early and final runs), CHIRPS, national gauges; logger gauges installed at 5 field sites for validation.
- **Field campaigns:** two dry-season campaigns, 80–100 validation sites (power-analysis-determined), soil sampling for 20 sites.

## 4. Methodology

**WP1 — Bias correction, proven on synthetic data first (months 1–8).** Generate synthetic landscapes with known susceptibility and imposed observation bias; verify the point-process correction recovers truth before touching real data. This closes the circularity critique of earlier designs. **Decision gate (month 8):** if correction fails on synthetics, fall back to buffer-based pseudo-absence sampling with explicit bias caveats.

**WP2 — Ensemble susceptibility mapping (months 6–18).** Random Forest, XGBoost and MaxEnt ensemble on the corrected inventory; spatially blocked cross-validation; uncertainty maps from ensemble disagreement. Factor-of-Safety physics screening used as an *exploratory plausibility check*, not validation.

**WP3 — Rainfall thresholds (months 12–26).** Build a dated triggering-storm catalogue; fit intensity–duration thresholds with logistic/Bayesian methods quantifying the false-alarm/missed-event trade-off; test how threshold skill degrades from gauge to IMERG early-run (the product actually available in near-real-time).

**WP4 — Prototype warning system (months 22–38).** Couple susceptibility classes with threshold exceedance into a three-tier advisory (watch/warning/evacuate-priority zones). Run a shadow-mode trial through one full rainy season, scoring every alert against observed events. Co-design alert protocols with NDMA and community wards.

**WP5 — Field validation (two dry seasons, months 10–14 and 22–26).** 80–100 sites, two local assistants per campaign, weather contingency built in. Backup study area (Limbe, Cameroon) if site access fails.

## 5. Risks and decision gates

| Risk | Likelihood | Mitigation |
|---|---|---|
| Bias correction fails on synthetics | Moderate | Month-8 gate → pseudo-absence fallback |
| Too few dated landslides for thresholds | Moderate | Regional threshold transfer (West African analogue catalogues) as prior |
| IMERG latency/skill inadequate | Moderate | Gauge-telemetry hybrid; document skill honestly — a negative result here is publishable |
| Field access disruption | Low–moderate | Two seasons, backup location, NDMA logistics MOU signed before start |

**Minimum viable thesis:** validated bias-corrected susceptibility map plus a threshold analysis, even if the operational trial is curtailed — 2 papers.

## 6. Outcomes

- Peer-reviewed papers (2–3): sampling-bias correction method; Freetown rainfall thresholds; shadow-trial evaluation.
- **Operational prototype handed to NDMA** with documented protocols and training workshops.
- Open landslide inventory and susceptibility layers (Zenodo, CC-BY).

## 7. Fit in the portfolio

Highest direct life-safety impact. Shares rainfall-extremes infrastructure with Project 1 and nowcasting components with Project 3, and its warning-protocol design feeds Project 4's heat-health system.
