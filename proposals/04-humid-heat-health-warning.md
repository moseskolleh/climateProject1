# Project 4 — Humid Heat and Health in Freetown: An Impact-Based Early Warning System

**From urban heat maps to operational heat-health warnings for a tropical coastal city**

| | |
|---|---|
| **Status** | New — absorbs and supersedes the urban heat island mapping project |
| **Duration** | 30 months |
| **Budget** | $90,000 |
| **Study area** | Freetown, Sierra Leone |
| **Core methods** | Dense low-cost sensor network, humid-heat metrics (WBGT/wet-bulb), ERA5-Land bias correction, impact-based warning thresholds |
| **Primary partners** | Freetown City Council (incl. the Chief Heat Officer's office), Ministry of Health, Sierra Leone Met Agency, community-based organisations |

---

## 1. Why this project

Freetown appointed Africa's first Chief Heat Officer because heat is already its most pervasive climate hazard — and the dangerous variable in a tropical coastal city is not temperature but **humid heat**. Wet-bulb globe temperatures in informal settlements with corrugated-metal roofing routinely enter ranges where labour capacity collapses and heat illness rises, yet the city has no heat-warning system, no heat-action plan triggers, and no measurements inside the settlements where exposure is worst.

The predecessor project aimed to map land-surface temperature from Landsat. The rethink drops what didn't survive review — persistent cloud cover destroys tropical thermal time series, LST is not the exposure humans feel, and hospital data access was a coin-flip — and keeps what mattered: dense ground measurement. The deliverable is no longer a map; it is **a working warning system with an action plan attached**.

## 2. Research questions

1. What is the intra-urban distribution of humid heat (WBGT, wet-bulb temperature) across Freetown's housing types and topography, measured directly rather than inferred from satellite LST?
2. Can bias-corrected ERA5-Land plus the sensor network yield reliable 1–5-day forecasts of neighbourhood-scale dangerous-heat episodes?
3. What warning thresholds and communication channels actually change protective behaviour in informal settlements — tested through a co-designed pilot season?

## 3. Data

- **Sensor network:** 50 shielded temperature/humidity loggers stratified across housing type, elevation and coastal distance; 5 full WBGT stations; 24 months of continuous record with community host agreements.
- **Forecast/reanalysis:** ERA5-Land, ECMWF open forecast data; Project 3's AI-model output as an experimental forecast source.
- **Health signal (opportunistic, not load-bearing):** aggregated, anonymised syndromic indicators only if a Ministry of Health agreement is in place by month 6; the warning system does not depend on it — thresholds default to physiological standards (ISO 7243 WBGT bands) localised with sensor data.
- **Context layers:** WorldCover land cover, building footprints (Open Buildings), settlement typology mapping with community organisations.

## 4. Methodology

**WP1 — Measure (months 1–12).** Deploy the network before the first hot season; characterise intra-urban humid-heat variability, nighttime non-recovery (the key health driver), and indoor–outdoor offsets for the dominant housing types (sub-study with 10 indoor loggers).

**WP2 — Predict (months 8–20).** Quantile-map ERA5-Land to each sensor site; build a simple, transparent downscaling model (regression with land-cover and topographic predictors — deliberately not a black box, since the met agency must own it) to interpolate warnings to neighbourhood scale; verify 1–5-day forecast skill for threshold exceedance.

**WP3 — Set thresholds (months 12–20).** Localise WBGT action bands using measured acclimatisation context and, where the month-6 health-data gate passes, association with syndromic indicators. Define a three-tier alert (be-aware / take-action / emergency) with the City Council and Ministry of Health.

**WP4 — Pilot warning season (months 20–28).** Run one full hot season of live advisories through channels co-selected with communities (radio, mosque/church networks, market associations, SMS). Evaluate reach, comprehension and self-reported behaviour with before/after surveys in 4 wards (n≈400). Hand over protocols, hardware and code to the City Council and Met Agency.

## 5. Risks and decision gates

| Risk | Likelihood | Mitigation |
|---|---|---|
| Sensor loss/vandalism | Moderate | Community host stipends, 15% spare units budgeted, monthly checks |
| Health data agreement fails | Moderate–high | **Month-6 gate**: system defaults to physiological thresholds — health data enriches, never gates |
| Forecast skill insufficient at 5 days | Moderate | Warnings ship at whatever lead time verifies; even 24 h is transformative vs nothing |
| Behaviour-change evaluation confounded | Moderate | Modest claims; process evaluation design reviewed by public-health co-supervisor |

**Minimum viable thesis:** the measured humid-heat climatology of Freetown (first of its kind) plus the ERA5-Land correction framework — 2 papers.

## 6. Outcomes

- Peer-reviewed papers (2–3): intra-urban humid heat in a West African city; forecast-based warning verification; pilot-season evaluation.
- **Operational heat-health warning protocol** adopted by Freetown City Council, with the sensor network left running.
- Open sensor dataset (Zenodo) — the first dense humid-heat record for a West African city.
- Template heat-action plan transferable to other WASCAL-network cities.

## 7. What was cut, and why

Landsat LST time-series mapping (cloud-limited, not exposure-relevant), ECOSTRESS validation (unreliable), and hospital-data-dependent epidemiology as a core component (access risk). Each removal traces to a specific weakness identified in the prior review; the sensor network and health-sector partnership were the salvageable core.
