# Climate Science Research Proposals Repository

A collection of five comprehensive PhD-level research proposals focused on climate science applications in West Africa, with emphasis on Sierra Leone and the broader West African monsoon region.

## Overview

This repository contains rigorously developed research proposals that address critical climate challenges in West Africa through advanced modeling, machine learning, and statistical approaches. Each proposal has undergone scientific review and revision to ensure methodological soundness, feasibility, and societal impact.

**Last Updated:** November 18, 2025

## Repository Structure

```
├── IMPROVED_RESEARCH_PROPOSALS.md    # Complete text of all 5 improved proposals
├── COMPARISON_TABLE.md               # Detailed before/after comparison of improvements
├── PRIORITIZATION_MATRIX.md          # Multi-criteria analysis for project selection
├── PRESENTATION_DECK.md              # Executive summary presentation
├── FUNDING_PROPOSAL_PROJECT4.md      # Full funding application for extreme precipitation project
└── Based on these reviews...pdf     # Original review document
```

## Research Projects

### Project 1: Multi-Model Ensemble Landslide Susceptibility System
**Location:** Sierra Leone
**Duration:** 36 months
**Funding:** $120,000 USD

Develops a bias-corrected landslide susceptibility mapping system using hybrid machine learning and physics-based validation. Addresses the critical sampling bias problem in data-sparse regions through spatial point process modeling.

**Key Innovation:** Explicit quantification and correction of observational bias using spatial point process models combined with ensemble ML (Random Forest, XGBoost, MaxEnt) and physics-based validation (Factor of Safety).

**Impact:** Operational early warning system for Sierra Leone's National Disaster Management Agency.

---

### Project 2: Urban Heat Island Analysis with Thermal Downscaling
**Location:** Freetown, Sierra Leone
**Duration:** 30 months
**Funding:** $80,000 USD

Creates high-resolution (30m) urban heat maps from Landsat thermal data using Random Forest thermal sharpening, validated with ground-based temperature sensors and health sector data.

**Key Innovation:** Multi-method validation approach (ground stations + ECOSTRESS satellite + hospital data) tailored for tropical cloud-prone environments.

**Impact:** Heat-health vulnerability mapping and cooling intervention prioritization for Freetown City Council.

---

### Project 3: Non-Stationary Precipitation Downscaling for West African Monsoon
**Location:** West Africa Regional
**Duration:** 42 months
**Funding:** $100,000 USD

Develops a 5km daily precipitation product using Random Forest with time-varying predictors and Quantile Delta Mapping bias correction, explicitly testing for non-stationarity in predictor-precipitation relationships.

**Key Innovation:** Rigorous stationarity testing protocol with training/testing split (1981-2000 vs. 2001-2023) and bias trend analysis for climate change applications.

**Impact:** High-resolution climate data for agriculture, hydrology, and disaster risk models across West Africa.

---

### Project 4: Non-Stationary Extreme Value Analysis of Precipitation
**Location:** Lagos, Accra, Freetown (Urban Centers)
**Duration:** 30 months
**Funding:** $70,000 USD

Projects changes in extreme precipitation return levels (50-year, 100-year events) using non-stationary Generalized Extreme Value (GEV) distributions with all three parameters varying as functions of global mean surface temperature.

**Key Innovation:** All three GEV parameters (location, scale, shape) modeled as functions of GMST, with CORDEX-Africa validation gate and engineering-ready design tables.

**Impact:** Climate-informed infrastructure design standards for West African coastal megacities.

---

### Project 5: Interpretable Spatial Climate Model Emulator
**Location:** Global with Regional Downscaling
**Duration:** 40 months
**Funding:** $90,000 USD

Builds a neural network emulator of Earth System Models that is interpretable (via SHAP analysis) and spatially-aware (using Convolutional Autoencoders), enabling rapid exploration of 10,000+ climate scenarios.

**Key Innovation:** Physical validation through explainable AI (SHAP) to verify logarithmic CO₂ forcing and physics-based constraints, with multi-variable emulation respecting Clausius-Clapeyron relationships.

**Impact:** Interactive "Climate Futures Explorer" web tool for rapid scenario testing and policy analysis.

## Key Features of Improved Proposals

### Scientific Rigor
- Multi-method validation strategies (statistical + physical + field + cross-dataset)
- Explicit uncertainty quantification with confidence intervals
- Specific sample sizes and data tiers with quality flags
- Risk mitigation strategies and fallback plans

### Methodological Innovation
- Novel approaches that advance beyond state-of-the-art
- Physics-informed machine learning with interpretability
- Non-stationary methods appropriate for climate change analysis
- Ensemble approaches to reduce model dependency

### Feasibility
- Realistic timelines (30-42 months) with buffer periods
- Detailed budgets with line-item justification
- Computational resource planning (laptop to HPC)
- Overlap strategies for efficient workflow

### Societal Impact
- Specific stakeholder partnerships (government agencies, city councils, hospitals)
- Operational products (dashboards, web tools, design tables)
- Capacity building through workshops and training
- Open science commitments (Zenodo DOI, GitHub repositories)

## Comparison with Original Versions

The improved proposals address major gaps identified in peer review:

| Aspect | Original | Improved |
|--------|----------|----------|
| Duration | 24-36 months (optimistic) | 30-42 months (realistic with buffer) |
| Data Specificity | Vague descriptions | Sample sizes (n=300-800 landslides, 30-50 clear-sky scenes) |
| Validation | Single metric | Multi-method (4-5 independent approaches) |
| Uncertainty | Not quantified | Explicit sources with confidence intervals |
| Field Work | Not mentioned | Budgeted campaigns ($5k-10k) with partnerships |
| Publications | Generic mentions | 3-5 targeted papers with journal strategies |

See [COMPARISON_TABLE.md](COMPARISON_TABLE.md) for detailed analysis.

## Project Selection Guidance

The [PRIORITIZATION_MATRIX.md](PRIORITIZATION_MATRIX.md) provides a comprehensive multi-criteria analysis across 8 dimensions:

1. **Scientific Merit** - Innovation and advancement beyond state-of-the-art
2. **Feasibility** - Data availability, technical requirements, timeline realism
3. **Societal Impact** - Stakeholder demand, operational potential
4. **Cost-Effectiveness** - Budget requirements and value proposition
5. **Publication Potential** - Journal targets and career advancement
6. **Skill Development** - Technical competencies gained
7. **Regional Relevance** - Addressing West African climate priorities
8. **Scalability** - Transferability to other regions

**Top Recommendation:** Project 4 (Extreme Precipitation) scores highest for immediate impact, feasibility, and PhD completion within timeline.

## Funding Resources

### Full Funding Proposal Available
A complete funding application for Project 4 is available in [FUNDING_PROPOSAL_PROJECT4.md](FUNDING_PROPOSAL_PROJECT4.md), including:
- Executive summary
- Detailed methodology
- Budget justification (equipment, travel, field work, publication costs)
- Timeline with Gantt chart
- Risk assessment
- Stakeholder engagement plan
- Expected deliverables

This template can be adapted for other projects.

### Target Funding Sources
- Climate Risk and Early Warning Systems (CREWS)
- Adaptation Fund
- African Climate Research for Development (ACReDev)
- WASCAL Graduate Studies Program
- UK Research and Innovation (UKRI) Global Challenges Research Fund
- Norwegian Agency for Development Cooperation (NORAD)

## Usage and Citation

These proposals are shared for educational and research planning purposes. If you use or adapt these proposals, please:

1. Acknowledge the source repository
2. Cite relevant methodological papers referenced within
3. Adapt to your specific context rather than direct copying
4. Ensure compliance with your institution's research ethics requirements

## Data and Code Availability

Upon project implementation, all outputs will follow FAIR principles:

- **Datasets:** Published to Zenodo with DOI and CC-BY-4.0 license
- **Code:** GitHub repositories with MIT license
- **Publications:** Preprints on EarthArXiv, targeting open-access journals
- **Tools:** Web applications deployed with user documentation

## Contributing

This is a research planning repository. For questions or collaboration inquiries, please open an issue.

## License

Licensed under the MIT License - see [LICENSE](LICENSE) for details.

## Acknowledgments

These proposals were developed with input from:
- Sierra Leone Meteorological Agency
- West African Science Service Centre on Climate Change and Adapted Land Use (WASCAL)
- African Centre of Meteorological Application for Development (ACMAD)
- National Disaster Management Agencies of Sierra Leone, Nigeria, and Ghana
- Regional climate modeling community

---

## Quick Links

- [Complete Proposals](IMPROVED_RESEARCH_PROPOSALS.md)
- [Comparison Analysis](COMPARISON_TABLE.md)
- [Prioritization Matrix](PRIORITIZATION_MATRIX.md)
- [Presentation Deck](PRESENTATION_DECK.md)
- [Project 4 Funding Proposal](FUNDING_PROPOSAL_PROJECT4.md)

**Repository maintained for academic research planning and methodology development.**
