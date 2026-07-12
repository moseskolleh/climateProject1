# Project 6 — When to Plant: Subseasonal Forecasts of Monsoon Onset and Dry Spells for West African Agriculture

**Turning open S2S forecast archives into calibrated planting-window advisories for smallholder farmers**

| | |
|---|---|
| **Status** | Extension track — recommended first addition |
| **Duration** | 36 months |
| **Budget** | $85,000 |
| **Study area** | West African monsoon region; advisory pilots in Senegal and Sierra Leone |
| **Core methods** | S2S reforecast skill assessment, ML post-processing/calibration, cost–loss forecast-value analysis, advisory co-design |
| **Primary partners** | AGRHYMET, ANACIM (Senegal), Sierra Leone Met Agency, national agricultural extension services |

---

## 1. Why this project

For a rain-fed smallholder, the costliest decisions of the year happen in two or three weeks: plant too early and a false monsoon onset kills the germinated seed; plant too late and the season is shortened. The information that could de-risk those decisions — subseasonal-to-seasonal (S2S) forecasts of monsoon onset timing and post-onset dry spells — sits in open archives (the WMO/ECMWF S2S and SubX databases, and now AI-model ensembles) largely unevaluated for this purpose. Seasonal outlooks (PRESAO/climate outlook forums) say whether the season will be wet; they cannot say *when to plant*. Nobody has systematically quantified, calibrated and valued S2S onset and dry-spell predictions for West African agriculture. This is the portfolio's agriculture gap, and it is the cheapest project relative to the number of people it touches.

## 2. Research questions

1. How much skill do current S2S systems (ECMWF, UKMO, NCEP reforecasts; AI-model ensembles) carry for local monsoon onset dates and post-onset dry spells (≥7 and ≥10 days), at which lead times, and how does that skill vary across agro-ecological zones?
2. Can ML post-processing of raw ensembles produce reliable, calibrated probabilities for the events farmers actually decide on ("onset within the next dekad", "a ≥7-day dry spell in the 3 weeks after planting")?
3. What is the economic value of these forecasts under realistic smallholder cost–loss structures — and does that value survive translation into advisories farmers receive, understand and act on?

## 3. Data

- **Forecasts:** S2S database reforecasts (ECMWF, UKMO, NCEP; ~20 years of hindcasts), SubX, and AI-model ensemble forecasts (AIFS ensemble) as an experimental comparison — connecting to Project 3's benchmark.
- **Verification:** CHIRPS and TAMSAT daily rainfall (two independent products), national gauge networks via met-service partners.
- **Onset definitions:** multiple agronomic definitions (e.g., cumulative-rainfall criteria with false-onset penalties) tested for sensitivity, chosen with agronomists rather than imposed.
- **Decision context:** farmer decision calendars, planting-cost and crop-loss parameters gathered through structured surveys run with extension services in Senegal and Sierra Leone (n≈300 across two zones).

## 4. Methodology

**WP1 — Skill assessment (months 1–12).** Verify onset-date and dry-spell predictions from the reforecast archives across the region: probabilistic scores (Brier, CRPSS, reliability) as a function of lead time, zone and onset definition. Deliverable: the first systematic S2S skill atlas for West African agronomic events — valuable even where the answer is "no skill beyond week 2", because it defines the honest usability boundary.

**WP2 — Calibration (months 8–20).** ML post-processing (gradient-boosted quantile regression and simple neural post-processing, benchmarked against standard NGR/ensemble-MOS) trained on reforecasts to correct model biases in onset timing and dry-spell frequency. Pre-registered success criterion: post-processed probabilities must beat climatology *and* raw ensembles on reliability and CRPSS at week-2+ leads.

**WP3 — Forecast value (months 14–26).** Extend the classic cost–loss framework with survey-derived parameters: replanting costs, seed prices, yield penalties for late planting. Compute value maps showing where and for whom the calibrated forecasts are worth acting on. This converts verification scores into the currency agricultural ministries understand.

**WP4 — Advisory pilot (months 22–34).** Co-design a dekadal planting-window bulletin with AGRHYMET/ANACIM formats and extension-service channels; run one full pilot season in two districts; evaluate comprehension and use with before/after farmer surveys. **The advisory rides existing channels — this project does not build a new dissemination system.**

## 5. Risks and decision gates

| Risk | Likelihood | Mitigation |
|---|---|---|
| Little S2S skill beyond week 2 | Moderate | The skill atlas + usability boundary is a publishable, policy-relevant result; value analysis then targets short-lead decisions |
| Onset-definition sensitivity dominates | Moderate | Multi-definition design from the start; agronomist-chosen primary definition |
| Survey logistics slip | Moderate | Surveys ride existing extension-service visits; two countries so one can carry the analysis |
| Pilot season is climatologically unusual | Possible | Evaluation focuses on process (reach, comprehension, trust), not single-season outcomes |

**Minimum viable thesis:** the S2S skill atlas (WP1) plus calibration study (WP2) — 2 papers, no field component required.

## 6. Outcomes

- Peer-reviewed papers (2–3): S2S skill atlas for agronomic events; ML calibration study; forecast-value/pilot evaluation.
- **Open calibrated-probability pipeline** runnable by AGRHYMET on each new forecast cycle.
- Survey-derived cost–loss parameter dataset for two countries (rare and reusable).
- Pilot-tested bulletin format for national met services.

## 7. Fit in the portfolio

Fills the portfolio's only major sectoral gap (agriculture). Reuses Project 3's verification infrastructure and AI-model interest at S2S lead times, and gives the portfolio a rural constituency to balance its urban focus.
