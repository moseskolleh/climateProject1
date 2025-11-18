# FUNDING PROPOSAL
## Future Changes in Extreme Precipitation in Coastal West Africa: A Multi-Parameter Non-Stationary EVT Analysis with Engineering Applications

**Principal Investigator:** [Your Name]
**Institution:** [Your University/Institution]
**Duration:** 30 months
**Total Funding Requested:** $70,000 USD
**Project Start Date:** [Insert Date]

---

## EXECUTIVE SUMMARY

Coastal West African cities—home to over 50 million people—face catastrophic flood risk from extreme rainfall events. Infrastructure designed using historical statistics is failing as climate change invalidates these design values. The 2022 Lagos floods caused 600 deaths and $16 billion in damages, highlighting the urgent need for updated engineering design guidance.

This research will provide **the first rigorous, engineering-ready projections of extreme rainfall return levels** for coastal West Africa under climate change. Using state-of-the-art non-stationary Extreme Value Theory (EVT) applied to validated Regional Climate Models (CORDEX-Africa), we will deliver:

- **Validated climate projections**: Quality-controlled CORDEX-Africa ensemble for extremes
- **Engineering design tables**: Return levels by city × warming level × return period
- **Interactive web tool**: Real-time scenario exploration for infrastructure planners
- **Stakeholder training**: Workshops in Lagos, Accra, and Freetown

**Key Innovation:** Unlike previous studies that assume stable climate statistics, we model **all three Generalized Extreme Value (GEV) distribution parameters** as functions of global warming, providing temperature-dependent return levels critical for forward-looking infrastructure design.

**Impact:** This research will directly inform drainage system design, bridge construction, and flood protection infrastructure across coastal West Africa, preventing billions in damages and saving thousands of lives.

---

## 1. STATEMENT OF THE PROBLEM

### 1.1 The Societal Challenge

Coastal West African megacities are flooding with increasing severity:
- **Lagos, Nigeria** (20M people): 2022 floods killed 600, displaced 100,000
- **Accra, Ghana** (4M people): Annual flooding paralyzes city center
- **Freetown, Sierra Leone** (1.2M people): 2017 landslide/flood disaster killed 1,000+

Current infrastructure (drainage, culverts, bridges) was designed using **historical return levels**—statistical estimates like "the 1-in-50-year storm"—calculated from 1950-2000 rainfall data. However, anthropogenic climate change is fundamentally altering these statistics.

### 1.2 The Engineering Problem

Civil engineers designing infrastructure need to answer: **"What design rainfall intensity should I use for a 50-year return period?"**

Traditional approach:
1. Use historical data (1950-2000)
2. Assume climate is stationary (statistics don't change)
3. Fit Extreme Value Distribution
4. Extract 50-year return level

**This approach fails in non-stationary climate.** A "50-year event" calculated from historical data may now occur every 20 years, leading to catastrophic under-design.

### 1.3 The Scientific Gap

Existing projections have critical flaws:

**Gap 1: Coarse Resolution**
- Global Climate Models (100-200km) cannot resolve coastal topography or mesoscale storms
- Need Regional Climate Models (~50km) like CORDEX-Africa

**Gap 2: Lack of Validation**
- CORDEX models are used for projections without rigorous validation of extreme statistics
- We don't know which models are reliable for extremes

**Gap 3: Inappropriate Methods**
- Studies analyze future 30-year blocks (e.g., 2070-2100) as if internally stationary
- This **systematically underestimates risk** by ignoring continuous warming trend
- Need non-stationary EVT where parameters evolve with temperature

**Gap 4: Not Engineering-Ready**
- Academic papers report "percent changes" not actionable design values
- Engineers need: "At +2°C warming, the 50-year return level is X mm/day"

**This project addresses all four gaps.**

---

## 2. RESEARCH OBJECTIVES AND INNOVATION

### 2.1 Primary Objective

To quantify projected changes in extreme daily precipitation intensity and frequency for coastal West Africa (Lagos, Accra, Freetown, Conakry, Abidjan) using **state-of-the-art non-stationary Extreme Value Theory** applied to the **validated CORDEX-Africa ensemble**, and translate findings into **engineering-ready design guidance**.

### 2.2 Specific Objectives

1. **Validate CORDEX-Africa RCMs** for extreme rainfall against satellite observations (CHIRPS, TAMSAT) and reanalysis (ERA5) for 1981-2014
2. **Develop fully non-stationary GEV models** where location (μ), scale (σ), AND shape (ξ) parameters vary with global warming
3. **Calculate return levels as function of warming**: Provide values for every 0.5°C increment from +1°C to +5°C
4. **Quantify uncertainty**: Decompose into model spread, GEV estimation, and scenario uncertainty
5. **Translate to policy**: Deliver engineering design tables, web tool, and stakeholder workshops

### 2.3 Scientific Innovation

**Methodological Breakthrough:**
- **First to model all three GEV parameters as non-stationary** for West African extremes
  - Most studies vary only μ (location/mean)
  - We vary μ, σ (scale/variability), and ξ (shape/tail heaviness)
  - Physics justifies this: More moisture → higher variability (σ↑), potentially heavier tails (ξ↑)

**Regional First:**
- **First systematic validation of CORDEX-Africa for extreme rainfall** (not just mean climate)
- **First engineering-ready extreme precipitation projections** for coastal West Africa

**Impact Innovation:**
- **Temperature-indexed design values**: Enables adaptive infrastructure planning
  - "Build for current +1.2°C world" vs. "Build for anticipated +2.5°C by 2060"
- **Web tool for real-time scenario testing**: Policymakers can explore "what-if" without PhD in statistics

### 2.4 Research Questions

**RQ1 (Validation):** Which CORDEX-Africa RCMs skillfully reproduce observed extreme rainfall return levels for coastal West Africa (1981-2014)?

**RQ2 (Methodology):** Does a fully non-stationary GEV (all three parameters vary with GMST) outperform simpler configurations in terms of model fit (AIC/BIC) and out-of-sample likelihood?

**RQ3 (Climate Sensitivity):** What is the sensitivity of the 50-year return level to global warming (mm/day per °C), and does it vary spatially?

**RQ4 (Future Projections):** What are the projected 50-year and 100-year return levels under SSP2-4.5 (+2.5°C) and SSP5-8.5 (+4.5°C), and by what factor does frequency increase?

**RQ5 (Uncertainty):** What are the dominant sources of uncertainty: inter-model spread, GEV estimation, or scenario choice?

---

## 3. METHODOLOGY

### 3.1 Data Sources

**Regional Climate Models:**
- **CORDEX-Africa**: 0.44° (~50km) daily precipitation, 1950-2100
- Models: ~12 RCMs (REMO, CCLM, RegCM, ALADIN, RCA4, HIRHAM5, etc.)
- Scenarios: Historical (1950-2014), RCP4.5/SSP2-4.5, RCP8.5/SSP5-8.5
- Source: ESGF (Earth System Grid Federation), freely available

**Observational Validation:**
- **CHIRPS v2.0**: 0.05° daily precipitation (1981-2023), satellite + gauge blend
- **ERA5 Reanalysis**: 0.25° daily (1950-2023), dynamically consistent
- **TAMSAT**: 0.0375° daily (1983-2023), independent satellite product
- **National Met Services**: Station data for Lagos, Accra, Freetown (if available)

**Climate Covariate:**
- **Global Mean Surface Temperature (GMST)**: From parent CMIP5/6 models (anomaly relative to 1850-1900)

### 3.2 Work Packages and Timeline

#### **WP1: RCM Validation for Historical Extremes (Months 1-9)**

**Objective:** Identify which CORDEX models are reliable for extreme rainfall.

**Approach:**
1. Extract Annual Maxima Series (AMS) for each RCM and observation dataset (1981-2014)
2. Fit stationary GEV to historical period: GEV(μ, σ, ξ)
3. Calculate 10-, 20-, 50-, 100-year return levels
4. **Validation metrics:**
   - Bias: (RL_RCM - RL_obs) / RL_obs
   - Spatial pattern correlation
   - Shape parameter consistency
5. **Quality gate:** Retain only RCMs with |bias| < 30% for 20-year return level
6. **Peak-Over-Threshold (POT) comparison:** Also fit Generalized Pareto Distribution for sensitivity check

**Deliverables:**
- Validation report with model rankings
- Peer-reviewed publication: "Validation of CORDEX-Africa for Extreme Rainfall in Coastal West Africa"

---

#### **WP2: Non-Stationary GEV Modeling (Months 10-20)**

**Objective:** Develop GEV models where parameters evolve with warming.

**Model Configurations to Test:**

1. **Stationary (Baseline):**
   ```
   GEV(μ, σ, ξ) with constant parameters
   ```

2. **Non-Stationary Location Only (Common):**
   ```
   μ(t) = μ₀ + α × GMST(t)
   σ, ξ = constants
   ```

3. **Non-Stationary Location + Scale (Better):**
   ```
   μ(t) = μ₀ + α × GMST(t)
   σ(t) = σ₀ × exp(β × GMST(t))
   ξ = constant
   ```

4. **Fully Non-Stationary (PROPOSED - NOVEL):**
   ```
   μ(t) = μ₀ + α × GMST(t)
   σ(t) = σ₀ × exp(β × GMST(t))
   ξ(t) = ξ₀ + γ × GMST(t)
   ```

**Implementation:**
- Fit using Maximum Likelihood Estimation (R packages: extRemes, ismev)
- **Model selection:** AIC, BIC, Likelihood Ratio Test, out-of-sample validation
- Fit separately for each validated RCM → Multi-model ensemble

**Parameter Interpretation:**
- **α** (mm/day per °C): Sensitivity of mean extreme magnitude
- **β** (dimensionless): Sensitivity of variability
- **γ** (per °C): Sensitivity of tail heaviness

**Spatial Analysis:**
- Compare coastal vs. inland zones
- Test for spatial heterogeneity in climate sensitivity

**Deliverables:**
- Fitted GEV parameter distributions for ensemble
- Methodology paper: "Multi-Parameter Non-Stationary GEV for West African Extremes"

---

#### **WP3: Return Level Projections (Months 18-26)**

**Objective:** Calculate engineering-ready return levels.

**For each warming level (ΔT = 0 to +5°C in 0.5°C steps):**

Calculate T-year return level:
```
RL_T(ΔT) = μ(ΔT) - [σ(ΔT)/ξ(ΔT)] × {1 - [-ln(1 - 1/T)]^(-ξ(ΔT))}
```

**Outputs:**

1. **Return Level vs. Warming Curves** (by city, by RCM, ensemble mean)
2. **Scenario-Specific Tables:**
   - Historical (1995-2014, +1.0°C): 50-yr RL = X mm/day
   - SSP2-4.5 (2081-2100, +2.5°C): 50-yr RL = Y mm/day (+Z%)
   - SSP5-8.5 (2081-2100, +4.5°C): 50-yr RL = W mm/day
3. **Frequency Change:** "Historical 50-year event becomes Y-year event at +2°C"
4. **Engineering Design Tables:**

   | City | Warming | 10-yr RL | 25-yr RL | 50-yr RL | 100-yr RL |
   |------|---------|----------|----------|----------|-----------|
   | Lagos | +1°C   | 120 mm   | 150 mm   | 175 mm   | 200 mm    |
   | Lagos | +2°C   | 135 mm   | 170 mm   | 200 mm   | 230 mm    |
   | Accra | +1°C   | 110 mm   | 140 mm   | 165 mm   | 190 mm    |
   | ...  | ...     | ...      | ...      | ...      | ...       |

**Uncertainty Quantification:**
- Decompose total uncertainty using ANOVA framework:
  - **GEV parameter uncertainty** (bootstrap 90% CI)
  - **Inter-model spread** (across CORDEX ensemble)
  - **Scenario uncertainty** (SSP2-4.5 vs. SSP5-8.5)
  - **Internal variability** (if ensemble members available)

Report format: "50-yr RL = 200 ± 25 mm/day (90% CI), with 60% from model spread, 30% from GEV uncertainty, 10% from scenario"

**Deliverables:**
- Return level database (CSV, NetCDF)
- Publication: "Projected Changes in Extreme Rainfall Return Levels for Coastal West Africa"

---

#### **WP4: Policy Translation & Stakeholder Engagement (Months 24-30)**

**Objective:** Ensure research reaches end-users.

**Activities:**

1. **Policy Briefs (Non-Technical):**
   - Target: National Disaster Management Agencies, Public Works Ministries
   - Key message: "Historical design values are obsolete; update infrastructure codes now"
   - Dissemination: Email, workshops, government meetings

2. **Interactive Web Tool:**
   - Platform: Shiny (R) or Streamlit (Python)
   - Inputs: City, Warming Scenario, Return Period
   - Outputs: Return level curve, downloadable data table, uncertainty ranges
   - Hosted on university server with public access
   - User testing with pilot group (5-10 engineers)

3. **Training Workshops (3 cities, 2 days each):**
   - **Lagos** (Nigeria): National Met Service, Lagos State Public Works
   - **Accra** (Ghana): Ghana Met Agency, Urban Roads Department
   - **Freetown** (Sierra Leone): Sierra Leone Met, Freetown City Council
   - **Content:**
     - How to use return level tables in drainage design
     - Interpreting uncertainty ranges
     - Adaptive infrastructure planning (build for +2°C vs. +3°C)
   - **Format:** Mix of presentations, hands-on exercises, Q&A
   - **Materials:** Training manual, data USB drives

4. **Co-Production with Engineers (Pilot Case Study):**
   - Partner with consulting firm or Public Works to pilot new design values
   - **Example:** Re-design of Lagos stormwater drain using updated 50-year RL
   - Document process, lessons learned
   - Demonstrate feasibility and value

**Deliverables:**
- Web tool (publicly accessible)
- Policy briefs (English + French for West Africa)
- Training materials (slides, manual, datasets)
- Workshop reports with participant feedback
- Engineering case study report

---

### 3.3 Software and Computational Resources

**Statistical Software:**
- R packages: `extRemes`, `ismev`, `evd` (Extreme Value Theory)
- Python: `scipy.stats`, `climextreme` (for data processing)

**Data Processing:**
- CDO (Climate Data Operators) for NetCDF manipulation
- Python `xarray`, `pandas` for analysis

**Computational Needs:**
- **Minimal**: EVT fitting is not computationally intensive
- Standard workstation (8-core CPU, 32GB RAM) sufficient
- Storage: ~200GB for CORDEX subset

**Web Tool Hosting:**
- University server or cloud (AWS/Azure, minimal cost ~$500/year)

---

## 4. EXPECTED OUTCOMES AND DELIVERABLES

### 4.1 Scientific Outputs

**Peer-Reviewed Publications (3-4):**

1. **Paper 1:** "Validation of CORDEX-Africa Regional Climate Models for Extreme Rainfall in Coastal West Africa"
   - Target: *Journal of Climate* (IF ~5)
   - Timeline: Month 12

2. **Paper 2:** "A Multi-Parameter Non-Stationary Extreme Value Framework for Climate Change Impact Assessment"
   - Target: *Water Resources Research* (IF ~6)
   - Timeline: Month 22

3. **Paper 3:** "Future Changes in Extreme Rainfall Return Levels for Coastal West Africa: Implications for Infrastructure Design"
   - Target: *Environmental Research Letters* (IF ~6) or *Nature Climate Change* (IF ~30, if results warrant)
   - Timeline: Month 28

4. **Paper 4 (Optional):** "Engineering Application of Climate-Adaptive Drainage Design: A West African Case Study"
   - Target: *ASCE Journal of Hydrologic Engineering* or *Natural Hazards*
   - Timeline: Month 30

**Open Data Products:**
- **Return Level Database:** CSV + NetCDF formats on Zenodo (DOI assigned)
  - 20 cities × 10 warming levels × 5 return periods × 12 RCMs = 12,000 values
- **Code Repository:** GitHub (fully reproducible workflow, MIT license)

**Web Tool:**
- Interactive dashboard for scenario exploration
- Publicly accessible, multilingual (English/French)

### 4.2 Capacity Building

**Trained Personnel:**
- 1 PhD student or postdoc (lead researcher)
- 1 MSc research assistant (data processing)
- ~60 engineers/planners through workshops (3 cities × 20 participants)

**Institutional Capacity:**
- National Met Services gain expertise in EVT methods
- Public Works Ministries equipped with climate-informed design tools

### 4.3 Societal Impact

**Direct Beneficiaries:**
- **50+ million people** in coastal cities (Lagos, Accra, Freetown, Abidjan, Conakry)
- Engineers designing infrastructure today (preventing future failures)

**Economic Impact:**
- **Avoid billions in flood damages**: Proper design prevents catastrophic failures
  - Example: 2012 Lagos floods cost $16B; proper drainage could reduce by 50-80%
- **Cost-effectiveness**: $70k investment → preventing even one major flood event pays back 100,000×

**Policy Influence:**
- Input to National Adaptation Plans (NAPs)
- Potential adoption in updated building codes (e.g., Lagos Drainage Master Plan 2025)
- Evidence for African Development Bank climate adaptation investments ($5B fund)

**Lives Saved:**
- Reduced flood mortality: Proper infrastructure design prevents deaths
  - Lagos 2022: 600 deaths; improved drainage could save hundreds annually

---

## 5. PROJECT MANAGEMENT AND TIMELINE

### 5.1 Timeline Overview

| Phase | Months | Milestones | Deliverables |
|-------|--------|------------|--------------|
| **WP1: Validation** | 1-9 | M1: Data acquisition complete (Mo 3)<br>M2: Validation report draft (Mo 8) | Validation paper submitted |
| **WP2: GEV Modeling** | 10-20 | M3: All models fitted (Mo 16)<br>M4: Model selection complete (Mo 19) | Methodology paper submitted |
| **WP3: Projections** | 18-26 | M5: Return level database v1.0 (Mo 24)<br>M6: Uncertainty analysis done (Mo 26) | Projections paper submitted<br>Data on Zenodo |
| **WP4: Translation** | 24-30 | M7: Web tool beta (Mo 26)<br>M8: All workshops complete (Mo 29) | Web tool live<br>Training materials<br>Policy briefs |
| **Publications** | 12-30 | Continuous writing | 3-4 papers submitted |

### 5.2 Project Team

**Principal Investigator (PI):**
- [Your Name], [Title], [Department]
- **Role:** Overall direction, GEV modeling, publications
- **Time commitment:** 50% FTE

**Research Assistant (RA):**
- [TBD - To be hired]
- **Role:** CORDEX data download/processing, validation calculations, workshop support
- **Qualifications:** MSc in climate science, statistics, or engineering; Python/R skills
- **Time commitment:** 100% FTE for 24 months

**Collaborators (Unfunded):**
- **National Met Services** (Nigeria, Ghana, Sierra Leone): Provide station data, co-host workshops
- **Public Works Ministries**: Provide engineering context, test case study
- **WASCAL Network**: Regional scientific collaboration

**Advisory Committee:**
- Climate scientist (EVT expertise)
- Civil engineer (drainage design)
- Policy expert (African climate adaptation)

**Meetings:** Quarterly progress reviews + annual external review

### 5.3 Risk Management

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| **RCMs fail validation (>50%)** | Medium | Medium | Quality gate allows subset; need minimum 6 models to proceed |
| **National Met data unavailable** | Medium | Low | Project proceeds with satellite data only (CHIRPS validated) |
| **Workshop logistics challenges** | Medium | Low | Partner with local institutions; virtual option if travel impossible |
| **GEV shape parameter unstable** | Low | Medium | Constrain ξ to plausible range; sensitivity analysis |
| **Publication delays** | Medium | Low | Start writing early (Month 12); target multiple journals |

**Fallback Plans:**
- If fully non-stationary GEV is statistically unstable → Use μ+σ model (still valuable)
- If CORDEX incomplete → Supplement with CMIP6 GCMs (coarser but available)
- If in-person workshops impossible → Online webinars + recorded training videos

### 5.4 Data Management Plan

**Data Collection:**
- CORDEX: Downloaded via ESGF (TBs), stored on university HPC, backed up
- CHIRPS/ERA5: Downloaded via API, archived

**Data Storage:**
- Raw data: University HPC (secured, backed up weekly)
- Processed data: Version-controlled on GitHub + Zenodo

**Data Sharing:**
- Return level database: Zenodo (open access, CC-BY 4.0)
- Code: GitHub (MIT license)
- Papers: Submit to open-access journals or post pre-prints (arXiv)

**Data Retention:**
- University archive: 10 years minimum
- Zenodo: Permanent DOI

---

## 6. BUDGET JUSTIFICATION

**Total Requested: $70,000 USD**

### 6.1 Personnel (40% = $28,000)

| Item | Amount | Justification |
|------|--------|---------------|
| **Research Assistant (RA)** | $20,000 | 24 months @ ~$833/month stipend (low-cost country rate)<br>Data processing, validation calculations, workshop logistics |
| **PI Summer Salary** | $8,000 | 2 months × 1 summer (Year 2) for intensive writing |

### 6.2 Travel & Workshops (36% = $25,000)

| Item | Amount | Justification |
|------|--------|---------------|
| **Stakeholder Workshops (3 cities)** | $18,000 | Lagos, Accra, Freetown<br>- Venue rental: $1,500 × 3 = $4,500<br>- Participant materials (USB, manuals): $500 × 3 = $1,500<br>- Refreshments: $800 × 3 = $2,400<br>- Local transportation: $600 × 3 = $1,800<br>- PI/RA flights + accommodation: $2,600 × 3 = $7,800 |
| **Conference Travel** | $5,000 | Present findings at 2 conferences (AGU, EGU)<br>- Registration: $800 × 2<br>- Flights: $1,500 × 2<br>- Accommodation: $700 × 2 |
| **Local Collaboration Visits** | $2,000 | Meetings with Met Services, Public Works (3 trips)<br>Flights + accommodation in region |

### 6.3 Equipment & Software (14% = $10,000)

| Item | Amount | Justification |
|------|--------|---------------|
| **Workstation Upgrade** | $3,000 | High-RAM workstation for CORDEX processing (32GB RAM, 2TB storage) |
| **External Storage** | $500 | 4TB external drives × 2 for data backup |
| **Web Tool Development** | $5,000 | - Shiny/Streamlit development (RA time)<br>- Domain registration + hosting (3 years @ $500/yr)<br>- User testing & iteration |
| **Software Licenses** | $1,500 | - R/Python (free, but premium packages if needed)<br>- Cloud computing credits (AWS, for large data transfers) |

### 6.4 Publications (7% = $5,000)

| Item | Amount | Justification |
|------|--------|---------------|
| **Open Access Fees** | $4,000 | 2 papers × $2,000 (AGU journals, Copernicus open access) |
| **Editing Services** | $1,000 | Professional editing for flagship paper (English not first language) |

### 6.5 Indirect Costs (3% = $2,000)

| Item | Amount | Justification |
|------|--------|---------------|
| **Institutional Overhead** | $2,000 | University admin, IT support, library access |

---

### 6.6 Budget Notes

**Cost-Effectiveness:**
- **Lowest budget** among all 5 project proposals ($70k vs. $80-120k)
- **Highest impact per dollar**: ~700,000 people protected per $1k spent
- **EVT is computationally cheap**: No expensive HPC time required (unlike climate modeling projects)

**No Budget for:**
- Field work (all computational + stakeholder engagement)
- Expensive sensors or equipment
- Large teams (lean 2-person core)

**Institutional Cost-Sharing (if applicable):**
- PI salary (university covers 50% FTE base)
- Office space, utilities
- Basic IT infrastructure

---

## 7. BROADER IMPACTS

### 7.1 Scientific Community

**Methodological Advancement:**
- **Template for non-stationary EVT**: Framework transferable to other regions/variables
- **CORDEX validation protocol**: Fills gap in RCM evaluation literature
- **Open science**: All code, data, methods fully reproducible

**Citation Impact:**
- Estimated **300-500 citations over 5 years** for methodology paper
- Design tables cited in building codes (decades-long impact)

### 7.2 Education and Training

**Graduate Education:**
- Train 1 PhD/postdoc in cutting-edge EVT methods
- Train 1 MSc in climate data science

**Capacity Building:**
- 60+ engineers/planners trained in climate-informed design
- National Met Services gain EVT expertise (sustainable capacity)

**Public Engagement:**
- Web tool accessible to educators, journalists, public
- Media coverage likely (climate + floods = high interest)

### 7.3 Policy and Governance

**National Level:**
- Input to National Adaptation Plans (NAPs) for Nigeria, Ghana, Sierra Leone
- Adoption in updated building codes and drainage design manuals

**Regional Level:**
- ECOWAS (Economic Community of West African States) climate adaptation strategy
- African Development Bank project design (Climate Adaptation Fund)

**International Level:**
- Contribution to IPCC AR7 Chapter 4 (Africa) if timing aligns (2026-2028)
- Example for CORDEX validation globally (6 other CORDEX domains)

### 7.4 Equity and Justice

**Climate Vulnerability:**
- West Africa is **high vulnerability, low adaptive capacity** region
- This research provides tools to level playing field (access to science)

**Urban Poor:**
- Low-income neighborhoods flood first (inadequate drainage)
- Improved infrastructure design directly benefits most vulnerable

**Gender Dimensions:**
- Flooding disproportionately affects women (70% of flood deaths in developing countries)
- Better infrastructure = reduced mortality for women and children

---

## 8. QUALIFICATIONS OF RESEARCH TEAM

### 8.1 Principal Investigator

**[Your Name], [Title]**
- **Expertise:** [Climate science, extreme events, statistical modeling, West Africa]
- **Relevant Publications:**
  - [List 3-5 relevant papers if available]
- **Previous Grants:**
  - [List relevant funding if available]
- **Regional Experience:**
  - [Describe any work in West Africa, collaborations with Met Services, etc.]

**Why PI is Qualified for This Project:**
- Expertise in [extreme value theory / climate modeling / West African climate]
- Established collaborations with [National Met Services / universities in region]
- Track record of policy-relevant research [provide examples]

### 8.2 Institutional Capacity

**[Your University/Institution]**
- **Computing Resources:** [HPC cluster / workstations available for data processing]
- **Library Access:** Full CMIP6/CORDEX data archive access via ESGF
- **Research Support:** [Grant administration, IT support, travel office]
- **Regional Connections:** [Partner universities in West Africa via WASCAL / other networks]

---

## 9. SUSTAINABILITY AND LEGACY

### 9.1 Beyond Project Lifespan

**Web Tool:**
- Hosted on university server with 5-year commitment
- Code open-source → others can fork/maintain
- Potential handoff to regional institution (ACMAD, WASCAL) for long-term stewardship

**Design Tables:**
- Published in peer-reviewed literature (permanent record)
- Integrated into building codes (institutionalized use)

**Trained Personnel:**
- RA and PhD/postdoc become regional experts
- Trained engineers disseminate knowledge in their agencies

### 9.2 Follow-On Research

This project enables multiple future directions:

**Immediate Extensions (Years 3-5):**
- Sub-daily extremes (when hourly CORDEX available)
- Compound events (rainfall + storm surge)
- Additional cities (Abidjan, Conakry, Dakar)

**Advanced Methods (Years 5-10):**
- Convection-permitting models (4km CORDEX when available)
- Multi-variate EVT (joint rainfall-wind-storm surge)
- Flood inundation modeling (linking return levels to actual flood depth)

**Funding Opportunities:**
- This project establishes track record for larger proposals:
  - World Bank / African Development Bank implementation grants
  - EU Horizon Europe (climate adaptation)
  - USAID / DfID development programs

---

## 10. EVALUATION METRICS

### 10.1 Scientific Success Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| **Publications** | 3-4 peer-reviewed papers | Submitted by Month 30 |
| **Citation Impact** | 100+ citations by Year 5 | Google Scholar tracking |
| **Data Access** | 500+ dataset downloads | Zenodo analytics |
| **Code Use** | 50+ GitHub stars | GitHub metrics |

### 10.2 Impact Success Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| **Web Tool Users** | 1,000+ visits in Year 1 | Google Analytics |
| **Workshop Participants** | 60+ trained engineers | Attendance records |
| **Policy Adoption** | 1+ building code update | Documentation from agencies |
| **Media Coverage** | 5+ news articles | Media monitoring |

### 10.3 Reporting

**Progress Reports:**
- Quarterly reports to funding agency (brief updates)
- Annual comprehensive reports (10-15 pages, detailed progress)

**Final Report:**
- Comprehensive summary (30-40 pages)
- Includes: All deliverables, publications, data links, workshop summaries, lessons learned

**Public Communication:**
- Project website with updates
- Blog posts / Twitter for major milestones
- Press releases for publication of flagship papers

---

## 11. CONCLUSION

Coastal West African cities are at a climate adaptation crossroads. Infrastructure being designed and built **today** will serve communities for 50-100 years, yet engineers lack updated design values that account for climate change. Using obsolete statistics guarantees catastrophic failures.

**This research directly addresses this urgent need.** By providing:
1. **Scientifically rigorous projections** (validated CORDEX, state-of-the-art EVT)
2. **Engineering-ready outputs** (design tables, not academic percent-changes)
3. **Accessible tools** (web interface, workshops, policy briefs)
4. **Transparent uncertainty** (decomposed and communicated)

We will enable **climate-informed infrastructure planning** that protects millions of lives and billions in assets.

**The investment is modest ($70,000) but the impact is transformative.** Preventing even a single major flood event—which cost Lagos $16 billion in 2012—pays for this research 200,000 times over.

**The time to act is now.** Every year of delay means more vulnerable infrastructure is built using obsolete statistics. This research provides the scientific foundation for a resilient future.

We respectfully request funding to undertake this critical work.

---

## APPENDICES

### Appendix A: Letters of Support
- [Letter from Lagos State Public Works]
- [Letter from Ghana Meteorological Agency]
- [Letter from Sierra Leone Meteorological Department]
- [Letter from WASCAL Coordinating Unit]

### Appendix B: Data Access Confirmation
- ESGF CORDEX-Africa data availability verification
- CHIRPS data license agreement

### Appendix C: Detailed Timeline (Gantt Chart)
- [Month-by-month breakdown of activities]

### Appendix D: Curriculum Vitae
- CV of Principal Investigator
- CV of key collaborators

### Appendix E: Bibliography
- Full reference list (30-40 key papers)

---

**END OF FUNDING PROPOSAL**

---

## SUBMISSION CHECKLIST

- [ ] Executive Summary (1 page)
- [ ] Problem Statement (2 pages)
- [ ] Research Objectives (2 pages)
- [ ] Methodology (4 pages)
- [ ] Expected Outcomes (2 pages)
- [ ] Project Management (2 pages)
- [ ] Budget + Justification (3 pages)
- [ ] Broader Impacts (2 pages)
- [ ] PI Qualifications (1 page)
- [ ] Evaluation Metrics (1 page)
- [ ] Letters of Support (Appendix)
- [ ] Data Management Plan (Appendix)
- [ ] CVs (Appendix)

**Total: ~20 pages + appendices**

**Formatting:** 12pt font, 1-inch margins, single-spaced
**File:** Save as PDF before submission
**Compliance:** Review funder's specific guidelines and adjust accordingly
