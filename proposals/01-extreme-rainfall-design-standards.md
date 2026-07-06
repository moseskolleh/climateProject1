# Project 1 — Climate-Proof Rainfall Design Standards for West African Coastal Cities

**Non-stationary extreme value analysis of precipitation for engineering practice in Lagos, Accra and Freetown**

| | |
|---|---|
| **Status** | Flagship — highest priority |
| **Duration** | 30 months |
| **Budget** | $75,000 |
| **Study area** | Lagos, Accra, Freetown |
| **Core methods** | Non-stationary GEV, CORDEX-Africa / CMIP6, bootstrap uncertainty |
| **Primary partners** | National met services, city drainage authorities, professional engineering bodies |

---

## 1. Why this project

Drainage systems, culverts, bridges and flood defences across coastal West Africa are designed against rainfall statistics computed from mid-20th-century records under the assumption that the climate is stationary. It is not. Warming increases atmospheric moisture at roughly 7% per °C (Clausius–Clapeyron), and observed daily rainfall extremes in the region are already intensifying. Every structure designed today against a stationary "100-year storm" is quietly under-designed for the climate it will actually live in.

The gap is not awareness — engineers know the climate is changing — it is the absence of **usable, defensible numbers**: updated intensity–duration–frequency (IDF) values and return-level tables with quantified uncertainty, delivered in the format design codes require.

## 2. Research questions

1. How are the parameters of extreme daily and sub-daily precipitation distributions in Lagos, Accra and Freetown changing as a function of global mean surface temperature (GMST)?
2. What are the projected 10-, 25-, 50- and 100-year return levels for 2030–2100 under SSP2-4.5 and SSP5-8.5, with credible uncertainty intervals?
3. How large is the resulting under-design margin in current national drainage standards, and what climate-adjustment factors would correct it?

## 3. Data

- **Observations:** daily gauge records from GHCN-Daily and national met services (target ≥40 years per city); sub-daily records where archives permit; IMERG and CHIRPS as gridded cross-checks.
- **Models:** CORDEX-Africa RCM ensemble (0.22°) screened by a validation gate on extreme-rainfall statistics; CMIP6 GCMs as a supplementary line of evidence when fewer than four RCMs pass.
- **Covariate:** observed and projected GMST (HadCRUT5; CMIP6 ensemble means), the standard covariate for physically interpretable non-stationary scaling.

## 4. Methodology

**WP1 — Observed non-stationarity (months 1–8).** Fit stationary and non-stationary GEV models to annual maxima per city. The **primary model varies location μ(GMST) and scale σ(GMST) with shape ξ held constant** — the configuration that is statistically stable at typical record lengths. Fully non-stationary ξ(GMST) is tested as an exploratory model only, retained solely if AIC improves by >10 and bootstrap standard errors stay below 50% of the estimate.

**WP2 — Model screening and projection (months 6–18).** Validation gate: an RCM is retained only if it reproduces observed extreme-rainfall climatology within pre-registered tolerances. Fallback ladder if fewer than four models pass: (a) relax the threshold with documented sensitivity analysis; (b) supplement with CMIP6 GCMs; (c) minimum viable ensemble of one best RCM plus three GCMs with widened uncertainty.

**WP3 — Return levels and design tables (months 14–24).** Project return levels along GMST trajectories per scenario. Quantify uncertainty by pooling bootstrap parameter uncertainty with ensemble spread. Translate into the two artefacts engineers actually use: **updated IDF curves** and **climate-adjustment factors** (multipliers on current design values) with recommended safety margins.

**WP4 — Uptake (months 20–30).** Co-design the outputs with practising civil engineers via two workshops per city (engineering bodies, drainage authorities, met services). Publish a lightweight open web tool serving the design tables, hosted with a regional institution (ACMAD/WASCAL) for sustainability beyond the project.

## 5. Risks and decision gates

| Risk | Likelihood | Mitigation |
|---|---|---|
| Gauge records too short/gappy | Moderate | Regional frequency analysis pooling nearby stations; satellite-era blending |
| <4 RCMs pass validation gate | Moderate | Pre-registered fallback ladder (WP2) |
| ξ(GMST) unstable | High (expected) | Not on critical path — primary model excludes it by design |
| Engineering uptake stalls | Moderate | Engineers engaged from month 1, not month 24; deliverables in code-ready format |

**Minimum viable thesis:** observed non-stationarity analysis (WP1) plus single-scenario projections with design tables for one city — publishable and useful on its own.

## 6. Outcomes

- Peer-reviewed papers (target 2–3): observed non-stationary scaling in coastal West Africa; projected return levels and design implications.
- **Open design-table dataset and IDF curves** (Zenodo, CC-BY) for three cities.
- Climate-adjustment factors submitted to national standards bodies.
- Open-source analysis pipeline (R/`extRemes` + Python).

## 7. Why it leads the portfolio

Shortest timeline, lowest budget, most established methods with a genuine frontier element (multi-parameter non-stationarity), and the clearest impact pathway in the portfolio: a number in a design table changes what gets built.
