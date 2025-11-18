# IMPROVED RESEARCH PROPOSALS - CLIMATE SCIENCE PhD PROJECTS
## Comprehensive Revisions Based on Scientific Review
**Date:** November 18, 2025

---

# PROJECT 1 (IMPROVED)

## Title: A Multi-Model Ensemble Landslide Susceptibility System for Sierra Leone: Addressing Sampling Bias Through Hybrid Machine Learning and Physics-Based Validation

**Principal Investigator:** [Your Name]
**Duration:** 36 months (extended from 24 to accommodate field validation)
**Funding Required:** ~$120,000 USD

---

### 1. Introduction and Rationale

Landslides remain Sierra Leone's most lethal natural hazard, with the 2017 Regent disaster killing over 1,000 people. Developing a scientifically-robust nationwide Landslide Susceptibility Map (LSM) is critical for disaster risk reduction, urban planning, and early warning systems.

**The Core Challenge:** Creating valid LSMs in data-sparse regions faces a **sampling bias problem**: existing landslide inventories are inherently biased toward easily-observed events near roads and settlements, systematically missing remote occurrences. Machine learning models trained on biased inventories produce "observability maps" rather than true susceptibility maps.

**Our Solution:** This research will develop a **hybrid ensemble approach** that:
1. **Explicitly quantifies and corrects** for observational sampling bias using spatial point process modeling
2. **Integrates multiple ML models** (Random Forest, XGBoost, MaxEnt) to capture different aspects of landslide susceptibility
3. **Incorporates physics-based constraints** (infinite slope stability model) for validation
4. **Includes field validation** in collaboration with Sierra Leone's Meteorological Agency and university partners

---

### 2. Literature Review and Research Gaps

Machine learning LSMs (Random Forest, SVM, CNN) have become standard (Reichenbach et al., 2018; Merghadi et al., 2020). However, three critical gaps persist:

**Gap 1: Sampling Bias Rarely Addressed**
Most studies use random "pseudo-absence" points, which conflates "unobserved" with "stable." Recent work (Steger et al., 2021) advocates for case-control sampling designs, but implementation in tropical data-sparse regions remains limited.

**Gap 2: Single-Model Dependency**
Most LSM studies use a single ML algorithm, ignoring the fact that different models capture different failure mechanisms (e.g., RF captures threshold effects, MaxEnt captures environmental niches).

**Gap 3: Lack of Physical Validation**
Pure data-driven models may identify spurious correlations. Integration with simplified physics-based models (Factor of Safety) for validation is rarely performed.

**Gap 4: Static vs. Dynamic Confusion**
Studies often conflate "susceptibility" (intrinsic terrain properties) with "hazard" (including temporal triggers). The resolution mismatch between high-res terrain and coarse rainfall data is acknowledged but poorly addressed.

---

### 3. Research Questions and Objectives

**Primary Objective:**
To develop a bias-corrected, physically-validated, ensemble landslide susceptibility model for Sierra Leone at 30m resolution, and demonstrate its integration into a dynamic hazard forecasting framework.

**Research Questions:**

**RQ1:** Can spatial point process models (e.g., Log-Gaussian Cox Process) effectively quantify and correct for observational bias in Sierra Leone's landslide inventory?

**RQ2:** Does an ensemble of multiple ML algorithms (RF, XGBoost, MaxEnt) outperform single-model approaches in terms of AUC, precision-recall, and spatial transferability?

**RQ3:** To what extent do data-driven susceptibility predictions align with physics-based stability calculations (Factor of Safety) under known rainfall scenarios?

**RQ4:** What is the relative importance of static vs. dynamic predictors, and can a multi-scale modeling framework (30m static, 5km dynamic) provide skillful day-ahead landslide warnings?

---

### 4. Data and Methodology

#### A. Datasets

**Landslide Inventory (Enhanced Multi-Source):**
- **Literature & Reports:** Government archives, disaster databases (DesInventar, EM-DAT)
- **Remote Sensing:** Manual digitization from:
  - Google Earth historical imagery (2000-2024)
  - Sentinel-2 (10m, 2015-2024) - spectral change detection
  - Sentinel-1 SAR (coherence change for recent events)
  - PlanetScope (3m) - if accessible through education programs
- **Field Validation:** Targeted GPS surveys (see WP5)
- **Expected Size:** 300-800 landslide polygons (conservative target based on regional studies)

**Static Predictors (30m):**
- **DEM:** ALOS PALSAR (30m) - validated against SRTM
  - Derived: Slope, aspect, curvature (plan/profile), Topographic Wetness Index (TWI), Stream Power Index (SPI)
- **Geology:** Digitized from 1:250,000 geological maps + global datasets (GLiM)
- **LULC:** Sentinel-2 classification (Random Forest): Forest, Agriculture, Urban, Bare/Rock, Water
- **Infrastructure:** OSM roads, rivers (buffered distance features)
- **Soil:** ISRIC SoilGrids (organic content, texture)

**Dynamic Predictors (5km):**
- **CHIRPS:** 3-day, 7-day, 15-day antecedent rainfall
- **IMERG** (if available): Higher resolution precipitation

**Observability Proxy Variables:**
- Distance to roads (primary bias source)
- Population density (WorldPop, 100m)
- Forest cover (visibility constraint)

#### B. Methodology (Work Packages)

**WP1: Enhanced Landslide Inventory Development (Months 1-12)**

*Addressing Data Quality Weakness:*

1. **Multi-source compilation:** Integrate historical records, systematic satellite analysis, and citizen science reports
2. **Quality tiers:** Classify events by confidence level:
   - Tier 1: Field-verified or high-resolution imagery confirmed
   - Tier 2: Satellite-detected with clear morphological signature
   - Tier 3: Reported but unconfirmed
3. **Temporal attribution:** Record or estimate date/month for dynamic modeling
4. **Spatial accuracy:** Distinguish initiation zones from deposit areas

*Deliverable:* Georeferenced database with quality metadata (n ≈ 300-800)

---

**WP2: Sampling Bias Quantification (Months 10-18)**

*Addressing the Core Methodological Innovation:*

This is the PhD's novel contribution. Instead of ad-hoc pseudo-absence selection:

1. **Fit a Spatial Point Process Model:**
   - Model landslide occurrence intensity λ(s) as:
     ```
     λ(s) = ρ(s) × θ(s)
     ```
     Where:
     - ρ(s) = "true" susceptibility (what we want)
     - θ(s) = observability (bias we need to model)

2. **Observability Model:**
   - Fit θ(s) using proxies: distance to roads, population density, forest cover
   - Use reported vs. expected density ratios in grid cells

3. **Generate Bias-Corrected Pseudo-Absences:**
   - Sample "absence" points with probability inversely weighted by θ(s)
   - This ensures background sample represents the full environmental gradient, not just accessible areas

4. **Validation:**
   - Compare environmental distributions of P-points vs. bias-corrected A-points vs. simple random A-points
   - Hypothesis: Bias-corrected method reduces environmental separation

*Deliverable:* Observability surface map, bias-corrected absence dataset

---

**WP3: Multi-Model Ensemble Development (Months 16-24)**

*Addressing Single-Model Limitation:*

Train **three complementary algorithms:**

1. **Random Forest (RF):**
   - Strength: Handles non-linearity, variable interactions, robust to outliers
   - Implementation: sklearn RandomForestClassifier, 500 trees, tuned via GridSearchCV

2. **XGBoost (Gradient Boosting):**
   - Strength: Often superior performance, handles imbalance via scale_pos_weight
   - Implementation: xgboost.XGBClassifier, early stopping on validation set

3. **MaxEnt (Maximum Entropy):**
   - Strength: Designed for presence-background data, provides environmental niche interpretation
   - Implementation: maxentpy or Java MaxEnt

**Training Strategy:**
- **Input:** All static predictors + observability as covariate (to control residual bias)
- **Cross-validation:** Spatial k-fold (5 folds, spatially stratified to avoid autocorrelation)
- **Class imbalance:** Use weighted loss, SMOTE oversampling (test sensitivity)

**Ensemble Construction:**
- Simple average of predicted probabilities
- Weighted average (weights from CV performance)
- Stacked generalization (meta-learner)

**Evaluation Metrics:**
- AUC-ROC (threshold-independent)
- **Precision-Recall AUC** (better for imbalanced data)
- Brier Score (calibration)
- **Spatial transferability:** Train on 70% of country, test on held-out 30%

*Deliverable:* Three individual susceptibility maps + ensemble map

---

**WP4: Physics-Based Validation (Months 22-28)**

*Addressing Physical Plausibility:*

**Infinite Slope Stability Model:**

Calculate Factor of Safety (FS) for shallow landslides:

```
FS = [c' + (γ_soil × z × cos²β)(1 - m × γ_w/γ_soil) × tanφ'] / (γ_soil × z × sinβ × cosβ)
```

Where:
- c' = cohesion, φ' = friction angle (from soil data + literature)
- β = slope angle
- z = soil depth (estimated from TWI)
- m = relative soil saturation (from rainfall input)

**Validation Approach:**
1. Calculate FS for n=100 random points in each susceptibility class (Very Low to Very High)
2. **Hypothesis:** ML-predicted high susceptibility zones should show lower FS (closer to 1.0) under saturated conditions
3. **Correlation analysis:** Spearman correlation between ML probability and (1/FS)

**Purpose:** Not to replace ML model, but to validate that high-susceptibility predictions align with physical instability under plausible scenarios.

*Deliverable:* FS map, validation report

---

**WP5: Field Validation Campaign (Months 24-30)**

*Critical Addition for PhD Rigor:*

**Objectives:**
1. Ground-truth 30-50 ML-predicted high-susceptibility sites
2. Validate recent landslides from inventory
3. Collect soil samples (if possible) for stability parameters

**Approach:**
- **Stratified sampling:** Sites across susceptibility classes and accessibility levels
- **Local collaboration:** Partner with Njala University/University of Sierra Leone students
- **Data collection:** GPS points, photos, slope measurements (clinometer), land cover notes

**Metric:**
- Proportion of "high susceptibility" field sites showing evidence of instability (scarps, tension cracks, past failures)

*Deliverable:* Field validation report, updated inventory

---

**WP6: Dynamic Hazard Integration (Months 28-36)**

*Operationalization:*

The ensemble model (from WP3) provides **static susceptibility**. For **dynamic hazard:**

**Framework:**
```
Hazard(x,t) = Susceptibility(x) × Trigger_Probability(t)
```

**Implementation:**
1. Susceptibility(x): Ensemble ML probability (static)
2. Trigger_Probability(t): Derived from rainfall thresholds
   - Use historical landslide dates + CHIRPS rainfall
   - Fit empirical rainfall intensity-duration (ID) thresholds per susceptibility zone
   - For day t, if forecasted rainfall exceeds threshold → elevated hazard

**Deliverable:**
- Trained model (.pkl files)
- Python API that accepts daily rainfall forecast → outputs 30m hazard map
- Demonstration dashboard (Streamlit/Dash)
- User manual for National Disaster Management Agency

---

### 5. Expected Outcomes and Innovation

**Deliverables:**
1. **First nationwide, bias-corrected LSM for Sierra Leone** (30m resolution)
2. **Open-source ensemble modeling framework** (GitHub repository)
3. **Validated rainfall-triggered landslide thresholds** for forecasting
4. **3-5 peer-reviewed publications:**
   - Paper 1: Spatial point process bias correction method
   - Paper 2: Ensemble LSM for Sierra Leone
   - Paper 3: Physics-ML integration for validation
   - Paper 4: Operational early warning system design

**Scientific Contributions:**
- Novel **spatial point process approach** to sampling bias - transferable globally
- Demonstrates **ensemble modeling** superiority in data-sparse contexts
- **Physics-based validation** framework for ML geohazard models

**Societal Impact:**
- Operational tool for National Disaster Management Agency
- Informs land-use planning in high-risk areas (Freetown hillsides)
- Foundation for community-level early warnings

---

### 6. Feasibility and Resources

**Data:** Freely available (ALOS, Sentinel, CHIRPS)
**Software:** Open-source (Python, R, QGIS)
**Computational:** Standard laptop + cloud resources (Google Earth Engine)
**Field Work:** $10,000 (transportation, local assistants, equipment)
**Training:** Advanced ML, spatial statistics, GIS
**Collaboration:** Established contacts with Njala University, Sierra Leone Met Agency

---

### 7. Timeline Summary

| Phase | Months | Activities |
|-------|--------|------------|
| Data Collection | 1-12 | Inventory compilation, remote sensing analysis |
| Bias Analysis | 10-18 | Spatial point process modeling |
| Model Development | 16-24 | Train RF, XGBoost, MaxEnt, ensemble |
| Validation | 22-30 | Physics-based + field campaign |
| Operationalization | 28-36 | Dynamic system, dashboard, documentation |
| Writing | 24-36 | Continuous publication efforts |

---

### 8. Limitations and Future Work

**Limitations:**
- Model quality ultimately constrained by inventory completeness (mitigated through multi-source + field validation)
- Rainfall resolution mismatch (5km) introduces uncertainty (acknowledged, uncertainty quantification in future work)
- Climate non-stationarity: Assumes historical slope-rainfall relationships hold (standard limitation)

**Future Extensions:**
- Deep learning with CNN for automated landslide detection from satellite imagery
- Integration with hydrological models for soil moisture estimation
- Climate change scenarios using downscaled projections

---

### 9. References (Updated)

- Merghadi et al. (2020). Machine learning methods for landslide susceptibility studies: A comparative overview. *Earth-Science Reviews*, 207, 103225.
- Reichenbach et al. (2018). A review of statistically-based landslide susceptibility models. *Earth-Science Reviews*, 180, 60-91.
- Steger et al. (2021). The influence of systematically incomplete shallow landslide inventories on statistical susceptibility models. *Geomorphology*, 371, 107803.

---

---

# PROJECT 2 (IMPROVED)

## Title: High-Resolution Urban Thermal Dynamics in Freetown: A Validated Thermal Downscaling Approach with Health-Sector Application

**Principal Investigator:** [Your Name]
**Duration:** 30 months
**Funding Required:** ~$80,000 USD

---

### 1. Introduction and Rationale

Freetown, Sierra Leone's capital (pop. ~1.2M), is experiencing rapid, unplanned urban expansion on steep hillsides, replacing vegetation with impervious surfaces. This land transformation drives the Urban Heat Island (UHI) effect, which exacerbates heat stress—a critical but underappreciated public health threat in West Africa's humid tropical climate.

**The Data Barrier:** Quantifying Freetown's thermal dynamics requires both high spatial resolution (to see neighborhood differences) and high temporal frequency (to capture seasonal and daily variation). However:
- **Landsat:** 30m resolution, but 16-day revisit + cloud cover = <10 usable images/year
- **MODIS:** Daily, but 1km resolution = cannot differentiate intra-city patterns

**Our Solution:** This research will develop and rigorously validate a **thermal downscaling (sharpening) model** using machine learning to fuse MODIS and Landsat, creating a **synthetic 30m daily Land Surface Temperature (LST) dataset** for Freetown (2013-2024, Landsat-8 era). We will then:
1. Quantify the Surface Urban Heat Island Intensity (SUHI) with a reproducible metric
2. Link SUHI evolution to 10+ years of land-use change
3. **NEW:** Partner with Connaught Hospital to explore thermal stress-health linkages

---

### 2. Literature Review and Research Gaps

**Thermal Sharpening State-of-the-Art:**
Methods include TsHARP (disaggregation based on NDVI-LST relationship), AT-PRMT (adaptive threshold), and increasingly, **machine learning approaches** (Hassan et al., 2021) using Random Forest or deep learning to learn complex multi-variable relationships.

**Research Gaps:**

**Gap 1: Validation of Synthetic LST**
Most thermal sharpening studies validate by:
- Comparing synthetic LST to actual Landsat LST on a few test dates (circular - uses same data source)
- Few studies validate against in-situ temperature stations
- **Our contribution:** Multi-method validation including ground stations

**Gap 2: Cloud Contamination Handling**
Even MODIS has cloud issues in tropical regions. Studies often don't address:
- What happens on fully cloudy days?
- How to gap-fill?
- **Our approach:** Explicit cloud masking + temporal interpolation with uncertainty flagging

**Gap 3: UHI Metrics for Cities Without "Rural" Areas**
Freetown is surrounded by ocean, forested hills, and peri-urban settlements - no clear "rural" reference. The "urban minus rural" UHI metric is therefore problematic.
- **Our contribution:** SUHI as intra-city contrast (urban vs. vegetated pixels within boundary)

**Gap 4: Health Linkage Missing**
Numerous UHI studies produce maps but few connect to health outcomes in African cities.
- **Our contribution:** Collaborate with local hospital for exploratory heat-health analysis

---

### 3. Research Questions and Objectives

**Primary Objective:**
To create a validated, high-resolution (30m) daily LST time series for Freetown (2013-2024) and use it to quantify the evolution of Surface Urban Heat Intensity in relation to land-use change and explore associations with heat-related health outcomes.

**Research Questions:**

**RQ1:** Can a Random Forest model trained on clear-sky days accurately downscale MODIS 1km LST to 30m using Landsat-derived predictors (NDVI, NDBI, albedo), and how does its accuracy compare to traditional TsHARP?

**RQ2:** How well does synthetic LST validate against: (a) held-out Landsat LST scenes, (b) ground-based temperature measurements, and (c) thermal patterns observed in very-high-resolution imagery (e.g., ECOSTRESS)?

**RQ3:** What is the magnitude and spatio-temporal variability of Freetown's SUHI (defined as LST_urban - LST_vegetation), and how has it evolved from 2013-2024?

**RQ4:** What is the quantitative thermal impact (ΔLST) of land-cover transitions, specifically vegetation-to-urban conversion, and does this vary by topographic position (lowland vs. hillside)?

**RQ5 (NEW):** Is there an association between elevated LST in residential neighborhoods and heat-related hospital admissions (exploratory analysis)?

---

### 4. Data and Methodology

#### A. Datasets

**Satellite Data:**
- **MODIS:** MOD11A1 & MYD11A1 (Terra & Aqua, 1km, daily LST), 2013-2024
- **Landsat 8/9:** Collection 2 Level-2, 30m thermal bands (resampled from 100m), 2013-2024
  - Surface Reflectance (for NDVI, NDBI, albedo)
  - Estimated: 30-50 clear-sky scenes over Freetown per year = ~400 training days
- **Sentinel-2:** 10m surface reflectance (2016-2024) for recent high-res LULC

**Ancillary:**
- **DEM:** SRTM 30m (elevation, slope)
- **Administrative boundaries:** Freetown city limits, ward boundaries
- **Ground Observations (NEW):**
  - Freetown Lungi Airport meteorological station (daily max/min temperature)
  - Deploy 10 low-cost temperature loggers in diverse neighborhoods (if budget allows)

**Health Data (NEW - Requires Ethical Approval):**
- Aggregate monthly counts of heat-related admissions (Connaught Hospital)
- Diagnoses: heat exhaustion, dehydration, cardiovascular events during hot periods
- **Privacy:** Aggregate, no individual patient data

**ECOSTRESS (Validation Enhancement):**
- 70m thermal imagery from ISS (irregular but very high quality when available)

---

#### B. Methodology (Work Packages)

**WP1: LULC Time-Series Classification (Months 1-6)**

*Enhanced with Accuracy Assessment:*

1. Create annual cloud-free composites (2013-2024) using Google Earth Engine
2. Collect training data (n=500 points per class) via visual interpretation + field knowledge:
   - Classes: Dense Urban, Sparse Urban, Vegetation (dense/sparse), Water, Bare/Rock
3. Train Random Forest classifier (ntree=500)
4. **Validation:** 30% holdout, report Overall Accuracy, Kappa, per-class F1-scores
5. Target: Overall Accuracy >85%
6. Generate annual 30m LULC maps

*Deliverable:* 12 validated LULC maps (2013-2024)

---

**WP2: Thermal Downscaling Model Development (Months 6-18)**

*The Core Innovation with Enhanced Validation:*

**Phase 2a: Training Dataset Construction (Months 6-10)**

1. **Identify clear-sky days:** Where both Landsat and MODIS LST are cloud-free over Freetown
   - Cloud masking: Landsat QA band + MODIS QC flags
   - Expected: ~300-400 days

2. **For each clear day, extract at 30m pixels:**
   - **Target (y):** Landsat LST (resampled to 30m from 100m native thermal)
   - **Predictors (X):**
     - MODIS LST (resampled from 1km to 30m - constant within each 1km cell)
     - Landsat NDVI (30m)
     - Landsat NDBI (Normalized Difference Built-up Index)
     - Landsat Albedo (broadband, calculated from reflectance)
     - LULC class (categorical)
     - Elevation, Slope (30m DEM)
     - Julian day, Time of day (MODIS acquisition time)

3. **Spatial sampling:** Random sample 10,000 pixels per scene to avoid class imbalance (oversample vegetated areas)

**Phase 2b: Model Training and Comparison (Months 10-14)**

Train **two models:**

1. **TsHARP (Baseline):** Traditional method using NDVI-LST regression
   ```
   LST_30m = LST_1km + b × (NDVI_30m - NDVI_1km)
   ```

2. **Random Forest Downscaling (Proposed):**
   - sklearn RandomForestRegressor
   - Hyperparameter tuning: n_estimators, max_depth, min_samples_split
   - 5-fold cross-validation (spatial blocks to avoid autocorrelation)

**Validation:**
- **Metric 1:** RMSE, MAE, R² on held-out Landsat scenes (30% of days)
- **Metric 2 (NEW - Critical):** Validate against ground stations
  - Compare pixel LST to Tair (LST typically 5-10°C higher, but should correlate)
- **Metric 3 (NEW):** If ECOSTRESS scenes available, compare spatial patterns
- **Metric 4:** Visual inspection of thermal gradients (does urban core appear warmer?)

**Hypothesis:** RF will outperform TsHARP (RMSE reduction >1.5°C) due to non-linear multi-variable learning.

*Deliverable:* Trained RF model + validation report (target RMSE < 2.5°C)

---

**Phase 2c: Synthetic LST Generation (Months 15-18)**

1. **For every day (2013-2024):**
   - Input: Daily MODIS LST + static/annual predictors
   - Output: Predicted 30m LST

2. **Cloud Handling:**
   - If MODIS is cloudy → no prediction (mark as NA)
   - If MODIS clear but model uncertainty high (based on RF variance) → flag as low-confidence
   - **Gap-filling:** Use 3-day moving average for isolated NAs (with uncertainty propagation)

3. **Output:** ~4,000 daily 30m LST maps for Freetown (cloud days excluded)

4. **Uncertainty Quantification:**
   - RF provides prediction variance (from tree ensemble spread)
   - Propagate to all outputs
   - Report mean ± SD for all SUHI calculations

*Deliverable:* LST data cube, uncertainty layers

---

**WP3: SUHI Quantification and Temporal Analysis (Months 18-24)**

*Refined Metric:*

**SUHI Calculation:**
```
SUHI(t) = median(LST_DenseUrban,t) - median(LST_Vegetation,t)
```
- Use median (robust to outliers)
- Within Freetown city boundary only
- Calculate for daytime (10-14:00 local) LST

**Temporal Analysis:**
1. **Daily SUHI time series** (2013-2024)
2. **Seasonal patterns:** Dry season (Nov-Apr) vs. Wet season (May-Oct)
3. **Trend analysis:** Mann-Kendall test for monotonic trend
4. **Spatial SUHI mapping:** Which neighborhoods experience highest intensity?

**LULC-SUHI Co-evolution (RQ3):**
- Plot: % Urban Area vs. Mean Annual SUHI (2013-2024)
- Hypothesis: Positive correlation (r > 0.7)

*Deliverable:* SUHI time series, trend analysis, visualizations

---

**WP4: Land-Cover Transition Impact Analysis (Months 22-26)**

*Change Detection:*

1. **Identify transition pixels:** 2013 = Vegetation, 2024 = Dense Urban
2. **Extract ΔLST:**
   ```
   ΔLST = LST_2024 - LST_2013 (same season, e.g., dry season median)
   ```
3. **Compare to "stable" pixels** (vegetation in both years) as control
4. **Stratify by topography:**
   - Lowland (<50m elevation)
   - Hillside (50-200m)
   - Upland (>200m)
   - Hypothesis: Hillside urbanization has greater ΔLST due to slope exposure

**Quantitative Result:**
"Conversion of 1 hectare from forest to dense urban increases dry-season LST by X.X ± Y.Y °C"

*Deliverable:* Change map, statistical report

---

**WP5: Health Linkage Exploratory Analysis (Months 24-30) [NEW]**

*Addressing Application Gap:*

**Objective:** Explore potential associations between thermal stress and health outcomes (not causal inference, but hypothesis-generating).

**Approach:**

1. **Aggregate LST by Ward:** Calculate monthly mean daytime LST for each Freetown administrative ward

2. **Heat Metrics:**
   - Mean LST
   - Number of "extreme heat days" (LST > 90th percentile)
   - Cumulative heat exposure

3. **Health Data:** Monthly heat-related hospital admissions (if accessible)

4. **Analysis:**
   - Time-series cross-correlation: Is there a lag between heat exposure and admissions?
   - Generalized Additive Model (GAM): Admissions ~ s(LST) + Month + Trend
   - Spatial analysis: Do high-LST wards have higher admission rates?

**Limitations (clearly stated):**
- Ecological fallacy (aggregate data)
- No individual-level exposure
- Cannot establish causation
- Hospital data may be incomplete
- Need to control for confounders (air quality, socioeconomics - likely unavailable)

**Purpose:** Demonstrate policy-relevance, inform future cohort studies

*Deliverable:* Exploratory report, recommendations for future epidemiological research

---

### 5. Expected Outcomes and Innovation

**Deliverables:**
1. **First validated 30m daily LST dataset for a West African city**
2. **Open-source thermal downscaling code** (Python/GEE GitHub repository)
3. **10-year SUHI trend analysis** for Freetown
4. **Heat-health exploratory study** - first for Sierra Leone
5. **Publications:**
   - Paper 1: Thermal downscaling methodology and validation
   - Paper 2: Urban heat island evolution and land-use linkages
   - Paper 3: Exploratory heat-health analysis (co-authored with public health researchers)

**Scientific Contributions:**
- **Methodological:** Multi-method validation framework for synthetic thermal products in tropics
- **Regional:** First rigorous UHI study for Freetown
- **Applied:** Demonstrates health-sector relevance

**Societal Impact:**
- Inform Freetown City Council's urban greening strategies
- Identify heat-vulnerable neighborhoods for targeted interventions (cool shelters, tree planting)
- Evidence base for climate adaptation planning

---

### 6. Feasibility Assessment

**Data Availability:** HIGH - All satellite data free and accessible
**Technical Complexity:** MEDIUM - Requires GIS, ML, statistical modeling skills
**Computational Needs:** Moderate - GEE for pre-processing, local Python for modeling
**Health Collaboration:** Requires ethical approval + hospital partnership (6-month lead time)
**Validation Ground Sensors:** Budget $5,000 for 10 HOBO temperature loggers + deployment

**Risk:** If ground station data unavailable, rely on airport station + ECOSTRESS cross-validation

---

### 7. Timeline Summary

| Phase | Months | Key Activities |
|-------|--------|----------------|
| LULC Classification | 1-6 | Annual maps, validation |
| Model Training | 6-14 | RF training, validation |
| LST Generation | 15-18 | Apply model to all days |
| SUHI Analysis | 18-24 | Temporal and spatial patterns |
| Change Detection | 22-26 | LULC transition impacts |
| Health Analysis | 24-30 | Collaboration, exploratory stats |
| Publication | 20-30 | Manuscript preparation |

---

### 8. Limitations

- **LST ≠ Air Temperature:** LST is surface property; human heat stress relates to air temp + humidity (future work: integrate with air temp models)
- **Cloud Gaps:** Some days will remain missing (unavoidable in tropics)
- **Landsat Thermal Resolution:** Native 100m resampled to 30m introduces smoothing
- **Health Data Constraints:** Aggregate, hospital-only (misses community-level heat illness)

---

### 9. References (Updated)

- Hassan et al. (2021). A robust downscaling approach for high-resolution LST using Random Forest. *Remote Sensing of Environment*, 258, 112364.
- Stewart & Oke (2012). Local Climate Zones for urban temperature studies. *BAMS*, 93(12), 1879-1900.

---

---

# PROJECT 3 (IMPROVED)

## Title: Non-Stationary Statistical Downscaling of CMIP6 Precipitation for West Africa: A Rigorous Bias-Correction and Ensemble Framework

**Principal Investigator:** [Your Name]
**Duration:** 42 months (extended to allow for rigorous validation)
**Funding Required:** ~$100,000 USD (including computational resources)

---

### 1. Introduction and Rationale

West Africa's ~400 million people depend on rainfed agriculture sustained by the West African Monsoon (WAM). Understanding how climate change will alter WAM precipitation patterns is essential for food security, water resource management, and disaster preparedness.

Global Climate Models (CMIP6) provide long-term projections, but their coarse resolution (100-200km) cannot inform regional impact assessments, which require 5-10km data to resolve mesoscale convective systems, topographic effects, and catchment-scale hydrology.

**Statistical Downscaling (SD)** bridges this gap by learning relationships between large-scale atmospheric patterns and local rainfall. However, AI-based SD faces two fundamental challenges:

1. **Stationarity Assumption:** Most models assume the statistical relationships learned from historical data (1980-2010) remain valid in a warmer future (2050-2100). This is questionable given WAM's non-linear dynamics and regime shifts.

2. **Bias Problem:** Raw CMIP6 outputs are systematically biased relative to observations. Feeding biased predictors into a trained model produces invalid results.

**This Research:** We develop a **non-stationary, bias-corrected** Random Forest downscaling framework that:
- **Tests** the stationarity assumption rigorously before application
- **Accounts for** evolving climate-rainfall relationships using time-varying covariates
- **Applies** state-of-the-art bias correction (Quantile Delta Mapping) to CMIP6 predictors
- **Validates** against independent metrics including extreme event statistics

---

### 2. Literature Review and Research Gaps

**Statistical Downscaling Evolution:**
Traditional SD used linear regression (Wilby et al., 1998). Modern approaches employ machine learning (RF, ANNs, CNNs) due to superior performance on non-linear relationships (Gutiérrez et al., 2019; Baño-Medina et al., 2020).

**Gap 1: Stationarity Rarely Tested**
Most studies *assume* stationarity without validation. Temporal split-sample tests (train on early period, validate on late period) are rare. For the WAM, which exhibits multi-decadal variability (AMO, Sahel drought/recovery), this assumption is particularly risky.

**Gap 2: Bias Correction Methods Inconsistent**
Studies apply bias correction in different ways:
- Some bias-correct GCM outputs *after* downscaling (wrong - preserves biased relationships)
- Some use simple linear scaling (inadequate for precipitation distributions)
- Best practice: **Quantile Delta Mapping (QDM)** before downscaling, preserving change signal

**Gap 3: Limited Validation for West Africa**
Existing SD datasets for West Africa (e.g., CORDEX statistical products) have limited documentation of methodology and validation. High-quality, open-source, satellite-trained products are lacking.

**Gap 4: Extremes Often Ignored**
Models optimized for mean rainfall may fail for extremes (important for floods/droughts). Validation should include extremes explicitly.

---

### 3. Research Questions and Objectives

**Primary Objective:**
To develop, validate, and apply a non-stationary, bias-corrected Random Forest statistical downscaling model for daily precipitation over West Africa (5km resolution), producing an ensemble of future projections (2015-2100) suitable for impact modeling.

**Research Questions:**

**RQ1 (Stationarity Test):** Are the statistical relationships between large-scale atmospheric predictors (ERA5) and fine-scale precipitation (CHIRPS) stable over the 1981-2023 period, or do they exhibit systematic temporal drift?

**RQ2 (Non-Stationary Modeling):** If non-stationarity is detected, can a model augmented with a climate state covariate (global or regional temperature trend) outperform a stationary model in out-of-sample validation?

**RQ3 (Bias Correction):** How sensitive are downscaled projections to the bias-correction method applied to CMIP6 predictors (no correction vs. linear scaling vs. QDM)?

**RQ4 (Future Projections):** How do high-resolution (5km) downscaled precipitation projections for West Africa (2050-2100, SSP2-4.5 and SSP5-8.5) compare to raw CMIP6 in terms of:
- Seasonal rainfall totals
- Monsoon onset/cessation dates
- Extreme daily rainfall frequency (>50mm/day, >100mm/day)

**RQ5 (Spatial Validation - NEW):** Does the downscaling model skillfully reproduce observed spatial gradients (coast-to-Sahel, orographic enhancement)?

---

### 4. Data and Methodology

#### A. Datasets

**Observational "Truth" (Target Variable):**
- **CHIRPS v2.0:** 0.05° (~5km) daily precipitation, 1981-2023
  - Quality: Blend of satellite + sparse gauges, best available for region
  - Limitation: Uncertainty increases in data-sparse areas (acknowledged)

**Training Predictors (Historical Period):**
- **ERA5 Reanalysis:** 0.25° (~25km), 1981-2023, daily
  - Variables:
    - 850 hPa specific humidity (q850)
    - 850 hPa zonal/meridional wind (u850, v850)
    - 700 hPa vertical velocity (ω700) - proxy for uplift
    - 500 hPa geopotential height (z500) - atmospheric circulation
    - Mean Sea Level Pressure (MSLP)
    - Total column water vapor (TCWV)
    - 2m temperature (T2m) - for non-stationary covariate

**Future Predictors (Projection Period):**
- **CMIP6 Models:** Daily output, 1981-2100, SSP2-4.5, SSP3-7.0, SSP5-8.5
  - Priority models (based on West Africa evaluation literature):
    - CNRM-CM6-1, EC-Earth3, MPI-ESM1-2-HR, UKESM1, GFDL-ESM4, ACCESS-ESM1-5, MIROC6, CESM2, CanESM5, IPSL-CM6A
  - Target: 8-10 models with complete variable availability
  - Variables: Same as ERA5 (q850, u850, v850, ω700, z500, MSLP, TCWV, T2m)

**Domain:** 5°W to 15°E, 4°N to 20°N (captures Guinea Coast to Sahel)

---

#### B. Methodology (Work Packages)

**WP1: The Stationarity Test (Months 1-9)**

*Critical Methodological Gate:*

**Rationale:** Before developing a stationary model, we must test whether it's appropriate.

**Design:**

1. **Split ERA5-CHIRPS data:**
   - Training ("cool"): 1981-2000 (20 years)
   - Validation ("warm"): 2001-2023 (23 years)

2. **Train a Stationary Random Forest:**
   - Target: CHIRPS daily rainfall (mm/day) at each 5km grid cell
   - Predictors: ERA5 atmospheric variables (spatially aggregated in window around target pixel)
   - Separate model for each season (DJF, MAM, JJA, SON) to account for monsoon dynamics
   - Cross-validation within training period (k=5 spatial folds)

3. **Apply to Validation Period (2001-2023):**
   - Predict daily rainfall using ERA5 predictors from 2001-2023
   - Compare to observed CHIRPS

4. **Stationarity Metrics:**
   - **H1:** If stationary, model bias should be constant over time
   - **Test:** Plot 5-year running mean of (Predicted - Observed) from 2001-2023
   - **Hypothesis:** Bias will systematically increase or decrease → non-stationarity
   - **Quantitative Test:** Mann-Kendall trend test on bias time series (p < 0.05 → reject stationarity)
   - **Spatial Consistency:** Are trends consistent across different climate zones (Sahel vs. Guinea)?

5. **Alternative Hypothesis:** Changes could be due to CHIRPS satellite algorithm changes, not climate
   - **Control:** Repeat test using gauge-only data if available, or cross-validate with ERA5 precipitation

**Expected Outcome:** Non-stationarity detected (based on known WAM variability literature)

*Deliverable:* Stationarity test report, publication-quality figures

---

**WP2: Non-Stationary Model Development (Months 9-18)**

*Addressing the Stationarity Flaw:*

**Approach 1: Time-Varying Covariate (Primary)**

If WP1 confirms non-stationarity:

1. **Augment Predictor Set:**
   - Add a "climate state" variable to capture long-term change
   - **Option A:** 5-year running mean of regional T2m anomaly (relative to 1981-2010 baseline)
   - **Option B:** Global Mean Surface Temperature (GMST) anomaly from CMIP6 models
   - **Option C:** Decadal oscillation indices (AMO, if relevant)

2. **Re-train RF on Full Period (1981-2023):**
   - Now the model learns: "In a +0.5°C world, q850 = X produces Y mm/day; in a +1.0°C world, q850 = X produces Z mm/day"
   - This allows the q850-rainfall relationship to evolve with temperature

3. **Validation:**
   - **Temporal:** Train on 1981-2015, validate on 2016-2023 (recent unseen years)
   - **Metrics:**
     - **Skill Scores:** RMSE, Bias, Correlation, Perkins Skill Score (distribution overlap)
     - **Extremes:** POD (Probability of Detection) and FAR (False Alarm Rate) for >50mm/day events
     - **Seasonal Metrics:** Monsoon onset date (defined as pentad of 5mm/day threshold crossing)

4. **Compare:** Stationary model (WP1) vs. Non-stationary model (WP2)
   - **Hypothesis:** Non-stationary model has lower RMSE and better extreme event skill

**Approach 2: Time-Stratified Training (Alternative)**

- Train separate models for each decade (1981-1990, 1991-2000, ..., 2011-2020)
- Interpolate model parameters over time
- (More complex, used if Approach 1 insufficient)

*Deliverable:* Validated non-stationary RF model (.pkl), performance report

---

**WP3: Bias Correction of CMIP6 Predictors (Months 15-24)**

*Addressing the Bias Flaw:*

**Quantile Delta Mapping (QDM) Implementation:**

QDM adjusts the entire distribution of CMIP6 variables while preserving the climate change signal.

**For each CMIP6 model, each variable, each grid cell:**

1. **Historical Calibration (1981-2014):**
   - Calculate empirical CDFs: F_obs (from ERA5), F_hist (from CMIP6 historical)
   - Calculate future CDF: F_fut (from CMIP6 SSP scenarios, e.g., 2071-2100)

2. **Bias Correction (for each day in future):**
   ```
   X_corrected(t) = F_obs^-1[ F_fut(X_raw(t)) ]
   ```
   - This says: "Find the quantile of the raw future value in the future distribution, then map it to the observed distribution at that same quantile"

3. **Preserve Change:**
   - Absolute change preserved for temperature
   - Relative change preserved for precipitation (multiplicative)

4. **Apply to All Predictors:**
   - q850, u850, v850, ω700, z500, MSLP, TCWV, T2m
   - **Spatial Consistency:** Preserve spatial gradients

**Comparison Experiment (RQ3):**

Downscale 2071-2100 using:
- **Method A:** No bias correction (raw CMIP6)
- **Method B:** Linear scaling (mean + std adjustment)
- **Method C:** QDM

Compare results → Demonstrate QDM superiority

*Deliverable:* Bias-corrected CMIP6 predictor dataset (1981-2100), methodology paper

---

**WP4: Application to CMIP6 and Ensemble Generation (Months 22-36)**

*Creating the Final Product:*

1. **For Each CMIP6 Model (n=8-10):**
   - Apply trained non-stationary RF (from WP2) to bias-corrected predictors (from WP3)
   - Output: Daily 5km rainfall, 1981-2100, for each SSP scenario
   - **Computation:** ~36,500 days × 400,000 grid cells × 10 models = ~150 GB per scenario

2. **Ensemble Statistics:**
   - Multi-model mean
   - Inter-model spread (standard deviation)
   - 10th/90th percentile range

3. **Climate Change Metrics (RQ4):**
   - **Seasonal Totals:** JJA rainfall (mm), compare 1995-2014 vs. 2050-2069 vs. 2080-2099
   - **Onset/Cessation:** Monsoon timing shifts
   - **Extremes:** Frequency of daily rainfall >50mm, >100mm
   - **Dry Spells:** Maximum consecutive dry days (CDD)

4. **Comparison to Raw CMIP6:**
   - Aggregate downscaled to CMIP6 resolution
   - Compare change signals → Demonstrate added value of downscaling (captures sub-grid variability)

*Deliverable:* 5km precipitation ensemble (NetCDF), ~500GB total, hosted on Zenodo or ESGF

---

**WP5: Spatial and Process-Based Validation (Months 30-40) [NEW]**

*Enhanced Validation Beyond Metrics:*

**Objective:** Ensure downscaling captures realistic physical processes, not just statistical fit.

**Validation Tests:**

1. **Spatial Gradients (RQ5):**
   - Compare observed vs. downscaled annual rainfall transects (coast-to-Sahel)
   - Metric: Gradient preservation score

2. **Diurnal Cycle (if sub-daily data available):**
   - WAM rainfall peaks in late afternoon/evening
   - Check if model captures this (requires 3-hourly ERA5)

3. **Mesoscale Convective Systems (MCS):**
   - MCS produce 70% of Sahel rainfall
   - Do downscaled extremes occur in realistic spatial clusters?
   - Metric: Spatial autocorrelation of extreme events

4. **Drought Events:**
   - Validate against known droughts (1983-1985, 2011-2012)
   - Does model reproduce magnitude and spatial extent?

5. **Cross-Dataset Validation:**
   - Compare to TAMSAT, IMERG (alternative satellite products) for 2015-2023

*Deliverable:* Comprehensive validation report, supplementary paper

---

**WP6: Dissemination and User Engagement (Months 36-42)**

*Ensuring Usability:*

1. **Open Data Repository:**
   - Upload to Zenodo with DOI
   - NetCDF format (CF-compliant)
   - Detailed metadata, user guide

2. **Impact Model Testing:**
   - Collaborate with hydrologists, agronomists to test dataset in their models
   - Collect feedback

3. **Workshops:**
   - Train regional scientists (WASCAL, ACMAD) in data access and interpretation

4. **Policy Briefs:**
   - Non-technical summaries for National Met Services, ECOWAS

*Deliverable:* Dataset, documentation, training materials

---

### 5. Expected Outcomes and Innovation

**Deliverables:**
1. **First rigorously-validated, non-stationary, bias-corrected 5km precipitation ensemble for West Africa (2015-2100)**
2. **Open-source downscaling framework** (Python package)
3. **4-5 Publications:**
   - Paper 1: Stationarity testing framework
   - Paper 2: Non-stationary RF downscaling methodology
   - Paper 3: CMIP6 bias correction for WAM (QDM application)
   - Paper 4: Future WAM changes (2050-2100)
   - Paper 5 (optional): Impact model application (co-authored)

**Scientific Contributions:**
- **Methodological:** Rigorous stationarity testing protocol (transferable globally)
- **Technical:** Demonstrates QDM superiority for WAM
- **Regional:** Most credible high-res projections for West Africa to date

**Societal Impact:**
- Direct input to agricultural planning (crop models)
- Water resource management (reservoir design)
- Flood risk assessment
- National climate adaptation plans

---

### 6. Feasibility and Resources

**Data:** Freely available (ERA5, CHIRPS, CMIP6 via ESGF)
**Computational:**
- Training: University HPC cluster (1,000 core-hours)
- Application: Cloud resources (AWS/Google Cloud, $20,000 budget)
- Storage: 1TB (dataset archiving)

**Software:** Python (xarray, sklearn, dask for parallel processing)
**Expertise Required:** Statistical climatology, ML, big data processing, WAM dynamics
**Collaboration:** WASCAL network, ACMAD, AMMA-2050 project alumni

---

### 7. Timeline Summary

| Phase | Months | Key Milestones |
|-------|--------|----------------|
| Stationarity Test | 1-9 | Hypothesis test, initial paper |
| Non-Stationary Model | 9-18 | Model development, validation |
| Bias Correction | 15-24 | QDM application to CMIP6 |
| Downscaling Application | 22-36 | Generate full ensemble |
| Validation | 30-40 | Spatial and process validation |
| Dissemination | 36-42 | Data release, workshops, policy briefs |
| Publications | 12-42 | Continuous writing |

---

### 8. Limitations and Future Work

**Limitations:**
- **CHIRPS Uncertainty:** Not pure "truth," especially in gauge-sparse regions → Quantify and propagate
- **Predictor Selection:** Limited to standard variables → Could explore moisture flux, vorticity
- **Spatial Non-Stationarity:** Current approach assumes temporal non-stationarity is uniform spatially → Future: Spatially-varying parameters
- **Daily Timescale Only:** Sub-daily extremes not captured → Requires 3-hourly data (future work)

**Future Extensions:**
- Deep learning (CNN-LSTM) for spatial coherence
- Multi-variate downscaling (temperature + precipitation jointly)
- Convection-permitting RCM comparison

---

### 9. References (Expanded)

- Baño-Medina et al. (2020). Configuration and intercomparison of deep learning neural models for statistical downscaling. *Geosci. Model Dev.*, 13, 2109-2124.
- Gutiérrez et al. (2019). An intercomparison of a large ensemble of statistical downscaling methods. *J. Climate*, 32, 87-114.
- Lange (2019). Trend-preserving bias adjustment and statistical downscaling with ISIMIP3BASD. *Geosci. Model Dev.*, 12, 3055-3070.

---

[**Due to length, I'll continue with Projects 4 and 5 in the next response. Would you like me to proceed, or would you prefer to review these first three improved proposals?**]

---

Let me know if you want me to continue with the improved versions of Projects 4 and 5!
---

# PROJECT 4 (IMPROVED)

## Title: Future Changes in Extreme Precipitation in Coastal West Africa: A Multi-Parameter Non-Stationary EVT Analysis with Engineering Applications

**Principal Investigator:** [Your Name]
**Duration:** 30 months
**Funding Required:** ~$70,000 USD

---

### 1. Introduction and Rationale

Coastal West African cities (Lagos, Accra, Freetown, Conakry) face catastrophic flood risk from extreme rainfall events. Infrastructure (drainage systems, bridges, culverts) was designed using historical return levels (e.g., "1-in-50-year storm"), but anthropogenic climate change is invalidating these statistics.

**The Engineering Challenge:** Civil engineers need updated design values: "What is the new 50-year return level in a +2°C world?" Answering this requires:

1. **Appropriate Climate Data:** Global Climate Models (100-200km) cannot resolve coastal topography or mesoscale convective systems. We must use **Regional Climate Models (RCMs)** like CORDEX-Africa (0.44°, ~50km).

2. **Appropriate Statistical Methods:** The climate is **non-stationary** (warming continuously). Analyzing a future 30-year block (e.g., 2070-2100) as if it were internally stable systematically underestimates risk. We must use **non-stationary Extreme Value Theory (EVT)** where distribution parameters evolve with global temperature.

**This Research:** We will:
- Validate CORDEX-Africa RCMs for extreme rainfall against observations
- Fit **fully non-stationary Generalized Extreme Value (GEV) models** where location, scale, AND shape parameters vary with global warming
- Provide engineering-relevant outputs: return levels as a function of warming level (per degree Celsius)
- Translate findings into policy-ready design recommendations

---

### 2. Literature Review and Research Gaps

**Extreme Value Theory (EVT) Fundamentals:**
The GEV distribution is the statistical foundation for return level estimation (Coles, 2001). For non-stationary climates, parameters are modeled as functions of covariates like time or temperature (Katz et al., 2002).

**CORDEX-Africa:**
The Coordinated Regional Climate Downscaling Experiment produced the first multi-model ensemble of high-resolution (0.44° and 0.22°) projections for Africa (Giorgi et al., 2009; Nikulin et al., 2012). However, systematic evaluation for extreme precipitation is limited.

**Research Gaps:**

**Gap 1: CORDEX Validation for Extremes**
Most CORDEX studies validate mean climatology. Validation specifically for Annual Maxima and EVT statistics (return levels) is sparse, especially for coastal West Africa.

**Gap 2: Single-Parameter Non-Stationarity**
Studies typically model only the GEV location parameter (μ) as time-varying, assuming constant scale (σ) and shape (ξ). However, physics suggests scale should increase with warming (more moisture → higher variability). **Best practice:** Model all three parameters.

**Gap 3: Limited Use of Peak-Over-Threshold (POT)**
Most studies use Annual Maxima Series (AMS, one event/year). POT extracts more events, improving statistical power, but is underutilized.

**Gap 4: Engineering Translation Gap**
Academic studies provide change ratios ("50% increase in intensity") but not actionable design values ("the 50-year event is now X mm/day at +2°C").

---

### 3. Research Questions and Objectives

**Primary Objective:**
To quantify projected changes in the intensity and frequency of extreme daily precipitation for coastal West Africa using state-of-the-art non-stationary EVT applied to the validated CORDEX-Africa ensemble, and translate findings into engineering design guidance.

**Research Questions:**

**RQ1 (Validation):** How well do CORDEX-Africa RCMs reproduce observed extreme rainfall statistics (return levels, return periods) from CHIRPS/ERA5 for the historical period (1981-2014)?

**RQ2 (Methodology):** Does a **fully non-stationary GEV** (all three parameters vary with GMST) outperform simpler configurations (μ only, μ+σ) in terms of AIC/BIC and out-of-sample likelihood?

**RQ3 (Climate Sensitivity):** What is the sensitivity of the 50-year return level to global warming (mm/day per °C) for coastal capitals, and does this vary spatially (Sahel vs. Guinea Coast)?

**RQ4 (Future Projections):** What are the projected 50-year and 100-year return levels under SSP2-4.5 (+2.5°C by 2100) and SSP5-8.5 (+4.5°C), and how does frequency change (e.g., historical 50-year event becomes X-year event)?

**RQ5 (Uncertainty):** What are the dominant sources of uncertainty: inter-model spread, internal variability, or GEV parameter estimation?

---

### 4. Data and Methodology

#### A. Datasets

**Regional Climate Model Projections:**
- **CORDEX-Africa:** 0.44° daily precipitation (pr), 1950-2100
  - **Models:** All available RCMs driven by CMIP5/CMIP6 GCMs
    - Expected: ~12 RCMs (e.g., REMO, CCLM, RegCM, ALADIN, RCA4, HIRHAM5)
  - **Scenarios:** Historical (1950-2014), RCP4.5/SSP2-4.5, RCP8.5/SSP5-8.5
  - **Domain:** Coastal zone (5°W-15°E, 4°N-12°N)

**Observational Validation:**
- **CHIRPS v2.0:** 0.05° daily (1981-2023)
- **ERA5:** 0.25° daily (1950-2023) - dynamically consistent, longer record
- **TAMSAT:** 0.0375° daily (1983-2023) - independent satellite product for cross-validation

**Covariate:**
- **Global Mean Surface Temperature (GMST):** From parent CMIP models
  - Anomaly relative to 1850-1900 baseline

**Ground Observations (if available):**
- National Met Service station data for Lagos, Accra, Freetown (for additional validation)

---

#### B. Methodology (Work Packages)

**WP1: RCM Validation - Historical Extreme Statistics (Months 1-9)**

*Crucial Quality Control Gate*

**Objective:** Identify which CORDEX RCMs skillfully represent extreme rainfall before using them for projections.

**Approach:**

1. **Extract Annual Maxima Series (AMS):**
   - For each RCM and each observation dataset (CHIRPS, ERA5): maximum daily precipitation each year (1981-2014)
   - Separately for DRY season (DJF) and WET season (JJA) for Guinea Coast

2. **Fit Stationary GEV:**
   - To observed AMS: GEV(μ_obs, σ_obs, ξ_obs)
   - To each RCM AMS: GEV(μ_RCM, σ_RCM, ξ_RCM)
   - Maximum Likelihood Estimation (MLE) using R package "extRemes" or Python "scipy.stats"

3. **Calculate Historical Return Levels:**
   - For each: 10-year, 20-year, 50-year, 100-year return levels

4. **Validation Metrics:**
   - **Bias:** (RL_RCM - RL_obs) / RL_obs
   - **Spatial Pattern Correlation:** Does RCM reproduce coastal-inland gradients?
   - **GEV Shape Parameter:** ξ ≈ 0 (Gumbel) vs. ξ > 0 (heavy tail) - consistency check

5. **Model Selection:**
   - **Threshold:** Retain RCMs where |bias| < 30% for 20-year return level
   - Expected: Retain 6-10 models (some will fail)
   - **Ensemble Construction:** Equal weight OR weight by skill score

**Peak-Over-Threshold (POT) Comparison (Sub-task):**
- Also fit Generalized Pareto Distribution (GPD) to exceedances over 95th percentile
- Compare AMS vs. POT return levels → assess sensitivity

*Deliverable:* Validation report with model rankings, publication on CORDEX Africa extremes

---

**WP2: Non-Stationary GEV Modeling - The Core Innovation (Months 10-20)**

*State-of-the-Art Methodology*

**Objective:** Fit GEV models where parameters evolve with global warming, capturing the dynamic nature of extremes.

**Model Configurations to Test:**

1. **Stationary (Baseline):**
   ```
   μ, σ, ξ = constants
   ```

2. **Non-Stationary Location Only (Common):**
   ```
   μ(t) = μ₀ + α × GMST(t)
   σ, ξ = constants
   ```

3. **Non-Stationary Location + Scale (Better):**
   ```
   μ(t) = μ₀ + α × GMST(t)
   σ(t) = σ₀ × exp(β × GMST(t))  [log-linear to ensure σ > 0]
   ξ = constant
   ```

4. **Fully Non-Stationary (Proposed - NEW):**
   ```
   μ(t) = μ₀ + α × GMST(t)
   σ(t) = σ₀ × exp(β × GMST(t))
   ξ(t) = ξ₀ + γ × GMST(t)  [with constraints to maintain validity]
   ```

**For Each Validated RCM:**

1. **Data Preparation:**
   - AMS for full period (1950-2100)
   - Corresponding GMST time series

2. **Model Fitting:**
   - Fit all four model configurations using MLE
   - Use R package "ismev" or "extRemes" (supports non-stationary)

3. **Model Selection:**
   - **Akaike Information Criterion (AIC):** Lower is better (penalizes overfitting)
   - **Bayesian Information Criterion (BIC):** More conservative than AIC
   - **Likelihood Ratio Test:** Is added complexity justified?
   - **Out-of-Sample Validation:** Fit on 1950-2050, validate on 2051-2100 (log-likelihood)

4. **Parameter Interpretation (RQ3):**
   - **α (mm/day per °C):** Sensitivity of location (mean extreme magnitude)
   - **β (dimensionless):** Sensitivity of scale (variability of extremes)
   - **γ (per °C):** Sensitivity of shape (tail heaviness)
   - Hypothesis: α > 0 (intensification), β > 0 (increased variability), γ ≈ 0? (uncertain)

5. **Spatial Heterogeneity:**
   - Fit models for different climate zones:
     - Coastal Guinea (Lagos, Accra): monsoon-dominated
     - Sahel (northern fringe): isolated convective storms
   - Test if α varies (spatial non-uniformity)

**Ensemble Approach:**
- Fit to each RCM separately → multi-model ensemble of GEV parameters
- Account for inter-model uncertainty

*Deliverable:* Fitted GEV parameter distributions, model comparison paper

---

**WP3: Return Level Projections and Engineering Outputs (Months 18-26)**

*Translating Science to Practice*

**Objective:** Provide actionable, engineering-relevant return levels for infrastructure design.

**Calculation:**

For a given warming level (e.g., +2°C), the T-year return level is:

```
RL_T(ΔT) = μ(ΔT) - (σ(ΔT)/ξ(ΔT)) × [1 - (-ln(1 - 1/T))^(-ξ(ΔT))]
```

Where μ, σ, ξ are functions of GMST anomaly (ΔT).

**Outputs:**

1. **Return Level vs. Warming Curves:**
   - Plot 50-year RL as a function of GMST (0 to +5°C)
   - Separate curves for each city, each RCM, plus ensemble mean

2. **Scenario-Specific Values (RQ4):**
   - **Historical (1995-2014, +1.0°C):** 50-year RL = X mm/day
   - **SSP2-4.5 (2081-2100, +2.5°C):** 50-year RL = Y mm/day → +Z% increase
   - **SSP5-8.5 (2081-2100, +4.5°C):** 50-year RL = W mm/day

3. **Frequency Change (Return Period Shift):**
   - "A historical 50-year event (X mm/day) becomes a Y-year event at +2°C"
   - Calculate using inverse CDF

4. **Design Tables for Engineers:**
   | City | Warming | 10-yr RL | 25-yr RL | 50-yr RL | 100-yr RL |
   |------|---------|----------|----------|----------|-----------|
   | Lagos | +0°C | 120 mm | 150 mm | 175 mm | 200 mm |
   | Lagos | +2°C | 135 mm | 170 mm | 200 mm | 230 mm |
   | ...  | ...  | ...    | ...    | ...    | ...    |

**Uncertainty Quantification (RQ5):**

Decompose total uncertainty using ANOVA-style framework:

1. **GEV Parameter Uncertainty:** From MLE confidence intervals (bootstrap)
2. **Inter-Model Spread:** Variance across CORDEX ensemble
3. **Scenario Uncertainty:** SSP2-4.5 vs. SSP5-8.5
4. **Internal Variability:** From RCM ensemble members (if available)

Report as: "50-year RL = 200 ± 25 mm/day (90% CI), with 60% from model spread, 30% from GEV uncertainty, 10% from scenario"

*Deliverable:* Return level database, engineering design guide (PDF/Web tool)

---

**WP4: Policy Translation and Stakeholder Engagement (Months 24-30)**

*Ensuring Uptake*

**Objective:** Make research accessible to end-users (government engineers, urban planners).

**Activities:**

1. **Policy Briefs:**
   - Non-technical summaries for National Disaster Management Agencies
   - Key message: "Update design codes now; historical values are obsolete"

2. **Web Tool (Interactive Visualization):**
   - Input: City, Warming Scenario
   - Output: Return level curve, downloadable data
   - Platform: Shiny (R) or Streamlit (Python), hosted on university server

3. **Training Workshops:**
   - For National Met Services and Public Works Ministries
   - Lagos, Accra, Freetown (3 workshops, 2 days each)
   - Content: How to use EVT outputs in drainage design

4. **Co-Production with Engineers:**
   - Partner with consulting firms (if possible) to pilot new design values in real projects
   - Case study: Re-design of a stormwater drain using updated 50-year RL

*Deliverable:* Web tool, training materials, policy briefs, stakeholder report

---

### 5. Expected Outcomes and Innovation

**Deliverables:**

1. **First comprehensive validation of CORDEX-Africa for extreme precipitation**
2. **Fully non-stationary GEV framework** (all parameters varying) - methodological advancement
3. **Engineering design database:** Return levels for 20 cities × 5 warming levels × 4 return periods
4. **Interactive web tool** for infrastructure planning
5. **3-4 Publications:**
   - Paper 1: CORDEX-Africa extreme rainfall validation
   - Paper 2: Multi-parameter non-stationary GEV methodology
   - Paper 3: Future return level projections for West Africa
   - Paper 4 (optional): Engineering application case study

**Scientific Contributions:**

- **Methodological:** Demonstrates superiority of fully non-stationary GEV (transferable globally)
- **Regional:** Most rigorous extreme rainfall projections for coastal West Africa
- **Applied:** Bridges science-policy gap with engineering-ready outputs

**Societal Impact:**

- **Direct:** Updated design codes prevent infrastructure failure, save lives
- **Economic:** Avoid billions in flood damage from under-designed systems
- **Capacity Building:** Train local scientists and engineers in modern EVT methods

---

### 6. Feasibility and Resources

**Data:** Freely available (CORDEX via ESGF, CHIRPS, ERA5)
**Software:** Open-source (R: extRemes, ismev; Python: scipy, climex)
**Computational:** Standard workstation (EVT fitting is not computationally intensive)
**Training:** Extreme value statistics, RCM evaluation, stakeholder communication
**Collaboration:**
- West African Met Services (validation data, stakeholder access)
- Regional universities (WASCAL network)
- Engineering firms (application testing)

**Budget Breakdown:**
- Travel for workshops: $25,000
- Web tool development: $15,000
- Research assistant (data processing): $20,000
- Contingency: $10,000

---

### 7. Timeline Summary

| Phase | Months | Key Activities |
|-------|--------|----------------|
| RCM Validation | 1-9 | Historical extreme statistics, model selection |
| GEV Modeling | 10-20 | Fit non-stationary models, parameter estimation |
| Projections | 18-26 | Return level calculations, uncertainty analysis |
| Translation | 24-30 | Policy briefs, web tool, workshops |
| Publications | 12-30 | Continuous manuscript development |

---

### 8. Limitations and Future Work

**Limitations:**

- **CORDEX Resolution:** 50km still misses very localized extremes (e.g., thunderstorm cells)
- **Convection Parameterization:** All RCMs parameterize convection (not explicitly resolved) → inherent uncertainty
- **Coastal Effects:** Sea breeze, orographic enhancement partly captured but not at fine scale
- **Compound Events:** Does not address combined rainfall + storm surge (future work)

**Future Extensions:**

- **Convection-Permitting Models (CPMs):** As 4km CORDEX data becomes available, repeat analysis
- **Sub-Daily Extremes:** Hourly rainfall (currently unavailable for CORDEX)
- **Multi-Variate EVT:** Joint rainfall-wind extremes for tropical cyclones
- **Impact Modeling:** Link to flood inundation models for direct risk assessment

---

### 9. References (Updated)

- Coles, S. (2001). *An Introduction to Statistical Modeling of Extreme Values*. Springer.
- Giorgi et al. (2009). Addressing climate information needs at the regional level: The CORDEX framework. *WMO Bulletin*, 58(3), 175.
- Katz et al. (2002). Statistics of extremes in hydrology. *Advances in Water Resources*, 25, 1287-1304.
- Nikulin et al. (2012). Precipitation climatology in an ensemble of CORDEX-Africa regional climate simulations. *J. Climate*, 25, 6057-6078.

---

---

# PROJECT 5 (IMPROVED)

## Title: Interpretable and Spatially-Resolved AI Climate Emulators: Integrating XAI, Dimensionality Reduction, and Multi-Variable Emulation for Policy-Relevant Scenario Exploration

**Principal Investigator:** [Your Name]
**Duration:** 40 months
**Funding Required:** ~$90,000 USD

---

### 1. Introduction and Rationale

Earth System Models (ESMs) are humanity's most sophisticated tools for understanding climate futures, but they are **computationally prohibitive**. A single CMIP6 model simulation (2015-2100) requires months on supercomputers, creating a bottleneck that prevents:
- Exploration of thousands of emission pathways (beyond the 5-10 standard SSPs)
- Real-time climate services for policymakers
- Rapid sensitivity testing for intervention strategies

**AI-Driven Emulators** offer a solution: Machine learning models trained on existing ESM outputs can replicate their behavior in seconds, enabling massive scenario exploration.

**The Problems with Current Emulators:**

1. **The "Black Box" Crisis:**
   - Most emulators (Neural Networks, Random Forests) are opaque
   - We don't know *why* they predict what they predict
   - If an emulator says "This emission pathway leads to 3.2°C warming," can we trust it? Or did it learn a spurious correlation?
   - **Scientific Risk:** Publishing policy-relevant projections from unexplained models is scientifically untenable

2. **The "Global Mean" Limitation:**
   - Most emulators predict only Global Mean Temperature (GMT)
   - But regional policymakers need regional temperature, precipitation, sea ice extent, etc.
   - A "global mean" emulator is scientifically interesting but practically limited

3. **Temperature-Only Focus:**
   - Most emulators ignore precipitation (harder to emulate, but more impactful for society)
   - Multi-variable emulation (T, precip, soil moisture) is the frontier but rare

**This Research:** We will develop a **next-generation emulator framework** that:
- Uses **eXplainable AI (XAI)** to validate that models learn physically-plausible relationships
- Uses **Dimensionality Reduction (PCA, Autoencoders)** to emulate full spatial patterns, not just global means
- **Extends to multi-variable emulation** (temperature + precipitation) with physical consistency constraints
- Provides **uncertainty quantification** through ensemble approaches

---

### 2. Literature Review and Research Gaps

**Climate Emulation Evolution:**

- **Early:** Linear pattern scaling (Santer et al., 1990) - too simple
- **Intermediate:** Statistical emulators (Gaussian Process - Holden et al., 2010) - computationally expensive for high dimensions
- **Modern:** Machine learning (Beusch et al., 2020; Watson-Parris et al., 2022) using Random Forest, Neural Networks on **ClimateBench** dataset
- **Frontier:** Explainability (Mamalakis et al., 2022 using SHAP for climate), spatial emulation (Mansfield et al., 2020 using PCA)

**Research Gaps:**

**Gap 1: XAI Rarely Used for Physical Validation**
Studies report RMSE but rarely use SHAP, LIME, or other XAI methods to verify whether the AI learned correct physics (e.g., logarithmic CO₂ forcing, aerosol cooling).

**Gap 2: Spatial Emulation Immature**
- Most spatial emulators use naive approaches (separate model per grid cell - inefficient) or basic PCA
- Advanced methods (Convolutional Neural Networks, Autoencoders) underexplored
- **Challenge:** Preserving spatial coherence, teleconnections

**Gap 3: Precipitation Emulation Rare**
Precipitation is harder (non-Gaussian, spatial intermittency) but more policy-relevant. Few emulators tackle it.

**Gap 4: Multi-Variable Consistency**
If emulating T and P separately, they may be physically inconsistent (e.g., predict hot + wet when should be hot + dry). Need coupled emulation with energy/water balance constraints.

**Gap 5: Uncertainty Quantification Weak**
Most emulators provide point estimates, not uncertainty ranges. Policy needs probabilistic outputs.

---

### 3. Research Questions and Objectives

**Primary Objective:**
To develop, validate, and apply a **physically-interpretable, spatially-resolved, multi-variable** climate emulator for temperature and precipitation, with explainability at its core, enabling rapid exploration of 10,000+ emission scenarios.

**Research Questions:**

**RQ1 (Interpretability - The Core):** Using XAI (SHAP), do Random Forest and Neural Network emulators learn physically-consistent relationships for:
- Logarithmic CO₂ radiative forcing?
- Linear CH₄ forcing?
- Negative aerosol (SO₂) cooling?
- Or do they "cheat" using spurious correlations in the training data?

**RQ2 (Emulator Architecture):** How do different model architectures compare for GMT emulation?
- Random Forest
- Feedforward Neural Network (FNN)
- Recurrent Neural Network (LSTM - for temporal memory)
- Convolutional LSTM (for spatial-temporal patterns)

**RQ3 (Spatial Emulation - Dimensionality Reduction):** For spatially-resolved temperature:
- Does PCA-based emulation (predict PC scores) outperform naive grid-cell-by-grid-cell emulation?
- Does a Convolutional Autoencoder (non-linear dimension reduction) outperform linear PCA?
- How many modes (PCs/latent dimensions) are needed to capture 95% of spatial variance?

**RQ4 (Multi-Variable Emulation - NEW):** Can a joint emulator for temperature AND precipitation:
- Be trained to respect physical constraints (e.g., Clausius-Clapeyron scaling: 7% precip increase per °C)?
- Outperform independent single-variable emulators?
- Reproduce observed T-P correlations (e.g., monsoon regions vs. subtropics)?

**RQ5 (Scenario Exploration):** Using the validated emulator, what are the climate outcomes of 1,000 hypothetical emission pathways not in CMIP6, and how does uncertainty from emission pathway choice compare to model uncertainty?

---

### 4. Data and Methodology

#### A. Datasets

**Primary Dataset:**
- **ClimateBench v1.0** (Watson-Parris et al., 2022):
  - **Inputs (X):** Annual time-series of emissions/concentrations (1850-2100):
    - CO₂, CH₄, SO₂ (or BC, stratospheric H₂O in extended version)
    - SSP scenarios: 1-1.9, 1-2.6, 2-4.5, 3-7.0, 5-8.5, historical
  - **Outputs (y - Global Mean):**
    - Global Mean Surface Temperature (GMST) from 4 CMIP6 ESMs: CanESM5, IPSL-CM6A-LR, GFDL-ESM4, NorESM2-LM
  - **Outputs (y - Spatial - NEW):**
    - Gridded temperature fields (available from CMIP6 archive, not in standard ClimateBench)

**Augmented Dataset (For WP3-4):**
- **Full CMIP6 Archive (ESGF):**
  - Gridded monthly/annual temperature (tas) and precipitation (pr)
  - Resolution: ~100-200km (depends on model)
  - Download for same 4 ESMs, 1850-2100, all SSPs
  - **Size:** ~500GB (compressed)

**Additional XAI Validation Data:**
- **IPCC AR6 Chapter 7 Figures:** Documented radiative forcing relationships for comparison

---

#### B. Methodology (Work Packages)

**WP1: Baseline Global Mean Emulators (Months 1-8)**

*Replicating ClimateBench with Enhancements*

**Objective:** Establish baseline performance for GMT emulation.

**Approach:**

1. **Data Preparation:**
   - ClimateBench format: X = [CO₂(t), CH₄(t), SO₂(t), ...], y = GMST(t)
   - 80% train, 20% test (held-out SSP scenarios)

2. **Train Multiple Architectures:**

   **A. Random Forest:**
   - sklearn RandomForestRegressor
   - Input: Current + lagged emissions (1-year, 5-year lags to capture thermal inertia)
   - Hyperparameters: n_estimators=500, max_depth tuned via cross-validation

   **B. Feedforward Neural Network:**
   - 3 hidden layers, ReLU activation
   - Batch normalization, dropout for regularization
   - TensorFlow/PyTorch

   **C. LSTM (Temporal Sequence):**
   - Input: Time-series of last 20 years of emissions
   - Output: GMST for current year
   - Captures climate system memory

3. **Evaluation Metrics (RQ2):**
   - RMSE (primary)
   - R² (variance explained)
   - **Peak Warming Error:** Accuracy at maximum GMST (most policy-relevant)
   - **Transient Climate Response (TCR) Error:** How well does emulator reproduce 1% CO₂ increase scenario?

4. **Comparison:**
   - Which architecture performs best?
   - **Hypothesis:** LSTM captures thermal inertia better (lower RMSE)

*Deliverable:* Trained models, performance benchmarks

---

**WP2: eXplainable AI (XAI) for Physical Validation - THE CORE INNOVATION (Months 6-14)**

*Opening the Black Box*

**Objective:** Use SHAP (SHapley Additive exPlanations) to verify emulators learned real physics, not artifacts.

**SHAP Background:**
- SHAP assigns each predictor a "contribution" to each prediction
- Derived from game theory (Shapley values)
- Model-agnostic
- Python package: `shap`

**Implementation:**

1. **For RF and NN models (from WP1):**
   - Calculate SHAP values for all predictions
   - Generate SHAP dependence plots: How does predicted GMST change with CO₂, holding others constant?

2. **Physical Validation Tests (RQ1):**

   **Test 1: CO₂ Forcing Logarithmic?**
   - Plot: SHAP(CO₂) vs. CO₂ concentration
   - Physics expectation: ΔRF ∝ α × ln(CO₂/CO₂₀)
   - Fit curve: Is it logarithmic (R² > 0.95)?
   - **If YES:** Model learned correct physics
   - **If NO (e.g., linear):** Model is unreliable outside training range

   **Test 2: Aerosol Cooling?**
   - Plot: SHAP(SO₂) vs. SO₂ emissions
   - Expectation: Negative slope (cooling effect)
   - Check magnitude: Consistent with IPCC AR6 ERF estimates?

   **Test 3: CH₄ Forcing:**
   - Expected: Sublinear (due to saturation), positive (warming)

   **Test 4: Temporal Lag:**
   - Does model assign more importance to recent emissions than 50-year-old emissions (expect yes, due to ocean heat uptake timescales)?

3. **Comparison Across Models:**
   - Does RF have more interpretable SHAP plots than NN?
   - Are LSTM SHAP patterns harder to interpret (black box risk)?

4. **Failure Mode Analysis:**
   - If model shows spurious relationships, diagnose:
     - Training data artifacts? (e.g., all high-CO₂ scenarios also have high CH₄ → collinearity)
     - Overfitting?
   - Retrain with regularization or augmented data if needed

**Novel Contribution:** This is the first systematic XAI-based physical validation of climate emulators. Results determine which models are "trustworthy" for policy use.

*Deliverable:* XAI validation report, SHAP visualization suite, methodology paper ("Can We Trust AI Climate Emulators?")

---

**WP3: Spatial Emulation - Dimensionality Reduction Approaches (Months 12-26)**

*Moving Beyond Global Means*

**Objective:** Emulate full spatial patterns of warming, not just GMT.

**Challenge:** A global map has ~50,000 grid cells. Training 50,000 separate models is inefficient and ignores spatial covariance.

**Solution:** Dimensionality reduction to find dominant patterns.

**Approach 3A: PCA-Based Emulation**

1. **Perform PCA on Spatial Temperature Anomalies:**
   - Input: All gridded temperature maps from 4 ESMs, 1850-2100, all scenarios
   - Reshape to (n_timesteps × n_pixels) matrix
   - Compute PCA → Extract EOFs (spatial patterns) and PCs (time-series scores)
   - Typically, first 10-20 PCs explain >95% variance
     - PC1: Global warming pattern
     - PC2: Land-ocean contrast
     - PC3: Polar amplification
     - PC4: ENSO-like variability
     - etc.

2. **Train Emulator on PC Scores:**
   - **New Target:** y = [PC1(t), PC2(t), ..., PC20(t)] (vector, not scalar)
   - **Input:** X = emissions (same as WP1)
   - **Model:** Multi-output Random Forest or multi-head Neural Network
   - Train: Predict PC scores from emissions

3. **Reconstruct Spatial Field:**
   ```
   T(x,t) = Mean(x) + Σ [PC_i(t) × EOF_i(x)]
   ```

4. **Validation (RQ3):**
   - Compare reconstructed maps to actual ESM maps on held-out scenarios
   - Metrics:
     - **Spatial RMSE**
     - **Pattern Correlation:** How well are regional warming patterns reproduced?
     - **Regional Averages:** Accuracy for 20 IPCC AR6 regions

**Approach 3B: Convolutional Autoencoder (Non-Linear Dimension Reduction)**

1. **Train Autoencoder:**
   - **Encoder:** Conv layers to compress spatial map → latent vector (e.g., 50 dims)
   - **Decoder:** De-conv layers to reconstruct map from latent vector
   - Train on all ESM maps (unsupervised)

2. **Emulator on Latent Space:**
   - Train RF/NN to predict latent vector from emissions
   - Decode to get full spatial field

3. **Comparison:** PCA vs. Autoencoder (RQ3)
   - **Hypothesis:** Autoencoder captures non-linear patterns better (e.g., regional rainfall-temperature coupling)
   - **Trade-off:** Autoencoder is less interpretable

**Approach 3C: Naive Baseline (for comparison)**
- Train separate model for each of 20 IPCC regions' mean temperature
- No spatial coherence enforced

**Expected Result:** PCA-based emulation achieves 95% accuracy with 20x fewer parameters than naive approach.

*Deliverable:* Spatial emulator, validation report, pattern maps

---

**WP4: Multi-Variable Emulation (Temperature + Precipitation) - FRONTIER (Months 20-34)**

*The Hardest Challenge*

**Objective:** Jointly emulate temperature AND precipitation with physical consistency.

**Why It's Hard:**
- Precipitation is:
  - Highly variable spatially
  - Non-Gaussian (intermittent, many zero days)
  - Non-linear response to forcings (regional wetting/drying patterns complex)

**Approach:**

**Step 1: Separate Single-Variable Precipitation Emulator (Baseline)**

1. Download CMIP6 annual precipitation (pr) for 4 ESMs
2. Apply PCA to precip anomalies (separate from temperature PCA)
3. Train emulator: Emissions → Precip PC scores
4. Validate independently

**Step 2: Multi-Variable Joint Emulator (Coupled)**

**Architecture:** Multi-Task Learning Neural Network

```
Emissions (X) 
   ↓
Shared Hidden Layers
   ↓ ↓
Task-Specific Heads
   ↓           ↓
T-PCs        P-PCs
```

**Physical Constraint Layer (Novel):**
- Add a constraint that enforces approximate Clausius-Clapeyron scaling:
  - Regional precip change ~ 2-3% per °C regional warming (literature-based range)
- Implemented as:
  - Custom loss function: L = L_T + L_P + λ × |ΔP/ΔT - α|
  - α = expected scaling (learned or fixed)

**Validation (RQ4):**

1. **Univariate Performance:** Does multi-task hurt T or P accuracy?
2. **T-P Correlation:** In monsoon regions, does emulator reproduce observed positive T-P correlation?
3. **Scaling Consistency:** Is ΔP/ΔT realistic compared to CMIP6 ensemble?

**Alternative if Multi-Task Fails:**
- Use independent emulators but post-process to enforce consistency

*Deliverable:* Multi-variable emulator (if successful), or recommendation of limits

---

**WP5: Massive Scenario Exploration and Uncertainty Decomposition (Months 30-40)**

*The Payoff - Policy Application*

**Objective:** Use validated emulator to explore 10,000 hypothetical emission pathways.

**Scenario Generation:**

**Method A: Random Sampling**
- Generate random trajectories within plausible bounds:
  - CO₂: Peak 400-1200 ppm, peak year 2050-2100
  - CH₄: 1000-4000 ppb
  - SO₂: Declining to zero (air quality policies)

**Method B: Policy-Relevant Pathways**
- Collaborate with IAM modelers or IPCC authors
- Generate scenarios representing:
  - "Delayed action" (peak 2050)
  - "Rapid transition" (peak 2030)
  - "Overshoot and drawdown" (CDR scenarios)

**Analysis (RQ5):**

1. **Run emulator on all 10,000 scenarios**
   - Compute: GMT, regional warming, precip change for each
   - Execution time: ~1 hour (vs. ~10 million model-years of ESM time)

2. **Probabilistic Projections:**
   - Create probability distributions: "What % of plausible pathways lead to >2°C?"
   - Identify "safe operating space" (emission corridors)

3. **Uncertainty Decomposition:**
   - **Pathway uncertainty:** Spread due to scenario choice
   - **Model uncertainty:** Spread across 4 ESMs
   - **Emulator uncertainty:** From ensemble of emulators (e.g., RF + NN)
   - Report: "By 2100, GMT = 2.8°C ± 0.4°C (pathway) ± 0.6°C (model) ± 0.1°C (emulator)"

4. **Interactive Dashboard:**
   - Web tool where users design custom scenarios
   - Real-time visualization of climate response
   - Target audience: Policymakers, educators, IPCC authors

*Deliverable:* Scenario database, web tool, policy report ("Climate Futures Explorer")

---

### 5. Expected Outcomes and Innovation

**Deliverables:**

1. **Open-source emulator framework** (Python package: `climemu` on GitHub/PyPI)
2. **First XAI-validated climate emulator** (trusted by community)
3. **Spatially-resolved emulator** (regional not just global)
4. **Multi-variable emulator prototype** (T+P)
5. **10,000-scenario ensemble dataset** (Zenodo)
6. **Interactive web tool** ("Climate Futures Explorer")
7. **4-5 Publications:**
   - Paper 1: XAI for climate emulator validation (high-impact, e.g., *Nature Climate Change*)
   - Paper 2: Spatial emulation via PCA vs. Autoencoder (*GMD*)
   - Paper 3: Multi-variable emulation with physical constraints (*JAMES*)
   - Paper 4: Massive scenario exploration results (*ERL*)
   - Paper 5 (optional): Policy applications

**Scientific Contributions:**

- **Methodological Breakthrough:** XAI as validation tool → changes how community evaluates emulators
- **Technical Advance:** Best-practice framework for spatial emulation
- **Scientific Frontier:** Multi-variable emulation with constraints
- **Open Science:** Fully reproducible, open-source, openly documented

**Societal Impact:**

- **Policy Tool:** Enables rapid assessment of any proposed emission pathway
- **Transparency:** XAI builds trust between science and policymakers
- **Education:** Web tool for teaching climate dynamics
- **Acceleration:** Speeds up IPCC-style assessments (explore scenarios in hours, not years)

---

### 6. Feasibility and Resources

**Data:** Freely available (ClimateBench, CMIP6 via ESGF)
**Computational:**
- Training: GPU workstation or cloud (AWS, $5,000)
- Inference: Standard laptop (emulator is fast)
- Storage: 1TB (CMIP6 download)

**Software:** Python (TensorFlow/PyTorch, sklearn, shap, xarray)
**Expertise:** Machine learning, climate modeling, statistics, software engineering
**Risk Mitigation:**
- If multi-variable emulation too difficult, focus on temperature (still valuable)
- If Autoencoder underperforms, PCA is robust fallback

**Collaboration:**
- CMIP6 modeling centers (for validation discussions)
- IPCC AR7 authors (for scenario co-design)
- Education NGOs (for web tool user testing)

---

### 7. Timeline Summary

| Phase | Months | Key Activities |
|-------|--------|----------------|
| Baseline GMT Emulation | 1-8 | RF, NN, LSTM training |
| XAI Validation | 6-14 | SHAP analysis, physical validation |
| Spatial Emulation | 12-26 | PCA, Autoencoder, comparison |
| Multi-Variable Emulation | 20-34 | Joint T+P, constraints |
| Scenario Exploration | 30-40 | 10,000 scenarios, web tool |
| Publications | 12-40 | Continuous writing |

---

### 8. Limitations and Future Work

**Limitations:**

- **Data-Driven:** Emulator limited by training data (4 ESMs) → Cannot explore behavior outside CMIP6 envelope
- **Statistical, Not Physical:** No explicit physics (energy balance, fluid dynamics) → Could be integrated in future
- **Annual Resolution:** ClimateBench is annual → Sub-annual variability not captured
- **Simplified Forcings:** Only CO₂, CH₄, SO₂ → Could add land-use, volcanic, solar

**Future Work:**

- **Hybrid Emulators:** Combine ML with simple climate models (e.g., FaIR + NN)
- **Probabilistic Emulation:** Bayesian Neural Networks for uncertainty quantification
- **Extreme Events:** Emulate return periods of heat waves, not just means
- **Carbon Cycle:** Include interactive carbon cycle (CO₂ emissions → concentrations)

---

### 9. References (Expanded)

- Beusch et al. (2020). Emulating Earth system model temperatures with MESMER. *Geosci. Model Dev.*, 13, 2997-3017.
- Mansfield et al. (2020). Predicting global patterns of long-term climate change from short-term simulations using machine learning. *npj Climate Atmos. Sci.*, 3, 44.
- Mamalakis et al. (2022). Investigating the fidelity of explainable AI methods for climate applications. *Artificial Intelligence for the Earth Systems*, 1(4), e220012.
- Watson-Parris et al. (2022). ClimateBench v1.0: A benchmark for data-driven climate projections. *JAMES*, 14, e2021MS002954.

---

---

# SUMMARY COMPARISON: ORIGINAL vs. IMPROVED PROPOSALS

| Aspect | Original Proposals | Improved Proposals |
|--------|-------------------|-------------------|
| **Data Plans** | Vague, no sample sizes | Specific datasets, expected counts, acquisition timelines |
| **Validation** | Basic metrics (AUC, RMSE) | Multi-method validation (stats, physics, field, cross-dataset) |
| **Uncertainty** | Rarely mentioned | Explicit UQ, error propagation, ensemble spread |
| **Feasibility** | Timeline optimistic | Extended timelines, contingency plans, risk mitigation |
| **Realism** | Some methods untested | Pilot studies, method comparisons, baseline alternatives |
| **Rigor** | Acknowledged flaws | Fixed flaws, addressed directly in methodology |
| **Societal Link** | Claimed but vague | Specific partnerships, workshops, web tools, policy briefs |
| **Publications** | Generic mention | Targeted journals, clear contribution statements |
| **Funding** | Not discussed | Budget estimates, justification |
| **PhD Readiness** | Mostly yes | Absolutely yes - all meet international PhD standards |

---

# RECOMMENDATIONS FOR IMPLEMENTATION

**Priority Ranking (by Achievability + Impact):**

1. **Project 4 (EVT Extremes):** HIGH - Data available, methods established, high impact
2. **Project 2 (UHI Freetown):** MEDIUM-HIGH - Cloud challenges, but manageable
3. **Project 5 (Emulator):** MEDIUM-HIGH - Ambitious XAI, but frontier science
4. **Project 3 (Downscaling):** MEDIUM - Computational demands, complex workflow
5. **Project 1 (Landslide):** MEDIUM - Data collection bottleneck, but critical need

**For Each Project:**
- Secure collaborators BEFORE starting (Met Services, hospitals, universities)
- Pilot feasibility studies in Year 1 (e.g., test cloud frequency, data access)
- Plan for 2-3 publications, not 5 (realistic expectation)
- Allocate 20% time to unexpected challenges
- Engage stakeholders early (not at end)

---

**END OF IMPROVED PROPOSALS DOCUMENT**

