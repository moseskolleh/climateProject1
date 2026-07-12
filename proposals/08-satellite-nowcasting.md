# Project 8 — Six Hours Ahead: Satellite-Only Deep Learning Nowcasting for Radar-Sparse West Africa

**Extreme-rainfall nowcasting from geostationary satellites where the standard radar toolchain does not exist**

| | |
|---|---|
| **Status** | Extension track |
| **Duration** | 36 months |
| **Budget** | $95,000 (GPU cloud credits included) |
| **Study area** | West Africa; warning case studies for Freetown, Lagos and Accra |
| **Core methods** | Deep-learning video prediction on geostationary imagery, MCS tracking, threshold-based warning verification |
| **Primary partners** | National met services, EUMETSAT (data/training programmes), ACMAD; internal links to Projects 2 and 4 |

---

## 1. Why this project

The floods that kill people in West African cities develop in hours, not days: a mesoscale convective system (MCS) intensifies, stalls, and drops 100 mm before any daily forecast is relevant. The global nowcasting playbook — radar extrapolation, radar-trained deep learning — assumes a weather-radar network the region does not have and will not get soon. What the region *does* have is world-class geostationary coverage: Meteosat scans every 5–15 minutes, and the new MTG satellites add a lightning imager and sharper infrared channels. Deep-learning nowcasting driven purely by satellite observations is scientifically open (almost all published systems lean on radar) and is the only nowcasting path available to most of Africa. Whoever solves it well changes what a 2 a.m. warning looks like in Freetown.

## 2. Research questions

1. How predictable are West African MCS trajectories, intensification and dissipation at 0–6 hour leads from geostationary imagery (and lightning) alone?
2. Can deep-learning video-prediction models trained on the multi-decade Meteosat archive beat operational baselines (persistence, optical-flow extrapolation, NWCSAF products) for heavy-rain probability at warning-relevant thresholds?
3. What warning lead time and false-alarm rate does the end-to-end system achieve for real urban flood and landslide-trigger events — and does it arrive with latency small enough to matter?

## 3. Data

- **Predictors:** MSG SEVIRI infrared/water-vapour archive (15-min, 2004–present; 5-min rapid scan where available), MTG FCI imagery and Lightning Imager data as they accumulate.
- **Rainfall labels:** IMERG (30-min) as primary, blended with CHIRPS-compatible gauge correction; multi-product labels to avoid single-product artefacts.
- **MCS structure:** existing West African MCS tracking databases for training stratification and evaluation by storm type.
- **Case-study ground truth:** gauge and impact records for documented flood/landslide events (shared catalogues with Projects 2 and 5).

## 4. Methodology

**WP1 — Training corpus (months 1–10).** Build an ML-ready corpus of co-registered SEVIRI sequences and IMERG rainfall over West Africa (~20 wet seasons), stratified by MCS life stage; publish it — a reusable corpus is a contribution other groups will build on.

**WP2 — Models (months 8–22).** Train video-prediction architectures (ConvLSTM/transformer-based, probabilistic outputs) to predict exceedance probabilities (e.g., ≥20 mm/h, ≥50 mm/3 h) at 0–6 h leads. Baselines are non-negotiable: persistence, optical-flow extrapolation (pySTEPS), and NWCSAF rapid-development-thunderstorm products. **Decision gate (month 16):** GPU pilot costs reviewed; if training at full domain is unaffordable, reduce to a Guinean-coast subdomain — the impact case studies live there anyway.

**WP3 — Warning-relevant verification (months 18–30).** Verify not on mean scores but on the operating points warnings need: probability of detection vs false-alarm ratio at impact thresholds, by lead time and storm type; deep-dive hindcasts of documented disasters (including the 2017 Freetown storm). Latency audit of the full chain (satellite → product) against the 30–60 minute budget a useful urban warning allows.

**WP4 — Operational pathway (months 26–36).** Demonstration integration with one met service: real-time feed, simple alert console, forecaster evaluation over one wet season. Outputs feed Project 2's landslide-trigger thresholds and Project 4's convective-heat-break forecasts directly.

## 5. Risks and decision gates

| Risk | Likelihood | Mitigation |
|---|---|---|
| IMERG label noise limits learnable skill | Moderate | Multi-product labels; evaluation includes label-uncertainty analysis |
| GPU costs exceed budget | Moderate | Month-16 gate; subdomain fallback; efficient architectures before large ones |
| Beats baselines on average but not on extremes | Moderate | Loss functions and evaluation centred on exceedance thresholds from day one |
| Real-time latency too high in practice | Moderate | Latency audit is a WP3 deliverable, honest either way |

**Minimum viable thesis:** the open training corpus plus the model-vs-baselines study — 2 papers, no operational component required.

## 6. Outcomes

- Peer-reviewed papers (2–3): the corpus/benchmark; satellite-only nowcasting skill for MCSs; the warning-oriented case-study evaluation.
- **Open SEVIRI–IMERG nowcasting corpus and trained models.**
- Real-time demonstration console at one national met service.
- Trigger-layer input for the portfolio's landslide and heat warning systems.

## 7. Fit in the portfolio

Complements Project 3 (which evaluates day-to-week AI forecasts) at the hours timescale, sharing verification infrastructure and GPU tooling. Only take both projects on if two students are available — they are siblings, not one thesis.
