# Project 9 — Powering Through a Changing Climate: Inflow Risk for West Africa's Hydropower Backbone

**Non-stationary reservoir inflow and firm-energy analysis for the dams that anchor national grids**

| | |
|---|---|
| **Status** | Extension track |
| **Duration** | 36 months |
| **Budget** | $90,000 |
| **Study area** | Akosombo (Volta, Ghana), Kainji/Jebba (Niger, Nigeria), Bumbuna (Seli, Sierra Leone) |
| **Core methods** | Hydrological modelling, bias-corrected climate projections, reservoir operation simulation, storyline stress tests |
| **Primary partners** | Volta River Authority, West African Power Pool (WAPP), Volta and Niger Basin Authorities, EDSA/Seli Hydropower (Sierra Leone) |

---

## 1. Why this project

A handful of reservoirs carry West Africa's electricity systems: Akosombo alone has at times supplied most of Ghana's power, and its historic drawdowns (1983–84, 1998, 2006–07) triggered national load-shedding crises with measurable GDP losses. Yet the climate resilience of these assets is far less studied than their importance warrants — most operating rules descend from mid-20th-century hydrology, and the Sahel/Guinean rainfall record shows exactly the kind of multi-decadal swings that make short calibration periods dangerous. Energy ministries and the West African Power Pool are actively deciding how much new hydro, solar and interconnection to build; what they lack is a defensible picture of how firm hydropower energy changes under climate scenarios.

## 2. Research questions

1. How have inflows to the three reservoir systems varied over the instrumental record, and how much of that variability is multi-decadal (the Sahel drought signal) versus trend?
2. What do bias-corrected CMIP6/CORDEX projections imply for inflow distributions, drought-of-record risk, and firm-energy yield at each site through 2060?
3. How robust are current operating rules and planned expansions to plausible worst-case inflow storylines, and which portfolio decisions (operating-rule changes, solar hybridisation, interconnection) hedge that risk most cheaply?

## 3. Data

- **Hydrology:** GRDC discharge records, basin-authority gauge data, operator inflow/level series where MOUs permit; satellite altimetry lake levels (DAHITI/Hydroweb) as the independent fallback that de-risks operator access.
- **Climate forcing:** CHIRPS/ERA5 historical; CMIP6 and CORDEX-Africa projections bias-corrected with the portfolio's shared methods (Projects 1 and 3).
- **Infrastructure:** GRanD/GOODD dam databases, turbine and storage specifications from operator documentation, WAPP master-plan scenarios.

## 4. Methodology

**WP1 — Inflow reconstruction and variability (months 1–12).** Reconstruct and quality-control inflow series per basin; separate multi-decadal variability from trend (spectral and change-point analysis). This record honesty step matters: a model calibrated on 1990–2020 alone silently absorbs one phase of a multi-decadal cycle.

**WP2 — Hydrological projection (months 8–22).** Deliberately parsimonious conceptual models (GR4J/HBV class) per basin — chosen because their uncertainty is quantifiable, not because fancier is infeasible — calibrated with split-sample tests across wet and dry decades, then forced with the bias-corrected ensemble. Report inflow distributions with uncertainty decomposed into climate-model, bias-correction and hydrological-model shares.

**WP3 — Reservoir and firm-energy simulation (months 16–28).** Simulate operations under current rules for each inflow scenario: energy generated, spill, drawdown-crisis frequency, firm energy at standard reliability levels. Add **storyline stress tests** — a repeat of the 1983-class drought under 2050 demand, back-to-back failed wet seasons — because planners reason in storylines, not percentile fans.

**WP4 — Planning interface (months 24–36).** With WAPP and national utilities, translate results into the decisions on their table: operating-rule sensitivity, solar-hydro hybridisation value (reservoir as battery), interconnection hedging. Deliver a reproducible open toolkit so utilities can rerun the analysis as projections update.

## 5. Risks and decision gates

| Risk | Likelihood | Mitigation |
|---|---|---|
| Operator data access slow or partial | High | Altimetry + GRDC + GRanD sustain the full analysis at reduced precision; MOUs pursued from month 1 |
| Large projection spread for rainfall | High (expected) | Uncertainty decomposition + storyline framing keep results decision-usable regardless |
| Hydrological model structural error | Moderate | Two model structures per basin; discrepancy reported, not hidden |
| Three basins too many | Moderate | **Month-14 gate:** drop to two basins (keep Akosombo + Bumbuna for the big/small contrast) |

**Minimum viable thesis:** variability analysis plus projection and firm-energy results for two basins — 2 papers.

## 6. Outcomes

- Peer-reviewed papers (2–3): multi-decadal inflow variability and reconstruction; projected firm-energy risk; storyline stress-test methodology for African power planning.
- **Open reservoir-inflow risk toolkit** adopted by WAPP/utility planners.
- Site-specific briefings for three national utilities and two basin authorities.

## 7. Fit in the portfolio

Extends the portfolio into the energy sector using machinery it already owns — Project 1's non-stationary statistics and Project 3's bias-corrected forcing — and gives it a second slow-timescale planning project alongside compound flooding (Project 5).
