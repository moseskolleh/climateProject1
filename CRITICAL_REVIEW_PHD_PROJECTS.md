# CRITICAL REVIEW OF PhD PROJECTS
## Comprehensive Analysis of Weaknesses, Strengths, Feasibility, and Impact
**Review Date:** December 7, 2025
**Reviewer Perspective:** Independent scientific assessment focusing on PhD viability

---

## EXECUTIVE SUMMARY

This document provides critical feedback on five PhD research proposals in climate science. Each project is evaluated across four dimensions:
1. **Scientific Weaknesses** - Methodological gaps, unrealistic assumptions, missing elements
2. **Scientific Strengths** - Novel contributions, methodological rigor, advancement beyond state-of-the-art
3. **Feasibility** - Data availability, timeline realism, resource requirements, risk factors
4. **Usefulness** - Scientific impact, societal relevance, policy applicability, scalability

**Overall Assessment:** All five projects are scientifically sound and PhD-worthy, but they suffer from common weaknesses:
- **Over-ambition in scope** (trying to do too much in 30-42 months)
- **Validation optimism** (assuming data will be available without contingency)
- **Publication pressure** (targeting 3-5 papers may delay graduation)
- **Stakeholder engagement naiveté** (assuming government agencies will enthusiastically collaborate)
- **Computational underestimation** (minimizing HPC needs and data storage challenges)

**Recommendation:** Each project needs focused trimming to a single core innovation, with secondary objectives moved to "future work."

---

# PROJECT 1: LANDSLIDE SUSCEPTIBILITY MAPPING

## CRITICAL WEAKNESSES

### 1. The "Sampling Bias Correction" May Be Circular Logic
**Problem:** The proposal claims to correct sampling bias using spatial point process models, but this requires knowing the "true" underlying susceptibility distribution, which is exactly what we're trying to estimate. This is potentially circular.

**Specific Issue:**
- The model λ(s) = ρ(s) × θ(s) assumes multiplicative separability of susceptibility and observability
- In reality, landslides are MORE likely to be observed WHERE they occur (roads are built in valleys, landslides on slopes) → observability and susceptibility are NOT independent
- If observability θ(s) is correlated with true susceptibility ρ(s), the correction will fail

**Evidence:** Steger et al. (2021) themselves note this limitation but don't solve it.

**Impact:** This is the PhD's core novelty - if it doesn't work, the thesis lacks a unique contribution.

**Fix Needed:**
- Need a **validation strategy that doesn't assume we know the truth**
- Suggest: Use simulated landslide data where true susceptibility is known, test if method recovers it
- Alternative: Frame contribution more modestly as "exploring" bias correction, not "solving" it

### 2. Field Validation is Underpowered
**Problem:** 30-50 field sites cannot validate a 300-800 event inventory across an entire country.

**Statistical Reality:**
- 50 sites ÷ 5 susceptibility classes = 10 sites per class
- With natural variability, this gives ~±30% confidence intervals on validation metrics
- Not sufficient for publication in top-tier journals

**Fix:** Either increase field campaign ($$$ and time) or be honest about validation limitations.

### 3. Physics-Based Validation is Weak
**Problem:** The infinite slope model (Factor of Safety) is too simplified for tropical environments:
- Assumes homogeneous soil (false for weathered tropical geology)
- Requires cohesion and friction angle (unavailable for Sierra Leone at 30m)
- Ignores tree root reinforcement (major stability factor in forests)
- Assumes planar failure surface (most tropical slides are complex)

**Reality Check:** Any correlation between ML predictions and FS will be weak and hard to interpret.

**Fix:** Either invest in soil sampling (expensive) or downgrade this to "exploratory" rather than "validation."

### 4. Dynamic Hazard Framework is Bolt-On, Not Integrated
**Problem:** WP6 treats dynamic hazard as an afterthought - multiply static susceptibility by rainfall threshold. This ignores:
- Antecedent moisture conditions (critical for triggering)
- Spatial variability of rainfall at landslide scale (<1 km)
- Non-linear triggering thresholds (not a simple product)

**Impact:** The "operational early warning system" deliverable is oversold.

**Fix:** Reframe as "proof-of-concept" rather than operational system.

### 5. Timeline Optimism
**36 months with overlapping WPs looks feasible on paper, but:**
- Field work in Sierra Leone during rainy season (May-Oct) when landslides occur = dangerous/impossible
- Dry season field work won't capture active failures
- This forces field work to Year 2 or 3, creating bottleneck
- If inventory is smaller than expected (n=100 instead of 300), need more time for remote sensing detection

**Realistic Timeline:** 42-48 months

## SCIENTIFIC STRENGTHS

### 1. Addresses a Real Gap
The sampling bias problem is underappreciated in landslide literature. Even if the proposed solution is imperfect, **raising the issue systematically** is a contribution.

### 2. Ensemble Approach is Sound
Using RF + XGBoost + MaxEnt captures different model assumptions. This is best practice and uncommon in regional studies.

### 3. Multi-Source Inventory is Rigorous
Combining literature + Sentinel-1/2 + field validation + quality tiers is excellent data practice. Many studies use only one source.

### 4. Regional Relevance is High
Sierra Leone desperately needs this. The 2017 Regent disaster killed 1,000+ people. Government stakeholders will engage.

## FEASIBILITY ASSESSMENT

| Aspect | Score (1-5) | Comment |
|--------|-------------|---------|
| Data Availability | 4 | Satellite data free; inventory compilation challenging but doable |
| Technical Skills Required | 4 | Spatial stats + ML + GIS - steep learning curve but achievable |
| Computational Resources | 5 | Low - standard laptop sufficient |
| Field Work Logistics | 2 | **MAJOR RISK** - Sierra Leone infrastructure poor, rainy season access limited |
| Stakeholder Collaboration | 4 | Good existing contacts, but government capacity low |
| Timeline Realism | 3 | 36 months tight; 42-48 safer |
| Budget Adequacy | 4 | $120k reasonable if field work efficient |
| **OVERALL FEASIBILITY** | **3.5/5** | **MODERATE** - field work is the bottleneck |

## USEFULNESS TO SCIENCE AND SOCIETY

### Scientific Impact: HIGH (4/5)
- **Novel Method:** First systematic application of spatial point process bias correction to landslide mapping (if successful)
- **Methodological Advance:** Ensemble + physics validation framework is transferable
- **Publication Potential:** 2-3 solid papers in *Landslides*, *Natural Hazards*, *Geomorphology*
- **Citation Potential:** High - fills regional gap

### Societal Impact: VERY HIGH (5/5)
- **Direct Application:** National Disaster Management Agency can use for zoning
- **Lives Saved:** Potential to prevent future Regent-scale disasters
- **Policy Relevance:** Informs land-use planning in Freetown hillsides
- **Capacity Building:** Trains local scientists in modern geohazard methods
- **Scalability:** Framework applicable across West Africa

### Cost-Benefit Ratio: EXCELLENT
$120k investment for a product that could save hundreds of lives = excellent ROI

## RECOMMENDATIONS FOR IMPROVEMENT

### MUST DO:
1. **Add simulated validation** of bias correction method (Month 6-9)
2. **Realistic field work timeline** with weather contingency (extend to 42 months)
3. **Downgrade physics validation** to "exploratory consistency check" not "validation"
4. **Simplify dynamic component** or remove entirely (makes it too complex)

### SHOULD DO:
5. **Target 2 papers, not 4** - one on method (main thesis), one on application
6. **Pre-register analysis plan** to avoid p-hacking with multiple ML models
7. **Include power analysis** for field validation (how many sites needed for X% confidence?)

### COULD DO:
8. Collaborate with geotechnical engineers at Njala University for soil data
9. Partner with World Bank (has Sierra Leone disaster risk project) for co-funding

---

# PROJECT 2: URBAN HEAT ISLAND ANALYSIS

## CRITICAL WEAKNESSES

### 1. Thermal Downscaling Validation is Partially Circular
**Problem:** Validating synthetic 30m LST against actual Landsat LST (on held-out dates) is not independent validation - both use the same sensor, same atmospheric correction, same uncertainties.

**What This Misses:**
- Systematic Landsat errors (emissivity assumptions, atmospheric correction failures)
- LST ≠ reality (it's a satellite estimate with ±2-3°C error)

**Real Validation Requires:**
- Ground truth (in-situ temperature sensors) - mentioned but underfunded
- Only 10 loggers for a city of 1.2M people is tokenistic

**Fix:** Need 30-50 sensors OR acknowledge validation is limited.

### 2. Cloud Contamination Will Destroy Temporal Coverage
**Reality Check for Freetown:**
- Located in wet tropics (3,000+ mm/year rainfall)
- Landsat: 16-day revisit → expect <10 clear-sky scenes/year in wet season
- MODIS: Daily but clouds still block ~60% of days during May-Oct
- **Result:** "Daily 30m LST" dataset will have huge gaps

**Proposed Gap-Filling (3-day moving average):**
- Only works for isolated gaps (1-2 days)
- During multi-week cloudy periods (common), interpolation will be poor
- Uncertainty will explode, making heat-health analysis unreliable

**Fix:**
- Be honest: "Daily LST for clear-sky days + interpolated values with high uncertainty"
- Limit heat-health analysis to dry season only (Nov-Apr)

### 3. ECOSTRESS is Not a Reliable Validation Dataset
**Problem:** ECOSTRESS is mentioned as validation (70m thermal from ISS), but:
- ISS orbit is precessing → Freetown coverage is sporadic and unpredictable
- May get 0-5 scenes per year, if lucky
- Not a systematic validation tool

**Fix:** Remove ECOSTRESS or state as "opportunistic" validation.

### 4. Heat-Health Analysis is Epidemiologically Naive
**Major Issues:**
- **Ecological Fallacy:** Aggregate ward-level LST vs. ward-level hospital admissions ignores individual exposure
- **Confounding:** Poverty, housing quality, access to water, pre-existing health → all correlate with both LST and admissions
- **Hospital Data Availability:** Connaught Hospital may not have digitized data or may refuse access (data privacy)
- **No Statistical Power Calculation:** How many months/wards needed to detect a signal?

**Reality:** This will likely fail or produce uninterpretable results. It's included to "increase impact" but risks wasting 6 months.

**Fix:**
- Make this explicitly "exploratory" and optional (WP5)
- Require ethical approval + hospital MOU BEFORE starting PhD (not during)
- If data unavailable by Month 18, skip this component

### 5. LULC Accuracy Target (85%) May Be Unrealistic
**Problem:** Achieving 85% overall accuracy for Freetown's heterogeneous urban landscape is hard:
- Mixed pixels (vegetation + buildings) common
- Informal settlements have spectral similarity to bare soil
- Cloud shadows create false change signals

**Typical Reality:** 75-80% for urban tropical environments

**Impact:** If LULC accuracy is low, thermal sharpening model inherits these errors.

**Fix:** Lower target to 80% OR focus on broader classes (Urban/Vegetation/Water only).

## SCIENTIFIC STRENGTHS

### 1. Multi-Method Validation is Best Practice
Ground stations + ECOSTRESS + Landsat cross-validation (even if imperfect) is more rigorous than 90% of thermal sharpening studies.

### 2. Tropical Cloud Handling is Novel
Most thermal sharpening studies ignore cloud issues (use dry climate cities). Explicitly addressing this for wet tropics is a contribution.

### 3. 10-Year Time Series is Valuable
Landsat-8/9 era (2013-2024) is the longest consistent thermal record for West Africa. This dataset alone (even without downscaling) is useful.

### 4. Practical Relevance is Clear
Freetown City Council has a climate adaptation plan → there's a clear pathway to uptake.

## FEASIBILITY ASSESSMENT

| Aspect | Score (1-5) | Comment |
|--------|-------------|---------|
| Satellite Data | 5 | Freely available, well-documented |
| Ground Sensors | 2 | **RISK** - $5k budget too low for 50 sensors; 10 sensors insufficient |
| Cloud Cover | 2 | **MAJOR RISK** - may limit analysis to dry season only |
| LULC Accuracy | 3 | Challenging but doable with effort |
| Health Data Access | 2 | **HIGH RISK** - may not materialize |
| Computational | 5 | Google Earth Engine handles pre-processing |
| Timeline (30 months) | 4 | Realistic IF health component is optional |
| **OVERALL FEASIBILITY** | **3.3/5** | **MODERATE** - cloud cover and health data are risks |

## USEFULNESS TO SCIENCE AND SOCIETY

### Scientific Impact: MODERATE-HIGH (3.5/5)
- **Methodological:** Validates thermal downscaling in wet tropics (niche but useful)
- **Regional:** First rigorous UHI study for West Africa (good)
- **Innovation:** Multi-method validation framework is best practice but not groundbreaking
- **Publication Potential:** 2 papers (*Remote Sensing of Environment*, *Urban Climate*)
- **Limitation:** Incremental advance on existing methods, not paradigm shift

### Societal Impact: HIGH (4/5)
- **Direct Application:** Heat vulnerability maps for Freetown City Council
- **Actionability:** Can identify neighborhoods for tree planting, cool roofs
- **Policy Relevance:** Supports Freetown's "Transform Freetown" climate plan
- **Scalability:** Methods transferable to Lagos, Accra, Conakry
- **Limitation:** Impact depends on city capacity to act (often weak)

### Cost-Benefit: GOOD
$80k for actionable heat maps = reasonable, especially if health component succeeds (but risky)

## RECOMMENDATIONS FOR IMPROVEMENT

### MUST DO:
1. **Increase ground sensor budget** to $15k (50 sensors) OR acknowledge validation limitations
2. **Make health analysis conditional** - require hospital MOU by Month 6 or skip it
3. **Realistic cloud coverage assessment** - analyze 2013-2023 Landsat archive for Freetown to quantify expected clear-sky days
4. **Add dry-season focus** - acknowledge wet season gaps upfront

### SHOULD DO:
5. **Lower LULC accuracy target** to 80% or simplify classes
6. **Remove ECOSTRESS** from validation plan (too unreliable)
7. **Pre-engage Freetown City Council** - get Letter of Support BEFORE starting
8. **Add uncertainty quantification** to all LST products (confidence intervals)

### COULD DO:
9. Partner with urban planning NGOs (Build Change, Sierra Leone Urban Research Centre)
10. Crowdsource ground measurements via citizen science (thermometers in schools)

---

# PROJECT 3: PRECIPITATION DOWNSCALING

## CRITICAL WEAKNESSES

### 1. The Stationarity Test Has a Fundamental Flaw
**Problem:** Testing stationarity by splitting 1981-2023 data into 1981-2000 (cool) and 2001-2023 (warm) assumes:
- The climate system was stationary within each period (false - warming is continuous)
- Any detected bias drift is due to non-stationarity (but could be due to CHIRPS algorithm changes)

**Alternative Explanation:**
- CHIRPS algorithm changed in 2015 when Landsat-8 thermal data became available
- Detected "non-stationarity" might be data artifact, not climate signal

**No Control Group:** Need to test on ERA5 precipitation (which has consistent physics-based algorithm) to rule this out.

**Impact:** If test is confounded, the entire WP1-WP2 conclusion is shaky.

**Fix:** Use ERA5 precipitation as control, compare CHIRPS vs ERA5 trends.

### 2. Non-Stationary Covariate May Not Help
**Assumption:** Adding global temperature trend as predictor will allow model to learn "in +1°C world, q850 → X mm/day"

**Reality:**
- We have only ONE realization of +1°C, +1.5°C warming (historical 1981-2023)
- Sample size for learning temperature-dependent relationships is tiny (n≈1 per warming level)
- Model will struggle to differentiate warming signal from natural variability (AMO, ENSO)

**Statistical Power Issue:** This requires long records with multiple temperature states - we barely have that.

**Fix:**
- Acknowledge this limitation explicitly
- Compare to simpler approach: Train on recent decade only (implicit non-stationarity)

### 3. QDM Bias Correction Assumes Historical Biases Persist
**Problem:** Quantile Delta Mapping corrects CMIP6 future projections using historical biases (1981-2014), but:
- If model bias is state-dependent (e.g., worse at high temperatures), QDM will fail in +4°C world
- No way to validate this since we don't have observations of +4°C future

**This is a Known Limitation of All Bias Correction:** Acknowledged in ISIMIP protocols but often ignored.

**Fix:**
- State this clearly as a "stationarity of bias" assumption
- Test on pseudo-future: Correct 2001-2014 using 1981-2000, see if it works

### 4. Computational Requirements Are Underestimated
**Reality Check:**
- 10 CMIP6 models × 3 SSPs × 250 years × 365 days = ~2.7 million model-days
- Each day requires predicting ~400,000 grid cells (West Africa at 5km)
- Even with efficient code, this is 100+ million predictions

**Hardware Needed:**
- Listed: "Laptop + cloud $20k"
- **Actually Needed:** University HPC cluster (multi-node) OR $40k+ AWS

**Storage:**
- 500GB estimated
- **Reality:** Intermediate files (bias-corrected predictors, daily outputs) → 2-5 TB

**Timeline Impact:** Data processing alone could take 6-12 months (not included in timeline).

**Fix:**
- Secure HPC access BEFORE starting
- Extend timeline by 6 months for computational pipeline development

### 5. Validation Against CHIRPS is Circular
**Problem:** Training on CHIRPS 1981-2023, then validating on CHIRPS 2016-2023 is not independent - same dataset, same biases.

**What's Needed:**
- Validation against independent dataset (TAMSAT mentioned but not used systematically)
- Gauge data (if available)

**Fix:** Add TAMSAT and ERA5 precipitation as independent validation.

## SCIENTIFIC STRENGTHS

### 1. Stationarity Testing is Rare and Important
Even if the test has flaws (see above), **explicitly checking** this assumption is far ahead of most studies that ignore it.

### 2. QDM is State-of-the-Art
Using Quantile Delta Mapping (not simple scaling) is best practice. Many studies still use outdated methods.

### 3. Multi-Model Ensemble is Robust
8-10 CMIP6 models with uncertainty quantification is rigorous.

### 4. Spatial Validation (Gradients, MCS) is Novel
Most downscaling studies validate only with grid-cell metrics. Validating spatial processes (coast-Sahel gradient, MCS clustering) is innovative.

### 5. Regional Demand is High
West Africa desperately needs high-resolution precipitation projections. Agricultural models, hydrological models, disaster planning all require this.

## FEASIBILITY ASSESSMENT

| Aspect | Score (1-5) | Comment |
|--------|-------------|---------|
| Data Availability | 5 | CHIRPS, ERA5, CMIP6 all free |
| Computational Resources | 2 | **MAJOR RISK** - HPC access required, budget underestimated |
| Technical Skills | 3 | Requires ML, climate modeling, big data processing - steep learning curve |
| Methodological Soundness | 3 | Stationarity test has flaws; bias correction assumptions strong |
| Timeline (42 months) | 3 | Tight if computational pipeline takes 6-12 months to debug |
| Stakeholder Engagement | 4 | WASCAL network exists, demand is high |
| **OVERALL FEASIBILITY** | **3.3/5** | **MODERATE** - computational resources are the bottleneck |

## USEFULNESS TO SCIENCE AND SOCIETY

### Scientific Impact: HIGH (4/5)
- **Methodological:** Stationarity testing protocol is transferable globally (major contribution)
- **Technical:** QDM application to WAM is novel
- **Dataset:** First high-quality 5km precipitation projections for West Africa
- **Publication Potential:** 3-4 strong papers (*GMD*, *J. Climate*, *Climatic Change*)
- **Limitation:** Doesn't solve fundamental bias correction dilemma

### Societal Impact: VERY HIGH (5/5)
- **Direct Application:** Input to agricultural planning, water resource models, flood risk
- **Economic Impact:** Crop failures cost billions - better projections save money
- **Policy Relevance:** National adaptation plans require this data
- **Scalability:** Framework applicable to other data-sparse regions
- **Capacity Building:** WASCAL network trained in modern methods

### Cost-Benefit: EXCELLENT (if computational budget fixed)
$100k for a dataset used by dozens of impact studies across 15 countries = high leverage

## RECOMMENDATIONS FOR IMPROVEMENT

### MUST DO:
1. **Secure HPC access** and revise computational budget to $40k
2. **Add ERA5 precipitation** as control for stationarity test
3. **Independent validation** using TAMSAT + gauges (not just CHIRPS)
4. **Test QDM bias stationarity** using pseudo-future approach

### SHOULD DO:
5. **Extend timeline** to 48 months (add 6 months for computational pipeline)
6. **Reduce model count** from 10 to 6-7 (more manageable)
7. **Simplify domain** - focus on key agricultural zones (Sahel) rather than full West Africa
8. **Pre-compute** bias-corrected CMIP6 predictors (6 months upfront work)

### COULD DO:
9. Collaborate with ISIMIP (Inter-Sectoral Impact Model Intercomparison Project) for standardized bias correction
10. Publish intermediate dataset (bias-corrected CMIP6) separately for community use

---

# PROJECT 4: EXTREME VALUE THEORY

## CRITICAL WEAKNESSES

### 1. CORDEX-Africa Validation Gate May Fail Most Models
**Reality:** CORDEX-Africa RCMs are known to struggle with extreme precipitation:
- Convection is parameterized (not resolved) → underestimates extreme intensities
- Many RCMs have wet/dry biases >50%
- Validation studies (Nikulin et al., 2012; Gibba et al., 2019) show only 3-4 models pass credibility tests

**Proposed Threshold:** |bias| < 30% for 20-year return level

**Expected Result:** May retain only 2-4 models (not 6-10 as assumed)

**Impact:** Small ensemble → large uncertainty, potentially inconclusive results

**Fix:**
- Lower threshold to 40% (accept "least bad" models)
- OR supplement with CMIP6 GCMs (coarser but more models)

### 2. Fully Non-Stationary GEV May Be Overfitting
**Problem:** Modeling all three GEV parameters (μ, σ, ξ) as functions of GMST requires estimating 6 parameters from ~150 data points (annual maxima, 1950-2100).

**Statistical Reality:**
- Shape parameter (ξ) is notoriously unstable - requires 500+ samples for robust estimation
- With only 150 samples, allowing ξ(t) to vary will produce huge uncertainty
- Model may fit noise, not signal

**Evidence:** Most EVT literature keeps ξ constant for exactly this reason.

**Fix:**
- Test ξ(t) but don't expect it to be significant
- Primary model: μ(t) + σ(t), with ξ constant (more defensible)

### 3. Return Period Shifts Are Misinterpreted by Engineers
**Communication Problem:** Saying "50-year event becomes 25-year event" sounds dramatic but confuses engineers:
- Infrastructure design uses return LEVELS (mm/day), not return periods
- Mixing the two creates confusion

**Better Communication:** "The 50-year design value increases from X to Y mm/day"

**Fix:** Focus outputs on updated design tables (already planned), de-emphasize frequency change.

### 4. Workshops May Not Reach Decision-Makers
**Reality Check:**
- National Met Services are under-resourced; staff turnover is high
- Training 20 people doesn't guarantee institutional uptake
- Public Works ministries (who design infrastructure) may not attend "climate science" workshops

**Past Experience:** Many well-intentioned capacity building efforts fail due to institutional barriers.

**Fix:**
- Target engineers directly (not just met services)
- Partner with professional associations (e.g., West African Federation of Engineering Organizations)
- Publish in engineering journals, not just climate journals

### 5. Web Tool Maintenance is Unfunded
**Problem:** Deliverable includes interactive web tool, but:
- Who hosts it after PhD ends? University servers are unreliable
- Who maintains it when R packages update and break the code?
- Who answers user questions?

**Typical Outcome:** Tool works for 1-2 years, then disappears (broken links).

**Fix:**
- Partner with ACMAD or WASCAL (institutions with IT staff) for hosting
- Use simple, stable tech stack (static site, not Shiny server)
- Plan for Zenodo archival of tool snapshot (DOI-citable)

## SCIENTIFIC STRENGTHS

### 1. Fully Non-Stationary GEV is Frontier (if it works)
Most studies model only μ(t). Attempting μ(t) + σ(t) + ξ(t) is ambitious and could be high-impact if successful.

### 2. Engineering Translation is Excellent
Design tables, warming-level scaling, policy briefs → this is how science should communicate with practitioners. Rare in academic work.

### 3. CORDEX Validation for Extremes is Needed
No comprehensive study exists for coastal West Africa. This fills a gap.

### 4. Uncertainty Decomposition is Rigorous
Separating GEV uncertainty vs. model spread vs. scenario uncertainty is best practice.

## FEASIBILITY ASSESSMENT

| Aspect | Score (1-5) | Comment |
|--------|-------------|---------|
| Data Availability | 5 | CORDEX, CHIRPS, ERA5 all free |
| Technical Skills | 4 | EVT is specialized but well-documented (R packages exist) |
| Computational | 5 | Low - EVT fitting is fast |
| Model Quality | 2 | **RISK** - CORDEX models may fail validation, leaving few usable |
| Stakeholder Access | 3 | Met services yes; engineers harder to reach |
| Timeline (30 months) | 4 | Realistic if validation gate passed quickly |
| Web Tool Sustainability | 2 | **RISK** - unfunded maintenance |
| **OVERALL FEASIBILITY** | **3.6/5** | **MODERATE** - model quality is the main risk |

## USEFULNESS TO SCIENCE AND SOCIETY

### Scientific Impact: HIGH (4/5)
- **Methodological:** Multi-parameter non-stationary GEV advances the field
- **Regional:** First comprehensive extreme rainfall projections for coastal West Africa
- **Validation:** CORDEX-Africa credibility assessment is needed by community
- **Publication Potential:** 3 strong papers (*J. Climate*, *Climate Dynamics*, *Climatic Change*)
- **Limitation:** Builds on existing methods rather than inventing new ones

### Societal Impact: VERY HIGH (5/5)
- **Direct Application:** Updated design codes prevent infrastructure failure
- **Lives Saved:** Reduces flood deaths in Lagos, Accra, Freetown (millions at risk)
- **Economic Impact:** Prevents billions in damage from under-designed drainage
- **Policy Relevance:** National building codes need this now (outdated standards)
- **Scalability:** Framework applicable globally

### Cost-Benefit: OUTSTANDING
$70k for design values used in billions of dollars of infrastructure = exceptional ROI. This is the highest societal impact project.

## RECOMMENDATIONS FOR IMPROVEMENT

### MUST DO:
1. **Plan for model failure** - what if only 2 CORDEX models pass validation? (Use CMIP6 as backup)
2. **Keep shape parameter constant** (ξ ≠ f(t)) unless strong evidence supports time-varying
3. **Secure hosting partner** for web tool (ACMAD, WASCAL)
4. **Target engineers directly** in dissemination plan

### SHOULD DO:
5. **Add CMIP6 GCMs** to ensemble (more models, coarser resolution)
6. **Simplify web tool** to static site (easier to maintain)
7. **Pilot design table** with one engineering firm before scaling workshops
8. **Publish engineering paper** in *Journal of Hydraulic Engineering* or *Water Resources Management*

### COULD DO:
9. Collaborate with World Bank (Urban Resilience Program) for dissemination
10. Include compound flooding (rainfall + storm surge) for coastal cities

---

# PROJECT 5: CLIMATE EMULATORS

## CRITICAL WEAKNESSES

### 1. XAI Validation is Philosophically Problematic
**The Core Issue:** Using SHAP to verify the emulator learned "correct physics" assumes we know what correct physics looks like. But:
- Logarithmic CO₂ forcing is a **simplified formula**, not fundamental truth
- Real Earth System Models have complex feedbacks (clouds, vegetation, ocean) that deviate from simple scaling
- If emulator learns something different than log(CO₂), it might be because ESMs themselves are non-linear, not because emulator is wrong

**The Circular Logic:**
- Train emulator on ESM outputs
- Use SHAP to check if emulator learned "physics"
- But we're comparing to simplified physics, not ESM actual physics
- If disagreement, can't tell if emulator failed or if simplified physics is wrong

**Fix Needed:**
- Reframe XAI as "interpreting what ESMs encode" not "validating correctness"
- Acknowledge that SHAP shows emulator behavior, not universal truth

### 2. Training Data is Tiny (4 ESMs, 5 SSPs = 20 Scenarios)
**Statistical Reality:**
- ClimateBench has ~20 unique emission scenarios
- Each scenario has 250 years → 5,000 data points total (seems like a lot)
- But for learning complex multi-dimensional relationships (CO₂ + CH₄ + SO₂ + interactions), this is small

**Risk:**
- Emulator will interpolate well (within SSP1-SSP5 range)
- Emulator will extrapolate poorly (beyond observed CO₂ levels, or weird combinations like "high CO₂ + high SO₂" that don't exist in training data)

**The 10,000 Scenarios Claim:**
- Proposal says "explore 10,000 scenarios"
- But how many will be out-of-sample extrapolations that are unreliable?
- No way to validate, since we don't have ESM runs for those scenarios

**Fix:**
- Clearly delineate "safe interpolation zone" vs. extrapolation
- Only claim validity within training envelope

### 3. Multi-Variable Emulation (T+P) is Highly Ambitious
**Why Precipitation is Hard:**
- Non-Gaussian (gamma distribution, many zeros)
- Spatial intermittency (rains here, dry 10 km away)
- Model disagreement is huge (CMIP6 models disagree on sign of change in many regions)

**Proposed Constraint (Clausius-Clapeyron):**
- CC scaling is ~7%/°C for atmospheric moisture capacity
- But precipitation ≠ moisture (requires convergence, uplift, instability)
- Regional precip changes range from -20% to +40%/°C in CMIP6 (breaks CC constraint)

**Reality:** Multi-variable emulation with physical constraints will either:
- Fail to converge (constraints too tight)
- OR ignore constraints (defeats the purpose)

**Success Probability:** 30-40%

**Fix:**
- Make this explicitly high-risk / optional (WP4)
- Have fallback: Independent T and P emulators (less novel but safer)

### 4. Spatial Emulation via PCA Assumes Linear Modes
**Problem:** PCA finds linear combinations of grid cells, but:
- Climate teleconnections are non-linear (ENSO, NAO)
- Regime shifts (e.g., AMOC collapse) won't be captured by linear PCs
- Autoencoder (non-linear) is proposed as alternative, but:
  - Requires 100x more training data
  - Is even less interpretable (defeats XAI goal)

**Impact:** Spatial emulator will work well for "business as usual" warming patterns, poorly for surprises.

**Fix:** Acknowledge this explicitly - emulator is for scenario exploration, not for predicting unknown unknowns.

### 5. Comparison to ESMs is Unfair
**Claim:** "Emulator runs 10,000 scenarios in 1 hour vs. 10 million model-years of ESM time"

**What's Wrong:**
- ESM provides 100+ variables (clouds, ocean currents, soil moisture, sea ice, chemistry)
- Emulator provides 2-10 variables (T, P, maybe a few others)
- Comparing single-variable emulation to full ESM is apples-to-oranges

**Better Comparison:** Compare to existing fast emulators (FaIR, MAGICC, MESMER)

**Fix:** Clarify that this is a statistical emulator for specific variables, not an ESM replacement.

### 6. Web Tool Will Be Misused
**Problem:** An interactive "Climate Futures Explorer" where users design custom scenarios sounds great, but:
- Policymakers will extrapolate wildly (e.g., "What if we remove all CO₂ in 2050?")
- Tool will give an answer (because it's trained to predict), even if it's nonsense
- No warning system for out-of-domain queries

**Past Experience:** Climate Shift Index tool was criticized for overconfidence in untrained regimes.

**Fix:**
- Add "confidence bounds" that widen for extrapolation
- Require users to acknowledge limitations before running scenarios
- Include "domain checker" that warns when input is outside training range

## SCIENTIFIC STRENGTHS

### 1. XAI for Climate is Novel and Important
Even if philosophically imperfect (see above), applying SHAP to climate emulators is new. The question "what did the AI learn?" is underappreciated.

### 2. Spatial Emulation is a Frontier
Most emulators are global-mean only. PCA-based spatial emulation is state-of-the-art.

### 3. Open Science Commitment is Excellent
GitHub code, PyPI package, Zenodo data, web tool → this is exemplary open science.

### 4. Targets Real Policy Need
Rapid scenario exploration is genuinely useful for IPCC-style assessments and national planning.

## FEASIBILITY ASSESSMENT

| Aspect | Score (1-5) | Comment |
|--------|-------------|---------|
| Data Availability | 5 | ClimateBench + CMIP6 freely available |
| Computational Resources | 4 | GPU needed ($5k AWS) but manageable |
| Technical Skills | 2 | **HARD** - Requires ML, climate modeling, software engineering, XAI expertise |
| Training Data Sufficiency | 3 | 20 scenarios is small for complex relationships |
| Multi-Variable Success | 2 | **HIGH RISK** - precipitation emulation may fail |
| Spatial Emulation | 4 | PCA approach is proven; Autoencoder is risky |
| Timeline (40 months) | 3 | Ambitious if multi-variable attempted |
| **OVERALL FEASIBILITY** | **3.3/5** | **MODERATE** - technical difficulty is high |

## USEFULNESS TO SCIENCE AND SOCIETY

### Scientific Impact: VERY HIGH (4.5/5)
- **Methodological:** XAI for climate emulators is frontier research
- **Technical:** Spatial + multi-variable emulation advances the field
- **Open Science:** Code + data + tool benefits entire community
- **Publication Potential:** 1-2 high-impact papers (*Nature Climate Change*, *PNAS*) + 2-3 methods papers (*GMD*, *JAMES*)
- **Innovation:** Combines multiple cutting-edge techniques
- **Limitation:** Builds on existing emulator paradigm (not fundamentally new)

### Societal Impact: MODERATE-HIGH (3.5/5)
- **Direct Application:** Rapid scenario exploration for policy
- **IPCC Relevance:** Could speed up AR7 scenario assessment
- **Education:** Web tool useful for teaching
- **Transparency:** XAI builds public trust in climate science
- **Limitation:** Policymakers already have FaIR, MAGICC - incremental improvement, not revolution

### Cost-Benefit: GOOD
$90k for cutting-edge research + community tool = solid, but societal impact is diffuse (not as direct as Projects 1, 2, 4)

## RECOMMENDATIONS FOR IMPROVEMENT

### MUST DO:
1. **Reframe XAI validation** as "interpretation" not "verification of truth"
2. **Add domain checker** to web tool (warn when extrapolating)
3. **Make multi-variable optional** - have clear fallback (T only, or T+P independent)
4. **Expand training data** - use all available CMIP6 models (30+), not just 4

### SHOULD DO:
5. **Compare to existing emulators** (FaIR, MAGICC, MESMER) explicitly
6. **Simplify scope** - remove Autoencoder (stick with PCA)
7. **Lower publication target** to 3 papers (not 5)
8. **Pre-test XAI on simple model** - validate SHAP on energy balance model where you KNOW the physics

### COULD DO:
9. Collaborate with IPCC WG1 authors for scenario co-design
10. Add uncertainty quantification via Bayesian Neural Networks

---

# CROSS-PROJECT SYNTHESIS

## Common Weaknesses Across All 5 Projects

### 1. **Validation Optimism**
All projects assume validation data will be available, accessible, and high-quality. Reality: field work fails, hospital data is denied, CORDEX models are biased, ECOSTRESS has no coverage.

**Fix:** Add "Plan B" validation for every project.

### 2. **Publication Pressure**
Targeting 3-5 publications per PhD creates pressure to rush, p-hack, or salami-slice results. Most successful PhDs have 2-3 solid papers.

**Fix:** Reduce to 2 papers (one methods, one application) + 1-2 optional.

### 3. **Stakeholder Engagement Naiveté**
All projects assume government agencies, hospitals, engineering firms will enthusiastically collaborate. Reality: they're busy, under-resourced, skeptical of academics.

**Fix:** Secure MOUs BEFORE starting, not during PhD.

### 4. **Timeline Optimism**
30-42 months assumes everything goes smoothly. Reality: data delivery delays, code bugs, field work rescheduling, supervisor feedback delays.

**Fix:** Add 6-month buffer to all timelines.

### 5. **Computational Underestimation**
Projects 3 and 5 especially underestimate HPC needs, storage, and data wrangling time.

**Fix:** Pilot computational pipeline in first 3 months; revise budget/timeline accordingly.

## Comparative Ranking

### By Feasibility (Least Risky to Most Risky):
1. **Project 4 (EVT)** - 3.6/5 - Data available, methods established, main risk is model quality
2. **Project 2 (UHI)** - 3.3/5 - Cloud cover is a risk, but manageable
3. **Project 3 (Downscaling)** - 3.3/5 - Computational resources are bottleneck
4. **Project 5 (Emulator)** - 3.3/5 - Multi-variable component is high risk
5. **Project 1 (Landslide)** - 3.5/5 - Field work in Sierra Leone is logistically challenging

### By Scientific Impact (Contribution to Field):
1. **Project 5 (Emulator)** - 4.5/5 - XAI for climate is frontier
2. **Project 3 (Downscaling)** - 4/5 - Stationarity testing is novel
3. **Project 4 (EVT)** - 4/5 - Multi-parameter GEV is frontier
4. **Project 1 (Landslide)** - 4/5 - Bias correction method is novel
5. **Project 2 (UHI)** - 3.5/5 - Incremental advance

### By Societal Impact (Lives/Money Saved):
1. **Project 4 (EVT)** - 5/5 - Infrastructure design, millions at risk
2. **Project 1 (Landslide)** - 5/5 - Disaster prevention, 1000s of lives
3. **Project 3 (Downscaling)** - 5/5 - Agriculture, water, billions in economic impact
4. **Project 2 (UHI)** - 4/5 - Urban planning, health
5. **Project 5 (Emulator)** - 3.5/5 - Policy tool, diffuse impact

### By Cost-Effectiveness (ROI):
1. **Project 4 (EVT)** - $70k for infrastructure design guidance = OUTSTANDING
2. **Project 1 (Landslide)** - $120k for disaster prevention = EXCELLENT
3. **Project 3 (Downscaling)** - $100k for regional dataset = EXCELLENT
4. **Project 2 (UHI)** - $80k for city heat maps = GOOD
5. **Project 5 (Emulator)** - $90k for research tool = GOOD

## OVERALL RECOMMENDATION FOR PhD CANDIDATE

**If You Want:**
- **Fast PhD completion (30 months)** → **Project 4** (lowest risk, clear path)
- **High scientific novelty** → **Project 5** (frontier methods, high-impact journals)
- **Maximum societal impact** → **Project 4 or 1** (saves lives directly)
- **Regional development focus** → **Project 3** (West Africa capacity building)
- **Urban applications** → **Project 2** (Freetown heat management)

**If You Must Choose ONE, Prioritize:**
**Project 4 (Extreme Value Theory)** - Best balance of feasibility, scientific contribution, societal impact, and cost-effectiveness.

---

# RECOMMENDATIONS FOR ALL PROJECTS

## Mandatory Improvements

### 1. Add Realistic Risk Assessments
Every WP needs:
- **What could go wrong?**
- **How likely is failure? (probability)**
- **What's Plan B?**
- **What's the "minimum viable thesis" if Plan B also fails?**

### 2. Pre-Registration
Register analysis plans (variables, methods, validation metrics) BEFORE collecting data to avoid p-hacking and HARKing (Hypothesizing After Results are Known).

### 3. Computational Pilot
Months 1-3: Test full pipeline on small dataset (1 model, 1 scenario, 1 year). Measure:
- Processing time
- Storage needed
- Code bugs
- → Use this to revise timeline and budget

### 4. Stakeholder Pre-Engagement
Before starting PhD:
- Get Letters of Support from government partners
- Get ethical approval for health/social data
- Get MOUs with universities for field collaboration
- Test data access (download test files, visit hospital, contact Met Service)

### 5. Reduce Publication Pressure
Change from "3-5 publications" to:
- **Required:** 1-2 peer-reviewed papers
- **Expected:** 1 additional paper under review
- **Bonus:** Additional papers if time allows

This reduces pressure and improves quality.

### 6. Add Uncertainty Everywhere
Every number needs:
- Point estimate
- Confidence interval (or prediction interval)
- Statement of assumptions
- Sensitivity analysis

### 7. Build in Flexibility
Timelines should have:
- Core objectives (must complete for PhD)
- Secondary objectives (would be nice)
- Stretch goals (if everything goes perfectly)

PhDs are awarded for core completion, not stretch goals.

---

# CONCLUSION

All five projects are scientifically sound and PhD-worthy, but they share common weaknesses:

**Over-ambition, validation optimism, computational underestimation, stakeholder naiveté, and publication pressure.**

**The Good News:** These are fixable through better planning, realistic risk assessment, and scope reduction.

**Recommendation:** Each candidate should choose ONE project, trim secondary objectives to "future work," secure collaborations upfront, and focus on delivering 2 high-quality papers + one operational product.

**Top Choice for Immediate Impact + PhD Completion:** **Project 4 (Extreme Value Theory)** - Most feasible, highest societal ROI, clear scientific contribution.

**Top Choice for Scientific Career:** **Project 5 (Climate Emulators)** - Frontier methods, high-impact publication potential, demonstrates ML expertise.

**Either would be an excellent PhD.**

---

**END OF CRITICAL REVIEW**
