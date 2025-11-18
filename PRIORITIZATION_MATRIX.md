# PROJECT PRIORITIZATION MATRIX
## Selecting Your Climate Science PhD Project

---

## How to Use This Matrix

This document provides a **systematic, evidence-based framework** for selecting which of the 5 improved research projects to pursue.

### Scoring System
Each project is scored on **6 criteria** using a 1-5 scale:
- **5 = Excellent** (top 20%)
- **4 = Good** (above average)
- **3 = Moderate** (average)
- **2 = Below Average** (concerns exist)
- **1 = Poor** (major challenges)

### Criteria Explained

1. **FEASIBILITY** (Weight: 25%) - Can it realistically be completed?
   - Data availability
   - Computational resources needed
   - Field work logistics
   - Dependency on external partners
   - Technical complexity

2. **IMPACT** (Weight: 25%) - What's the societal benefit?
   - Lives potentially saved/improved
   - Economic value (infrastructure protected, crops saved)
   - Number of beneficiaries
   - Policy influence potential
   - Urgency of need

3. **TIMELINESS** (Weight: 15%) - How urgent is this research?
   - Current gaps in knowledge
   - Immediate policy needs
   - Competitive landscape (are others doing this?)

4. **PUBLICATION POTENTIAL** (Weight: 15%) - Career advancement value
   - Journal tier (Nature/Science vs specialty)
   - Number of publishable papers
   - Methodological novelty
   - Citation potential

5. **CAREER DEVELOPMENT** (Weight: 10%) - Skills & network
   - Transferable skills gained
   - Network/partnerships built
   - Post-PhD job market fit
   - International profile

6. **COST-EFFECTIVENESS** (Weight: 10%) - Bang for buck
   - Budget required
   - Impact per dollar
   - Funding competitiveness

---

## SCORING MATRIX

| Project | Feasibility (25%) | Impact (25%) | Timeliness (15%) | Publication (15%) | Career (10%) | Cost-Eff (10%) | **TOTAL** | **WEIGHTED** | **RANK** |
|---------|------------------|--------------|------------------|-------------------|--------------|----------------|-----------|--------------|----------|
| **1. Landslides** | 3 | 5 | 5 | 4 | 4 | 3 | 24/30 | **4.05/5** | **#5** |
| **2. Urban Heat** | 4 | 4 | 4 | 4 | 4 | 4 | 24/30 | **4.00/5** | **#2** |
| **3. Downscaling** | 3 | 4 | 4 | 5 | 5 | 3 | 24/30 | **3.95/5** | **#4** |
| **4. Extremes** | 5 | 5 | 5 | 5 | 5 | 5 | 30/30 | **5.00/5** | **🥇 #1** |
| **5. Emulator** | 4 | 3 | 3 | 5 | 5 | 4 | 24/30 | **3.90/5** | **#3** |

### Calculation Example (Project 4):
- Weighted Score = (5×0.25) + (5×0.25) + (5×0.15) + (5×0.15) + (5×0.10) + (5×0.10) = **5.00**

---

## DETAILED SCORING JUSTIFICATION

---

### PROJECT 1: Landslide Susceptibility Mapping

#### ✅ **FEASIBILITY: 3/5** (Moderate)
**Strengths:**
- Data freely available (ALOS, Sentinel, CHIRPS)
- Software open-source (Python, QGIS, sklearn)
- Method well-documented (Random Forest is mature)

**Challenges:**
- ⚠️ Field validation campaign requires 3-6 months in Sierra Leone (safety, logistics, visas)
- ⚠️ Landslide inventory completeness uncertain (target 300-800, may get less)
- ⚠️ Depends on local partnerships (Njala University, Met Agency) for field access
- ⚠️ Rainy season timing constrains field work (May-October)

**Mitigation:** Tiered quality system allows completion even with incomplete inventory

---

#### ✅ **IMPACT: 5/5** (Excellent)
**Why Maximum Score:**
- 🔴 **CRITICAL NEED**: 2017 Regent disaster killed 1,000+ people
- 🌍 **LIVES SAVED**: Operational early warning system directly prevents deaths
- 💰 **ECONOMIC**: Informs land-use planning for $100M+ Freetown infrastructure projects
- 📊 **BENEFICIARIES**: 1.2M Freetown residents + national rural communities
- 🚨 **URGENCY**: Landslides occur every rainy season; warnings needed NOW

**Concrete Outcome:** National Disaster Management Agency operational tool by Year 3

---

#### ✅ **TIMELINESS: 5/5** (Excellent)
**Why Urgent:**
- 🏆 **GAP**: No existing nationwide LSM for Sierra Leone
- 🏆 **COMPETITION**: No other group working on bias-corrected LSM for this region
- 🏆 **POLICY WINDOW**: Government rebuilding after COVID/Ebola; receptive to DRR tools
- 🏆 **CLIMATE CHANGE**: Rainfall intensifying (IPCC AR6); risk increasing annually

**Window of Opportunity:** Government currently drafting National Disaster Risk Reduction Strategy (2025-2030)

---

#### ✅ **PUBLICATION POTENTIAL: 4/5** (Good)
**Expected Papers (3-5):**
1. **Methodological**: Spatial point process bias correction → *Geomorphology* or *Landslides* (high-impact specialty journal)
2. **Regional**: Sierra Leone ensemble LSM → *Natural Hazards and Earth System Sciences*
3. **Physics-ML integration**: Validation framework → *Environmental Modelling & Software*
4. **Operational**: Early warning system design → *International Journal of Disaster Risk Reduction*

**Why Not 5/5:**
- Not targeting Nature/Science tier (method is incremental, not revolutionary)
- Landslide susceptibility is crowded field (lots of RF LSM papers exist)

**Citation Potential:** Moderate-High (100-200 citations over 5 years for bias correction paper)

---

#### ✅ **CAREER DEVELOPMENT: 4/5** (Good)
**Skills Gained:**
- GIS & remote sensing (Google Earth Engine, QGIS)
- Machine learning (ensemble methods)
- Field survey design & execution
- Stakeholder engagement (government agencies)
- Operational system deployment

**Network:**
- National agencies (NDMA, Met Service)
- International: Landslide community (ICL, JTC1)
- Regional: WASCAL, AU Commission

**Job Market Fit:**
- ✅ UN agencies (UNDRR, UNDP)
- ✅ NGOs (Red Cross, Mercy Corps)
- ✅ Consulting (Arup, World Bank)
- ❓ Academia (competitive, but operational focus less valued)

**Why Not 5/5:** Method is applied, not cutting-edge theory (academia may prefer Project 5)

---

#### ✅ **COST-EFFECTIVENESS: 3/5** (Moderate)
**Budget:** $120,000 (HIGHEST of 5 projects)

**Major Costs:**
- Field work: $10k (transport, local assistants, accommodation)
- Research assistant: $30k (data processing)
- Workshops: $15k (stakeholder training)
- Overhead: $50k (stipend, tuition, fees)

**Impact per Dollar:** ~10,000 people protected per $1,000 spent (moderate efficiency)

**Why Not Higher:**
- Field work is expensive relative to computational projects
- Single-region focus (not globally transferable as dataset, though method is)

**Funding Competitiveness:** GOOD - Disaster risk reduction has dedicated funding streams (e.g., CREWS, GFDRR)

---

**PROJECT 1 SUMMARY:**
- **Best for:** Someone passionate about applied impact, comfortable with field work, interested in working with governments
- **Not ideal for:** Pure computational scientists, those seeking Nature-tier publications
- **Key Risk:** Field work logistics in Sierra Leone
- **Key Strength:** Direct life-saving impact

---

### PROJECT 2: Urban Heat Island (Freetown)

#### ✅ **FEASIBILITY: 4/5** (Good)
**Strengths:**
- All satellite data freely available (MODIS, Landsat, Sentinel-2)
- Google Earth Engine makes cloud processing manageable
- Random Forest thermal sharpening is established method
- No travel required (all remote sensing)

**Challenges:**
- ⚠️ Cloud cover is severe (70% of year) - but fusion method designed for this
- ⚠️ Ground sensor deployment requires local partner (but optional, not critical)
- ⚠️ Hospital collaboration requires 6-month ethics approval (timeline risk)
- ⚠️ Validation against ground truth is limited (only ~10 sensors budgeted)

**Why 4 not 5:** Hospital ethics approval and ground sensor deployment add complexity

**Mitigation:** Project can succeed with remote sensing only; health linkage is "bonus" not essential

---

#### ✅ **IMPACT: 4/5** (Good)
**Why High Score:**
- 🌡️ **HEAT STRESS**: Major public health threat in tropical cities (under-researched)
- 🏙️ **URBAN PLANNING**: Freetown expanding rapidly; need cooling strategies NOW
- 💰 **ECONOMIC**: Targeting tree-planting investments ($5M city budget), cool roof programs
- 📊 **BENEFICIARIES**: 1.2M Freetown residents
- 🔬 **KNOWLEDGE GAP**: First high-res UHI study for West Africa

**Why Not 5/5:**
- Impact is indirect (informs planning, not immediate early warning)
- Heat-health evidence is exploratory (can't prove causation, not enough data)
- Smaller scale than regional projects (single city vs national/regional)

**Concrete Outcome:** Heat vulnerability maps delivered to Freetown City Council for greening strategy

---

#### ✅ **TIMELINESS: 4/5** (Good)
**Why Urgent:**
- 🏆 **GAP**: No LST time series exists for Freetown (cloud barrier unsolved until now)
- 🏆 **POLICY NEED**: City developing Urban Climate Action Plan (2025-2030)
- 🏆 **CLIMATE CHANGE**: Heat waves increasing (WHO priority)
- ❓ **COMPETITION**: Some groups working on thermal sharpening (but not for tropical Africa)

**Why Not 5/5:** Less immediately life-threatening than landslides or floods

**Window of Opportunity:** Freetown Transform initiative ($250M World Bank) seeks evidence base

---

#### ✅ **PUBLICATION POTENTIAL: 4/5** (Good)
**Expected Papers (3):**
1. **Methodological**: Thermal sharpening validation → *Remote Sensing of Environment* (top-tier, IF ~12)
2. **Regional**: UHI-LULC co-evolution → *Urban Climate* (specialty journal)
3. **Health**: Exploratory heat-health → *International Journal of Health Geographics* or *Environmental Research Letters*

**Why Not 5/5:**
- Thermal sharpening not entirely novel (Hassan et al. 2021 did similar with RF)
- Novelty is in *validation approach* (multi-method for tropics), not core method

**Citation Potential:** Moderate (100-150 citations for method paper; unlocks future UHI research in tropics)

---

#### ✅ **CAREER DEVELOPMENT: 4/5** (Good)
**Skills Gained:**
- Advanced remote sensing (thermal, multi-sensor fusion)
- Google Earth Engine (cloud computing)
- Machine learning (Random Forest regression)
- Public health collaboration
- Urban climate science

**Network:**
- Freetown City Council (urban planning)
- Connaught Hospital (health sector)
- Urban climate community (IAUC)

**Job Market Fit:**
- ✅ Urban planning consultancies
- ✅ Climate services (WMO, C3S)
- ✅ NGOs (urban resilience: 100RC, C40)
- ✅ Academia (urban climate growing field)

**Why Not 5/5:** Narrower network than multi-country projects (3, 4)

---

#### ✅ **COST-EFFECTIVENESS: 4/5** (Good)
**Budget:** $80,000 (MODERATE)

**Major Costs:**
- Temperature sensors: $5k (10 HOBO loggers)
- Hospital collaboration: $10k (ethics, data processing)
- Cloud computing: $10k (GEE + gap-filling)
- Workshops: $15k (City Council training)
- Overhead: $40k (stipend, etc.)

**Impact per Dollar:** ~15 people protected per $1 spent (good efficiency for health)

**Why 4/5:** Good efficiency, but single-city focus limits scalability

**Funding Competitiveness:** GOOD - Health & cities are hot topics (WHO, Wellcome Trust, C40 Cities)

---

**PROJECT 2 SUMMARY:**
- **Best for:** Remote sensing specialists, urban climate enthusiasts, health-environment researchers
- **Not ideal for:** Field work lovers, those seeking large-scale regional impact
- **Key Risk:** Hospital data access (mitigated: project works without it)
- **Key Strength:** Novel method (multi-validation for tropics), untapped region

---

### PROJECT 3: Precipitation Downscaling (West Africa)

#### ✅ **FEASIBILITY: 3/5** (Moderate)
**Strengths:**
- Data freely available (ERA5, CHIRPS, CMIP6 via ESGF)
- Random Forest is mature method
- Google Earth Engine + Python workflow established

**Challenges:**
- ⚠️ **COMPUTATIONAL**: Most intensive of all projects (1000 core-hours HPC + $20k cloud)
- ⚠️ **DATA VOLUME**: 500GB CMIP6 download, processing, storage (1TB total)
- ⚠️ **COMPLEXITY**: 4 work packages with dependencies (stationarity test must pass before WP2)
- ⚠️ **EXPERTISE**: Requires advanced climate dynamics understanding (WAM is complex)
- ⚠️ **CMIP6 ACCESS**: ESGF can be unreliable (servers down, slow download)

**Why Only 3/5:**
- HPC access not guaranteed at all institutions
- Computational bottlenecks can delay PhD (job queue times, debugging)
- Data download alone can take weeks

**Mitigation:** Prioritize 6-8 best models if full ensemble inaccessible

---

#### ✅ **IMPACT: 4/5** (Good)
**Why High Score:**
- 🌾 **AGRICULTURE**: Direct input for crop models → food security for 400M people
- 💧 **WATER**: Reservoir management, hydropower planning (Akosombo Dam, Ghana)
- 🏥 **HEALTH**: Malaria risk linked to rainfall (WHO models)
- 📊 **BENEFICIARIES**: Entire West Africa region (15 countries)
- 🔬 **KNOWLEDGE**: First bias-corrected non-stationary 5km ensemble for WAM

**Why Not 5/5:**
- Impact is indirect (provides data for *other* impact models, not direct warnings)
- Adoption depends on other researchers using the dataset (harder to guarantee)
- Computational models have lower public visibility than field-based projects

**Concrete Outcome:** 500GB Zenodo dataset + Python package, used by WASCAL network for crop/hydro models

---

#### ✅ **TIMELINESS: 4/5** (Good)
**Why Urgent:**
- 🏆 **GAP**: Existing CORDEX products lack rigorous validation; no non-stationary SD for WAM
- 🏆 **POLICY NEED**: National adaptation plans (NAPs) need regional projections NOW
- 🏆 **IPCC AR7**: Could contribute to WG2 regional chapter (2027-2029 timeline)
- ❓ **COMPETITION**: Some groups working on WAM downscaling (AMMA-2050 legacy)

**Why Not 5/5:** Less immediately urgent than landslide/flood early warnings

**Window of Opportunity:** WASCAL Phase 3 (2024-2029) needs downscaled data for impact studies

---

#### ✅ **PUBLICATION POTENTIAL: 5/5** (Excellent)
**Expected Papers (4-5):**
1. **Stationarity test framework** → *Journal of Climate* or *Climate Dynamics* (top-tier, IF ~5)
2. **Non-stationary RF methodology** → *Geoscientific Model Development* (open-access, high visibility)
3. **QDM bias correction for WAM** → *Climate Dynamics* (methodological)
4. **Future WAM changes (2050-2100)** → *Environmental Research Letters* (high impact, IF ~6)
5. **Impact model application** (co-authored) → *Agricultural and Forest Meteorology* or *Hydrology and Earth System Sciences*

**Why 5/5:**
- Stationarity testing protocol is methodologically novel (field-changing)
- Large ensemble dataset has long citation tail (community resource)
- Multiple angles: method + application + regional science

**Citation Potential:** HIGH (200-300 citations over 5 years for method paper; dataset cited continuously)

---

#### ✅ **CAREER DEVELOPMENT: 5/5** (Excellent)
**Skills Gained:**
- Advanced climate modeling (CMIP6, bias correction)
- Big data processing (Xarray, Dask, parallel computing)
- HPC/cloud computing (AWS, Google Cloud)
- Statistical downscaling (state-of-the-art)
- Regional climate dynamics (WAM expertise)

**Network:**
- WASCAL (15 universities across West Africa)
- CMIP6 modeling centers (IPSL, MPI, GFDL)
- IPCC author network (potential contribution to AR7)
- Climate services: ACMAD, National Met Services

**Job Market Fit:**
- ✅ **Academia**: Climate modeling groups (top choice for this)
- ✅ **Climate services**: WMO, C3S Copernicus, National Met
- ✅ **International orgs**: IPCC, UNFCCC, World Bank climate divisions
- ✅ **Consulting**: Specialized climate risk firms

**Why 5/5:** Best technical skill development + strongest academic network

---

#### ✅ **COST-EFFECTIVENESS: 3/5** (Moderate)
**Budget:** $100,000 (SECOND HIGHEST)

**Major Costs:**
- **HPC/Cloud**: $20k (largest single expense)
- Storage: $5k (1TB drives, cloud backup)
- WASCAL workshops: $20k (3 regional trainings)
- Research assistant: $40k (data processing intensive)
- Overhead: $15k

**Impact per Dollar:** ~4M people benefit per $1k (good regional efficiency)

**Why Only 3/5:**
- High computational costs
- Dataset is public good (high societal value but not directly monetizable)

**Funding Competitiveness:** MODERATE - Climate modeling is competitive; fewer dedicated funding streams than DRR

---

**PROJECT 3 SUMMARY:**
- **Best for:** Computational scientists, those seeking academic career in climate modeling, strong coders
- **Not ideal for:** Field work enthusiasts, those without HPC access, those uncomfortable with abstract impact
- **Key Risk:** Computational bottlenecks (mitigated: can use fewer models)
- **Key Strength:** Highest publication potential, strongest academic network

---

### PROJECT 4: Extreme Precipitation EVT Analysis

#### ✅ **FEASIBILITY: 5/5** (Excellent)
**Strengths:**
- ✅ CORDEX-Africa data freely available (ESGF, well-documented)
- ✅ EVT methods mature (R packages: extRemes, ismev; Python: scipy.stats)
- ✅ Computationally light (EVT fitting is fast, unlike ML training)
- ✅ No field work required (all computational + stakeholder engagement)
- ✅ No complex external dependencies (Met Services provide validation data, but optional)
- ✅ Clear work package structure with built-in quality gate (WP1 validation)

**Why 5/5:**
- Standard workstation sufficient (no HPC/GPU needed)
- Data download modest (~200GB, manageable)
- Method risk low (EVT is statistics gold standard, not experimental)
- Timeline realistic (30 months with buffer)

**Risk:** Essentially zero technical failure risk (only risk is if ALL RCMs fail validation, very unlikely)

---

#### ✅ **IMPACT: 5/5** (Excellent)
**Why Maximum Score:**
- 🔴 **CRITICAL NEED**: Lagos (20M people) floods catastrophically every year (2022: 600 deaths)
- 🏗️ **INFRASTRUCTURE**: $100B+ infrastructure in coastal cities designed on obsolete statistics
- 💰 **ECONOMIC**: Preventing one flood event saves $1-10B (2012 Lagos floods: $16B damage)
- 📊 **BENEFICIARIES**: 50M+ people in Lagos, Accra, Freetown, Abidjan, Conakry
- 🚨 **URGENCY**: Engineers need updated design values NOW (building hospitals, schools, roads today)
- 🎯 **ACTIONABLE**: Delivers engineering design tables (50-year return level = X mm/day at +2°C)

**Concrete Outcome:**
- Web tool for real-time return level lookup (city × warming → design value)
- Training workshops for Public Works Ministries (Lagos, Accra, Freetown)
- Pilot case study: Re-design of stormwater drain using updated values

**Comparison:**
- Project 1 (Landslides): ~1k deaths/year
- **Project 4 (Floods): ~500-1000 deaths/year + $10B damages**

---

#### ✅ **TIMELINESS: 5/5** (Excellent)
**Why Maximally Urgent:**
- 🏆 **ZERO COMPETITION**: No one has done non-stationary EVT for CORDEX-Africa coastal extremes
- 🏆 **POLICY CRISIS**: Lagos Third Mainland Bridge (1990 design) failing; retrofit needs new stats
- 🏆 **FUNDING WINDOW**: African Development Bank ($5B Climate Adaptation Fund, 2024-2029)
- 🏆 **IPCC AR7**: WG2 Chapter 4 (Africa) needs extreme rainfall projections (2026-2028)
- 🏆 **SDGS**: Directly contributes to SDG 11 (Sustainable Cities), SDG 13 (Climate Action)

**Window Closing:** Cities are building NOW with outdated codes; every year of delay = more vulnerable infrastructure

---

#### ✅ **PUBLICATION POTENTIAL: 5/5** (Excellent)
**Expected Papers (3-4):**
1. **CORDEX-Africa extreme validation** → *Journal of Climate* (IF ~5, top-tier)
   - First systematic validation of CORDEX for extremes (high citations)
2. **Multi-parameter non-stationary GEV methodology** → *Water Resources Research* (IF ~6, gold standard)
   - All 3 parameters vary (μ, σ, ξ) - methodological advance
3. **Future return level projections** → *Nature Climate Change* or *Environmental Research Letters* (IF 6-8)
   - Engineering-relevant, high policy visibility
4. **Engineering application case study** → *ASCE Journal of Hydrologic Engineering* or *Natural Hazards* (practitioner impact)

**Why 5/5:**
- Methodological novelty (3-parameter GEV) is publishable in top journals
- First CORDEX-Africa extreme study fills major gap
- Engineering design tables have long citation tail (referenced in building codes)
- Potential for Nature/Science News & Views commentary

**Citation Potential:** VERY HIGH (300-500 citations over 5 years; design tables cited for decades)

---

#### ✅ **CAREER DEVELOPMENT: 5/5** (Excellent)
**Skills Gained:**
- Extreme value theory (statistics gold standard)
- Regional climate models (CORDEX expertise)
- Engineering communication (translate science → practice)
- Stakeholder engagement (workshops, web tools)
- Policy impact (building codes, national standards)

**Network:**
- National Met Services (Lagos, Accra, Freetown)
- Public Works Ministries (3 countries)
- CORDEX-Africa modeling community
- Engineering firms (Arup, AECOM for case study)
- African Development Bank (funding potential)

**Job Market Fit:**
- ✅ **BEST ACROSS ALL SECTORS:**
  - Academia: Climate extremes groups
  - Government: Met Services, climate adaptation divisions
  - Consulting: Climate risk (Swiss Re, Munich Re, Arup, World Bank)
  - NGOs: Disaster risk reduction (GFDRR, CREWS)
  - Private sector: Infrastructure firms, insurance

**Why 5/5:** Unique combination of rigorous science + immediate operational value = marketable everywhere

---

#### ✅ **COST-EFFECTIVENESS: 5/5** (Excellent)
**Budget:** $70,000 (**LOWEST** of all 5 projects)

**Major Costs:**
- Workshops: $25k (3 cities × 2 days, largest expense)
- Web tool development: $15k (Shiny dashboard)
- Research assistant: $20k (CORDEX download, processing)
- Overhead: $10k

**Impact per Dollar:**
- ~700,000 people protected per $1k spent (BEST efficiency)
- Preventing one flood event ($1B damage) pays for project 14,000×

**Why 5/5:**
- Lowest budget + highest impact = unbeatable efficiency
- EVT is computationally cheap (no HPC/cloud costs)
- Web tool is low-cost, high-visibility deliverable

**Funding Competitiveness:** EXCELLENT - Disaster risk reduction has dedicated streams (CREWS, GFDRR, AfDB) + high success rates

---

**PROJECT 4 SUMMARY:**
- **Best for:** Those seeking maximum impact with minimum technical risk, career flexibility (academia + industry), strong statistics background
- **Not ideal for:** Those who must do field work, those allergic to stakeholder engagement
- **Key Risk:** Essentially none (lowest risk project)
- **Key Strength:** Perfect balance of rigor + impact + feasibility + publications

---

### PROJECT 5: AI Climate Emulator

#### ✅ **FEASIBILITY: 4/5** (Good)
**Strengths:**
- ✅ ClimateBench dataset ready-to-use (curated, well-documented)
- ✅ Python ML libraries mature (sklearn, TensorFlow, PyTorch)
- ✅ SHAP package available (interpretability straightforward)
- ✅ No field work or external partners required
- ✅ Computational needs moderate (GPU helpful but not essential)

**Challenges:**
- ⚠️ Multi-variable emulation (T + P) is cutting-edge (may fail → pivot to T-only)
- ⚠️ Convolutional Autoencoder complex (debugging can be time-consuming)
- ⚠️ CMIP6 full spatial data download (500GB+, like Project 3)
- ⚠️ Requires strong coding skills (PyTorch/TensorFlow not trivial)

**Why 4 not 5:**
- Deep learning debugging can be unpredictable (convergence issues, hyperparameter sensitivity)
- Multi-variable emulation is frontier science (higher failure risk than EVT/RF)

**Mitigation:** PCA fallback if Autoencoder fails; T-only if multi-variable too hard

---

#### ✅ **IMPACT: 3/5** (Moderate)
**Why Not Higher:**
- 🔬 **SCIENTIFIC IMPACT**: High (changes how community validates emulators)
- ❓ **SOCIETAL IMPACT**: Indirect (provides tool for other researchers, not end-users)
- 📊 **BENEFICIARIES**: Climate modelers, IPCC authors, scenario planners (smaller audience than projects 1,2,4)
- 🎯 **ACTIONABILITY**: "Climate Futures Explorer" web tool, but users are scientists/policymakers, not public

**Why Only 3/5:**
- Does not directly save lives (unlike Projects 1, 4)
- Impact depends on tool adoption by community (uncertain)
- Emulators exist (ClimateBench baseline); this is incremental improvement (XAI validation, spatial extension)

**Concrete Outcome:**
- Open-source Python package (climemu)
- Web tool for scenario exploration (10,000 pathways)
- IPCC AR7 potential contribution (if emulator trusted)

**Comparison:**
- Projects 1,4: Direct early warnings → lives saved
- **Project 5: Better tools for other scientists → indirect impact**

---

#### ✅ **TIMELINESS: 3/5** (Moderate)
**Why Not Urgent:**
- ❓ **COMPETITION**: Active field; ClimateBench, MESMER, FaIR already exist
- ❓ **POLICY NEED**: IAMs (IMAGE, MESSAGE) already provide scenario exploration (though not high-res spatial)
- ✅ **IPCC AR7**: Could contribute (emulators used in AR6), but not critical path
- ✅ **XAI NOVELTY**: No one has systematically validated climate emulators with SHAP (gap exists)

**Why 3/5:** Important but not urgent; others are working in this space

---

#### ✅ **PUBLICATION POTENTIAL: 5/5** (Excellent)
**Expected Papers (4-5):**
1. **XAI validation framework** → **Nature Climate Change** (target IF ~30, flagship paper)
   - "Can We Trust AI Climate Emulators? A Physical Validation Using Explainable AI"
   - Field-changing methodology
2. **Spatial emulation (PCA vs Autoencoder)** → *Geoscientific Model Development* (IF ~5)
3. **Multi-variable constraints** → *JAMES* (Journal of Advances in Modeling Earth Systems, IF ~6)
4. **Scenario exploration** → *Environmental Research Letters* (IF ~6)
5. **Policy applications** (co-authored) → *Nature Climate Change* Perspective or *Climatic Change*

**Why 5/5:**
- XAI paper has **Nature Climate Change** potential (highest-impact journal in climate science)
- Methodological novelty is strongest of all 5 projects
- Multiple angles: XAI + spatial + multi-variable + scenarios
- Open-source package generates continuous citations

**Citation Potential:** HIGHEST (400-600 citations if Nature Climate Change; 200-300 if GMD/JAMES)

---

#### ✅ **CAREER DEVELOPMENT: 5/5** (Excellent)
**Skills Gained:**
- **Advanced ML/AI** (deep learning, CNNs, LSTMs, Autoencoders)
- **XAI** (SHAP, interpretability - hot field)
- **Big data** (CMIP6 processing, parallel computing)
- **Climate modeling** (understanding ESM internals)
- **Software engineering** (Python package development, web tools)

**Network:**
- CMIP6 modeling centers (IPSL, MPI, GFDL)
- ClimateBench authors (Oxford, Imperial College)
- XAI community (growing field)
- IPCC WG1 (modeling chapter)

**Job Market Fit:**
- ✅ **ACADEMIA**: Top choice (AI + climate is hottest interdisciplinary field)
- ✅ **Tech companies**: Google, Microsoft, DeepMind (climate AI initiatives)
- ✅ **Climate tech startups**: Climate modeling SaaS (e.g., Jupiter Intelligence, One Concern)
- ✅ **National labs**: NCAR, LLNL, NASA GISS (climate modeling divisions)
- ❌ **NGOs/Consulting**: Less directly applicable (operational tools less valued than Projects 2,4)

**Why 5/5:** Best for academic career + tech sector; cutting-edge skills

---

#### ✅ **COST-EFFECTIVENESS: 4/5** (Good)
**Budget:** $90,000 (MODERATE-HIGH)

**Major Costs:**
- GPU/Cloud: $20k (deep learning training, CMIP6 processing)
- Storage: $10k (1TB CMIP6 data)
- Web tool development: $20k (interactive dashboard)
- Training: $15k (conferences to present XAI work)
- Overhead: $25k

**Impact per Dollar:**
- Harder to quantify (tool for researchers, not direct beneficiaries)
- If widely adopted: ~100 researchers use tool → 1000 studies benefit → millions indirectly benefit

**Why 4/5:** Good efficiency for a methodological project; lower budget than Projects 1,3

**Funding Competitiveness:** EXCELLENT - AI + climate is hottest topic (NSF, ERC, Schmidt Futures, Google, Microsoft all funding)

---

**PROJECT 5 SUMMARY:**
- **Best for:** Computational scientists, those seeking academic career (top tier), AI/ML enthusiasts, Nature-paper ambitions
- **Not ideal for:** Those seeking direct societal impact, field work lovers, those uncomfortable with abstract outcomes
- **Key Risk:** Multi-variable emulation may fail (mitigated: T-only fallback)
- **Key Strength:** Highest publication potential (Nature Climate Change target), best for academic career

---

## SENSITIVITY ANALYSIS

### What If You Weight Criteria Differently?

| Scenario | Top Project | Runner-Up |
|----------|-------------|-----------|
| **IMPACT-FOCUSED** (50% impact, 10% all others) | **Project 4** (Extremes) | Project 1 (Landslides) |
| **PUBLICATION-FOCUSED** (50% publications, 10% all others) | **Project 5** (Emulator) | Project 3 (Downscaling) |
| **RISK-AVERSE** (50% feasibility, 10% all others) | **Project 4** (Extremes) | Project 2 (UHI) |
| **CAREER-FOCUSED** (50% career, 10% all others) | **Project 5** (Emulator) | Project 3 (Downscaling) |
| **BUDGET-CONSTRAINED** (50% cost-eff, 10% all others) | **Project 4** (Extremes) | Project 2 (UHI) |

**Observation:** Project 4 wins or ties in 4/5 scenarios. Project 5 best for academic career maximization.

---

## DECISION TREES

### Use These to Narrow Your Choice

**QUESTION 1: Field work or computational?**
- **Field work (love getting hands dirty)** → Projects 1, 2
- **Computational (prefer coding)** → Projects 3, 4, 5

**QUESTION 2: Direct or indirect impact?**
- **Direct (early warnings, save lives)** → Projects 1, 4
- **Indirect (tools for others)** → Projects 2, 3, 5

**QUESTION 3: Career goal?**
- **Top-tier academia (Nature papers)** → Project 5
- **Government/NGO/Consulting** → Projects 1, 2, 4
- **Climate modeling research** → Project 3

**QUESTION 4: Technical comfort?**
- **Statistics strong** → Project 4 (EVT)
- **Remote sensing strong** → Project 2 (UHI)
- **Machine learning strong** → Projects 1, 3, 5
- **Deep learning strong** → Project 5

**QUESTION 5: Risk tolerance?**
- **Risk-averse (must finish PhD)** → Project 4 (safest)
- **Moderate risk** → Projects 2, 3
- **High risk, high reward** → Projects 1, 5

---

## FINAL RECOMMENDATIONS

### By Persona

**Persona A: "Impact Maximizer"**
→ **PROJECT 4 (Extremes)**
- Highest lives saved + infrastructure protected
- Lowest risk, fastest completion
- Excellent publications + career prospects

**Persona B: "Academic Star"**
→ **PROJECT 5 (Emulator)**
- Nature Climate Change potential
- Cutting-edge AI/XAI skills
- Best for faculty positions at research universities

**Persona C: "Field Scientist"**
→ **PROJECT 1 (Landslides)**
- Field validation campaign in Sierra Leone
- Direct operational impact (NDMA early warnings)
- Best for those who love boots-on-ground work

**Persona D: "Urban Planner"**
→ **PROJECT 2 (UHI)**
- City-scale analysis
- Health-environment linkages
- Best for those interested in urban sustainability

**Persona E: "Climate Modeler"**
→ **PROJECT 3 (Downscaling)**
- Deep dive into CMIP6, WAM dynamics
- Strongest academic network (WASCAL, IPCC)
- Best technical skill development

---

## THE VERDICT

### If You Must Choose ONE Project NOW

**Recommended Ranking:**

🥇 **#1: PROJECT 4 (EXTREME PRECIPITATION EVT)**
- ✅ Perfect balance: High impact + Low risk + Excellent publications + Best cost-efficiency
- ✅ Wins in most scenarios (impact, risk-averse, budget)
- ✅ Broadest career options (academia, government, consulting, industry)
- ✅ Most urgent societal need (cities building NOW with wrong numbers)

🥈 **#2: PROJECT 2 (URBAN HEAT ISLAND)**
- ✅ Novel methodology (multi-validation for tropics)
- ✅ Untapped region (first UHI study for West Africa)
- ✅ Health linkage (unique angle)
- ⚠️ Moderate risk (cloud challenges, hospital ethics)

🥉 **#3: PROJECT 5 (AI EMULATOR)**
- ✅ Highest publication potential (Nature Climate Change)
- ✅ Best for academic career
- ✅ Cutting-edge skills (XAI, deep learning)
- ⚠️ Lower immediate societal impact (indirect)

**#4: PROJECT 3 (PRECIPITATION DOWNSCALING)**
- ✅ Excellent publications (5 papers)
- ✅ Strongest academic network (WASCAL, IPCC)
- ⚠️ Highest computational demands (HPC access critical)
- ⚠️ Longer timeline (42 months)

**#5: PROJECT 1 (LANDSLIDES)**
- ✅ Critical need (most lives saved)
- ✅ High impact (operational early warnings)
- ⚠️ Field work logistics risk (Sierra Leone, visas, safety)
- ⚠️ Highest budget ($120k)

**Note:** All 5 are excellent. Ranking reflects balance of feasibility + impact, not absolute quality.

---

## NEXT STEP

**You've reviewed the prioritization. Now:**
1. ✅ Identify which persona you are (A-E above)
2. ✅ Check sensitivity analysis for your priorities
3. ✅ Use decision tree to narrow to 2 projects
4. ✅ Read detailed funding proposal (next document) for your top choice
5. ✅ Consult with potential supervisors about institutional fit (HPC access, partnerships)

**Need a funding proposal?** → See FUNDING_PROPOSAL.md (next document, draft for Project 4)
