# Project 3 — Do AI Weather Models Work for West Africa?

**Evaluating and adapting machine-learning weather and downscaling models for the West African monsoon**

| | |
|---|---|
| **Status** | New — replaces the CMIP6 statistical-downscaling project |
| **Duration** | 36 months |
| **Budget** | $110,000 (GPU cloud credits instead of institutional HPC) |
| **Study area** | West African monsoon region (5°S–25°N, 25°W–15°E) |
| **Core methods** | AI weather models (GraphCast-class, AIFS, NeuralGCM), generative super-resolution/downscaling, rigorous regional benchmarking |
| **Primary partners** | ACMAD, WASCAL, ECMWF (data), national met services |

---

## 1. Why this project

Between 2023 and 2026, AI weather models went from research curiosities to operational systems: ECMWF runs AIFS operationally, and GraphCast-class models match or beat physics-based NWP on many global scores. But those scores are dominated by mid-latitude verification. The West African monsoon — driven by organised mesoscale convective systems (MCSs) that produce most of the region's rain and nearly all of its extremes — is precisely the regime where reanalysis training data is weakest and where smooth, blurry ML forecasts could fail dangerously while still scoring well globally.

Meanwhile the region's need for high-resolution rainfall information is acute, and the previous plan to meet it — classical statistical downscaling of a CMIP6 ensemble — required 48 months, $140k and guaranteed HPC access. Pretrained AI models invert that economics: **inference is cheap; the scientific work moves from computation to evaluation and adaptation.** Nobody has done that evaluation systematically for West Africa. This project does, and it is exactly the kind of contribution a well-resourced but not HPC-rich group can lead.

## 2. Research questions

1. How skilful are current AI weather models (AIFS, GraphCast-class, NeuralGCM) for West African monsoon precipitation — onset, MCS-driven extremes, dry spells — relative to ECMWF IFS and to what the region's forecasters currently receive?
2. Can generative ML downscaling (diffusion/GAN super-resolution, CorrDiff-style) produce physically credible ~4 km rainfall fields over West Africa from coarse model output, trained against satellite-era observations?
3. Does lightweight regional fine-tuning of a pretrained model improve monsoon skill without degrading global performance — and what does that cost in compute?

## 3. Data

- **AI model output:** WeatherBench 2 archives; operational AIFS/IFS forecasts (ECMWF open data); NeuralGCM runs.
- **Verification:** IMERG, CHIRPS, TAMSAT (three independent satellite products to avoid single-product circularity), national gauge networks via met-service agreements, MCS tracking datasets.
- **High-resolution reference:** CP4-Africa convection-permitting simulations (available archives) as a physical-realism benchmark for downscaled fields.

## 4. Methodology

**WP1 — Regional benchmark (months 1–12).** Build the first systematic West African verification suite for AI weather models: standard scores plus **monsoon-specific process diagnostics** — MCS frequency/intensity, diurnal cycle of convection, monsoon onset timing, dry-spell statistics, extreme-percentile behaviour. Verify against three independent observation products. Deliverable: an open, reusable benchmark ("WAM-Bench") others can run on any new model.

**WP2 — Generative downscaling (months 8–24).** Train a conditional diffusion model to map coarse (0.25°) fields to ~4 km rainfall, trained on IMERG with CP4-Africa realism checks (spatial spectra, storm-cell statistics, intensity distributions — not just pixel scores). **Decision gate (month 16):** if diffusion training is unstable on available GPUs, fall back to a deterministic U-Net + quantile-mapping hybrid, which is cheaper and still novel for the region.

**WP3 — Regional adaptation (months 18–32).** Parameter-efficient fine-tuning (LoRA-style adapters) of one pretrained model on regional reanalysis/observations. Success criterion is pre-registered: ≥10% improvement in monsoon precipitation scores with <2% global degradation. A negative result — fine-tuning doesn't help — is explicitly publishable and operationally important.

**WP4 — Forecaster co-evaluation (months 24–36).** Case-study evaluation of high-impact events (Freetown 2017 storm, recent urban floods) with ACMAD and national forecasters; subjective + objective assessment of whether AI guidance would have changed warnings issued.

## 5. Risks and decision gates

| Risk | Likelihood | Mitigation |
|---|---|---|
| GPU costs exceed budget | Moderate | Pilot in months 1–3 measures real costs; adapters not full retraining; fallback WP2 architecture |
| Gauge data access slow | High | Three satellite products carry verification alone; gauges upgrade, not gate, the analysis |
| Field moves fast, models superseded | Certain | The benchmark is the durable contribution — designed to evaluate any successor model |
| Downscaling looks good, verifies badly | Moderate | Process-based realism checks are first-class deliverables, not afterthoughts |

**Minimum viable thesis:** WAM-Bench benchmark paper plus one downscaling or fine-tuning study — 2 papers.

## 6. Outcomes

- Peer-reviewed papers (2–3): the West African AI-model benchmark; generative downscaling for the monsoon; fine-tuning study.
- **WAM-Bench:** open verification suite and leaderboard for AI models over West Africa.
- 4 km downscaled rainfall demonstration dataset (Zenodo).
- Training workshop for regional forecasters on using and *distrusting* AI guidance appropriately.

## 7. Why it replaced the old downscaling project

Same regional need (high-resolution rainfall), but: 36 vs 48 months, ~$110k vs $140k, no institutional-HPC gate, and a contribution at the field's live frontier rather than behind it. The stationarity-testing insight from the old project survives inside WP1's process diagnostics.
