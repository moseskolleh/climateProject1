# SUMMARY OF CRITICAL UPDATES TO PhD PROPOSALS
**Date:** December 7, 2025
**Action:** Comprehensive critical review and revision of all 5 projects

---

## OVERVIEW

All five PhD proposals have been critically reviewed and updated to address major weaknesses identified in the peer review process. This document summarizes the key changes made to each project.

---

## PROJECT 1: LANDSLIDE SUSCEPTIBILITY MAPPING

### Critical Issues Addressed:
1. **Sampling Bias Circularity** - Added simulated validation before real-world application
2. **Field Validation Power** - Increased from 30-50 to 80-100 sites across 2 field seasons
3. **Timeline Optimism** - Extended from 36 to 42 months
4. **Budget Realism** - Increased from $120k to $135k
5. **Physics Validation Limitations** - Downgraded to "exploratory" not "validation"

### Key Revisions:
- Added **decision gates** and **Plan B** options throughout
- Included power analysis for field validation
- Added weather contingency (2 dry seasons instead of 1)
- Reduced publication target from 3-5 to 2-3 papers
- Made dynamic hazard system optional (can move to post-doc)
- Added Cameroon as backup location if Sierra Leone access blocked

### New Budget Items:
- Field work: $18k (up from $10k)
- 2 field seasons × 3 weeks each
- 2 local assistants
- Soil lab analysis for 20 samples

---

## PROJECT 2: URBAN HEAT ISLAND ANALYSIS

### Critical Issues Addressed:
1. **Ground Sensor Inadequacy** - Increased from 10 to 40-50 sensors
2. **Cloud Contamination Realism** - Acknowledged gaps, limited to dry season analysis
3. **Health Data Risk** - Made strictly optional with Month 6 decision gate
4. **ECOSTRESS Over-Reliance** - Removed from primary validation plan
5. **Validation Circularity** - Enhanced ground-truth validation

### Key Revisions:
- **Health Analysis (WP5):** Now explicitly optional - requires hospital MOU by Month 6 or skip entirely
- **Ground Sensors:** 50 loggers ($15k) for adequate statistical power
- **Cloud Coverage:** Honest assessment - expect major gaps in wet season
- **ECOSTRESS:** Reframed as "opportunistic" not reliable validation
- **Budget:** Increased from $80k to $95k
- **Publications:** Reduced from 3-5 to 2-3 papers

### Decision Gate Added:
- **Month 6:** Hospital MOU secured? If NO → skip health analysis, reallocate time to enhanced physical validation

---

## PROJECT 3: PRECIPITATION DOWNSCALING

### Critical Issues Addressed:
1. **Stationarity Test Confounding** - Added ERA5 and TAMSAT controls to rule out data artifacts
2. **Computational Underestimation** - Revised HPC budget from $20k to $40k, storage from 1TB to 3-5TB
3. **CHIRPS Validation Circularity** - Added independent validation with TAMSAT and ERA5 precipitation
4. **Timeline Inadequacy** - Extended from 42 to 48 months
5. **Model Count** - Reduced from 10 to 6-8 CMIP6 models (more manageable)

### Key Revisions:
- **WP1 Stationarity Test:** Now includes 3 control experiments (ERA5, TAMSAT, gauges)
- **Computational Pilot:** Months 1-3 test on 1 model to measure actual resource needs
- **HPC Requirement:** MUST secure access BEFORE PhD start (critical gate)
- **Plan B:** If HPC unavailable, reduce to 6 models + 2 SSPs
- **Budget:** Increased from $100k to $140k
- **Duration:** 48 months (added 6 months for computational pipeline development)

### New Decision Tree:
- IF all datasets show bias drift → Non-stationary modeling
- IF only CHIRPS shows drift → Use ERA5/TAMSAT as target instead
- IF no drift → Use stationary model (simpler)

---

## PROJECT 4: EXTREME VALUE THEORY

### Critical Issues Addressed:
1. **CORDEX Model Failure Risk** - Added contingency for model validation failures
2. **GEV Overfitting** - Primary model now μ(t)+σ(t) with ξ constant; fully non-stationary is exploratory only
3. **Engineering Communication** - Focus on design tables, not frequency changes
4. **Web Tool Sustainability** - Partner with ACMAD/WASCAL for hosting
5. **Workshop Targeting** - Directly engage engineers, not just met services

### Key Revisions:
- **Expected RCM Retention:** Reduced from 6-10 to 4-8 models (realistic)
- **Plan B Options:**
  - B1: Relax threshold to 40%
  - B2: Supplement with CMIP6 GCMs
  - B3: Single best RCM + GEV uncertainty
  - Minimum viable: 1 RCM + 3 GCMs
- **GEV Hierarchy:** Primary model is μ(t) + σ(t), ξ constant
  - Fully non-stationary (ξ(t)) tested but not relied upon (likely unstable)
- **Publications:** Reduced from 3-4 to 2-3 papers
- **Budget:** Increased from $70k to $75k (web tool hosting)

### Statistical Rigor Added:
- Bootstrap validation for fully non-stationary model
- Decision rule: Only use ξ(t) if AIC improvement >10 and SE <50% of estimate

---

## PROJECT 5: CLIMATE EMULATORS

### Critical Issues Addressed:
1. **XAI Philosophical Problem** - Reframed from "validation" to "interpretation"
2. **Training Data Limitation** - Expanded from 4 to 20-30 CMIP6 models
3. **Multi-Variable Risk** - Made explicitly optional with Month 22 decision gate
4. **Web Tool Misuse** - Added domain checker and confidence bounds
5. **Extrapolation Safety** - Clear delineation of safe interpolation zone

### Key Revisions:
- **XAI Reframing:** WP2 now "interprets what ESMs encode" NOT "validates physics"
  - Acknowledges SHAP shows emulator behavior, not universal truth
- **Training Data:** 20-30 ESMs × 5 SSPs = 100 scenarios (5x increase from 20)
- **Multi-Variable Emulation:** Success probability stated as 30-40%
  - Decision gate at Month 22: Skip if time insufficient or precipitation intractable
  - **Plan B:** Temperature-only emulator is still valuable (PhD-worthy)
- **Web Tool Safety:**
  - Domain checker warns when extrapolating
  - Confidence bounds widen outside training range
  - User must acknowledge limitations
- **Budget:** Increased from $90k to $95k
- **Publications:** Reduced from 4-5 to 2-3 papers

### Minimum Viable Thesis:
- Spatial temperature emulator with XAI interpretation
- Comparison to existing emulators (FaIR, MAGICC, MESMER)
- Open-source package + web tool
- 2 publications (1 methods, 1 application)

---

## CROSS-PROJECT IMPROVEMENTS

### Common Updates to All Projects:

1. **Risk Assessments Added:**
   - Every Work Package now has risk level (LOW/MODERATE/HIGH)
   - **Plan B** options for high-risk components
   - **Minimum Viable Thesis** defined (what's required for graduation if setbacks occur)

2. **Decision Gates Implemented:**
   - Clear month-based checkpoints where methodology is reassessed
   - "Go/No-Go" decisions for optional/high-risk components
   - Prevents sunk-cost fallacy (continuing failed approaches)

3. **Publication Pressure Reduced:**
   - Changed from "3-5 publications" to "2-3 publications"
   - **Required:** 1-2 peer-reviewed papers
   - **Optional:** Additional papers if time allows
   - **Strategy:** 2 papers published/in-review for graduation; 3rd can be post-defense

4. **Computational Realism:**
   - Projects 3 and 5: Added computational pilots (Months 1-3)
   - Revised budgets for HPC and cloud computing
   - Storage requirements corrected (3-5TB not 1TB for Project 3)
   - HPC access must be secured BEFORE PhD start

5. **Stakeholder Engagement Pre-Requirements:**
   - MOUs with government agencies required BEFORE PhD start (not during)
   - Letters of Support from collaborating institutions
   - Ethical approval for health/social data upfront
   - Test data access in advance

6. **Timeline Buffers:**
   - 6-month buffers built into all timelines
   - Weather contingencies for field work
   - Review/revision time allocated
   - Realistic acknowledgment of delays (data delivery, code bugs, supervisor feedback)

7. **Validation Enhancements:**
   - Added independent datasets (not circular validation)
   - Power analyses for statistical adequacy
   - Multi-method validation (stats + physics + field + cross-dataset)
   - Uncertainty quantification throughout

8. **Budget Revisions:**
   - Project 1: $120k → $135k
   - Project 2: $80k → $95k
   - Project 3: $100k → $140k
   - Project 4: $70k → $75k
   - Project 5: $90k → $95k
   - **Total Increase:** ~$70k across all projects (more realistic)

9. **Duration Adjustments:**
   - Project 1: 36 → 42 months
   - Project 2: 30 months (unchanged, but health component optional)
   - Project 3: 42 → 48 months
   - Project 4: 30 months (unchanged)
   - Project 5: 40 months (unchanged)

---

## METHODOLOGICAL IMPROVEMENTS BY PROJECT

### Project 1:
- ✅ Simulated validation of sampling bias correction (before real application)
- ✅ Power analysis for field validation (80-100 sites for ±15% CI)
- ✅ Two field seasons (weather risk mitigation)
- ✅ Backup location (Cameroon if Sierra Leone inaccessible)

### Project 2:
- ✅ 50 ground sensors (up from 10) for robust validation
- ✅ Health analysis strictly optional (Month 6 gate)
- ✅ ECOSTRESS removed from primary validation (too unreliable)
- ✅ Cloud coverage honestly assessed (dry season focus)

### Project 3:
- ✅ Stationarity test with 3 control datasets (ERA5, TAMSAT, gauges)
- ✅ Computational pilot (Months 1-3) before full implementation
- ✅ HPC access requirement enforced
- ✅ Independent validation (not just CHIRPS)

### Project 4:
- ✅ CORDEX model failure contingencies (3 Plan B options)
- ✅ GEV overfitting addressed (primary model has ξ constant)
- ✅ Bootstrap validation for parameter stability
- ✅ Engineering-focused dissemination strategy

### Project 5:
- ✅ XAI properly framed as interpretation (not validation of truth)
- ✅ Training data expanded 5x (100 scenarios instead of 20)
- ✅ Multi-variable made optional with clear success criteria
- ✅ Web tool misuse prevention (domain checker, warnings)

---

## OVERALL IMPACT

### Before Critical Review:
- ❌ Over-ambitious scopes (trying to do too much)
- ❌ Optimistic timelines (assumed everything goes smoothly)
- ❌ Validation wishful thinking (assumed data will be available)
- ❌ Computational underestimation (laptop + cloud won't suffice for Project 3)
- ❌ Publication pressure (3-5 papers expected, may delay graduation)
- ❌ No contingency plans (what if method fails?)

### After Critical Review:
- ✅ Focused scopes with clear core objectives
- ✅ Realistic timelines with 6-month buffers
- ✅ Validation with Plan B options
- ✅ Adequate computational resources budgeted
- ✅ Reduced publication pressure (2-3 papers, quality over quantity)
- ✅ Multiple contingency plans and decision gates

---

## FEASIBILITY SCORES (REVISED)

| Project | Before | After | Improvement |
|---------|--------|-------|-------------|
| Project 1 (Landslide) | 3.0/5 | 3.8/5 | ↑ Field validation power, timeline buffer |
| Project 2 (UHI) | 2.8/5 | 3.7/5 | ↑ Ground sensors, health optional |
| Project 3 (Downscaling) | 2.5/5 | 3.6/5 | ↑ HPC budget, stationarity controls |
| Project 4 (EVT) | 3.6/5 | 4.0/5 | ↑ Model failure contingencies |
| Project 5 (Emulator) | 3.0/5 | 3.8/5 | ↑ Training data, multi-variable optional |

**All projects now >3.5/5 feasibility (MODERATE to HIGH)**

---

## RECOMMENDATION FOR CANDIDATE

### If Prioritizing One Project (Revised Rankings):

**1. Project 4 (Extreme Value Theory)** - 4.0/5 Feasibility
- ✅ Highest feasibility after revisions
- ✅ Clearest societal impact (infrastructure design, millions at risk)
- ✅ Best cost-benefit ratio ($75k for life-saving design values)
- ✅ Established methods (EVT) with frontier innovation (multi-parameter non-stationary)
- ✅ Strong publication potential (2-3 solid papers in J. Climate, Climate Dynamics)
- ✅ 30 months (shortest timeline)

**2. Project 1 (Landslide)** - 3.8/5 Feasibility
- ✅ High societal impact (disaster prevention for Sierra Leone)
- ✅ Novel method (sampling bias correction) with fallback options
- ✅ Strong stakeholder demand (post-Regent disaster)
- ⚠️ Field work logistics challenging but now better planned (2 seasons)
- ✅ 42 months with buffer

**3. Project 5 (Climate Emulators)** - 3.8/5 Feasibility
- ✅ Highest scientific novelty (XAI for climate, frontier research)
- ✅ High-impact publication potential (Nature Climate Change, PNAS)
- ✅ Training data expanded (100 scenarios)
- ⚠️ Multi-variable optional (PhD-worthy even without it)
- ✅ 40 months

**4. Project 3 (Downscaling)** - 3.6/5 Feasibility
- ✅ Very high societal impact (West Africa agricultural planning)
- ✅ Important methodological contribution (stationarity testing)
- ⚠️ Computationally intensive (HPC required - critical gate)
- ⚠️ 48 months (longest timeline)
- ✅ High regional demand (WASCAL network)

**5. Project 2 (UHI)** - 3.7/5 Feasibility
- ✅ Good feasibility after revisions
- ✅ High local impact (Freetown heat management)
- ✅ Solid methodology (thermal downscaling validated)
- ⚠️ Health component high-risk (but now optional)
- ✅ 30 months

---

## NEXT STEPS

### Before Starting Any PhD:

1. **Secure Computational Access** (Projects 3, 5):
   - Confirm HPC cluster availability
   - Test data download and processing pipeline
   - Measure actual resource needs

2. **Establish Collaborations:**
   - Get MOUs from government agencies
   - Secure Letters of Support from universities
   - Test data access (download sample files, visit hospital, contact Met Service)

3. **Obtain Ethical Approvals:**
   - Project 2: Hospital health data (if pursuing WP5)
   - Project 1: Community engagement for field work

4. **Pilot Key Methods:**
   - Project 1: Test sampling bias correction on simulated data (Months 1-3)
   - Project 3: Computational pilot (Months 1-3)
   - Project 5: XAI test on simple energy balance model

5. **Plan Publications:**
   - Identify target journals
   - Draft outlines for 2 core papers
   - Set realistic submission timeline (don't wait until Month 30)

---

## CONCLUSION

All five projects are now **scientifically rigorous, methodologically sound, and PhD-worthy**. The critical revisions address:

✅ **Feasibility risks** with contingency plans
✅ **Validation weaknesses** with independent datasets
✅ **Computational realism** with adequate budgets
✅ **Timeline optimism** with 6-month buffers
✅ **Publication pressure** with reduced targets (2-3 papers)
✅ **Methodological gaps** with Plan B options

**All projects now have >3.5/5 feasibility and clear pathways to completion.**

**Top Recommendation:** **Project 4 (Extreme Value Theory)** remains the best balance of scientific contribution, societal impact, feasibility, and timeline (30 months).

**Runner-Up:** **Project 1 (Landslide)** or **Project 5 (Emulator)** depending on whether candidate prioritizes regional impact (Project 1) or frontier AI research (Project 5).

---

**END OF UPDATES SUMMARY**
