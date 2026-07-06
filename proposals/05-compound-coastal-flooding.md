# Project 5 — When Hazards Collide: Compound Coastal Flood Risk in West African Cities

**Joint extreme rainfall, storm tide and sea-level rise analysis for Lagos, Accra and Freetown**

| | |
|---|---|
| **Status** | New — replaces the global climate-emulator project |
| **Duration** | 36 months |
| **Budget** | $105,000 |
| **Study area** | Lagos, Accra, Freetown (low-lying coastal districts) |
| **Core methods** | Copula-based joint probability, tide-gauge and satellite altimetry analysis, reduced-complexity flood modelling, SLR scenario integration |
| **Primary partners** | Nigerian Institute of Oceanography, Ghana Meteorological Agency, Sierra Leone Maritime Administration, city planning authorities |

---

## 1. Why this project

The worst urban floods in coastal West Africa are rarely caused by one extreme. They happen when heavy monsoon rainfall lands on a city whose drainage outfalls are already backed up by a high spring tide or elevated coastal water levels — a **compound event**. Yet risk assessments for Lagos, Accra and Freetown treat rainfall and coastal water levels as independent hazards, which can underestimate joint flood probability severely; and sea-level rise steadily raises the baseline on which every future storm tide rides.

Compound-event research is one of the most active frontiers in climate science, but it is concentrated on well-instrumented coastlines in Europe, North America and Asia. For the Gulf of Guinea — home to some of the world's fastest-growing coastal megacities — the basic dependence structure between rainfall extremes and coastal water levels has never been quantified. This project fills that gap and converts it into planning-relevant flood maps.

This project replaces the previous portfolio's global interpretable climate-emulator project, which — while scientifically interesting — had no regional anchor, an XAI framing its own review found shaky, and no direct user in West Africa.

## 2. Research questions

1. What is the statistical dependence between extreme rainfall and elevated coastal water levels (tide + surge) at Lagos, Accra and Freetown, and through which synoptic mechanisms does it arise?
2. How much higher is the true joint flood probability than the independence assumption implies — today, and under sea-level-rise scenarios to 2100?
3. Which districts face the largest compound-flood exposure, and how do adaptation levers (drainage upgrades, outfall gates, setback zones) change the risk surface?

## 3. Data

- **Coastal water levels:** GESLA-3 and national tide gauges (Lagos has ~century-scale fragments; Takoradi/Tema for Ghana), satellite altimetry (Copernicus), global tide+surge reanalysis (GTSR/CoDEC) to extend records.
- **Rainfall:** as in Projects 1–3 — gauges, IMERG, CHIRPS; consistent event catalogues shared across the portfolio.
- **Sea-level rise:** IPCC AR6/successor regional projections (medium and low-confidence high-end scenarios).
- **Topography/exposure:** FABDEM (forest-and-buildings-removed DEM), Open Buildings footprints, WorldPop population, drainage network data from city authorities.

## 4. Methodology

**WP1 — Event catalogues and dependence (months 1–14).** Build quality-controlled joint catalogues of rainfall and water-level extremes; measure tail dependence with rank correlations and extremal coefficients; fit bivariate copulas (with model selection and bootstrap uncertainty). Composite the synoptic conditions behind observed compound events to establish the physical mechanism, not just the statistic. **Decision gate (month 10):** where gauge records are too short, substitute the GTSR-reanalysis-driven analysis and state the added uncertainty explicitly.

**WP2 — Joint return periods under SLR (months 10–22).** Compute joint return periods ("100-year rainfall coinciding with 20-year water level") under observed dependence vs independence; propagate SLR scenarios as a nonstationary baseline shift; import Project 1's non-stationary rainfall parameters so both drivers evolve consistently.

**WP3 — Flood mapping (months 16–30).** Reduced-complexity inundation modelling (LISFLOOD-FP class on FABDEM) for a design-event matrix per city; overlay population and building exposure; rank districts by compound-flood exposure now / 2050 / 2100.

**WP4 — Planning uptake (months 24–36).** Scenario workshops with city planning authorities testing adaptation levers in the model; deliver district-level compound-risk atlases and an open methods toolkit.

## 5. Risks and decision gates

| Risk | Likelihood | Mitigation |
|---|---|---|
| Tide-gauge records short/gappy | High | GTSR/CoDEC reanalysis + altimetry extension; month-10 gate per city |
| Dependence turns out weak | Possible | A quantified near-independence result is itself decision-relevant and publishable |
| Hydrodynamic modelling scope creep | Moderate | Reduced-complexity model class fixed at proposal stage; no 2D urban drainage simulation |
| Drainage data unavailable | Moderate | DEM-based pluvial proxy; documented as limitation |

**Minimum viable thesis:** dependence structure + joint return periods for two cities, no flood mapping — 2 papers.

## 6. Outcomes

- Peer-reviewed papers (2–3): first Gulf of Guinea compound-event dependence analysis; joint return periods under SLR; compound-flood exposure atlas.
- **District-level compound-flood risk atlases** for three cities (open, versioned).
- Open joint event catalogues and copula toolkit (Zenodo/GitHub).
- Direct input to Lagos and Freetown resilience/drainage master-planning processes.

## 7. Fit in the portfolio

Consumes Project 1's non-stationary rainfall statistics and shares event catalogues with Projects 2–3, closing the portfolio's logic: design standards (P1), warnings (P2, P4), forecast skill (P3), and long-range planning (P5) — all four decision horizons covered.
