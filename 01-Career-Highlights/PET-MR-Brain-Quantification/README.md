# PET-MR Brain Quantification Pipeline

> **Note:** This project was developed for a medical imaging startup under proprietary license. 
> Full source code cannot be shared, but technical approach, architecture, and validation results 
> are documented here.

## 📋 Project Overview

**Timeline:** 2020-2022  
**Role:** R&D Engineer - Technical lead  
**Status:** Successfully deployed, validated across multiple clinical sites  

## 🎯 Business Context

**Challenge:** The company's core product focused on MR-only brain analysis. To expand market 
Reach and address unmet clinical needs, we wanted to add PET imaging quantification capabilities.

**Stakeholders:**
- Clinical neurologists (end users)
- Radiopharmaceutical research partners
- Company leadership (product strategy)

**Constraints:**
- Must achieve clinical-grade accuracy
- Seamless integration with existing MR pipeline
- Multiple PET tracers support (PiB, FMT, FBP, FBB, NAV4694)

## 🔬 Technical Challenge

**Core Problem:** Accurate uptake quantification requires:
1. Precise spatial alignment between PET and MR modalities
2. Consistent anatomical region definition across subjects
3. Robust handling of variable image quality and acquisition protocols


## 🏗️ Solution Architecture

### High-Level Pipeline

Input: PET + MR Nifti images 

Output: Quantitative results

<img src="Images/pipeline_registration.svg" width="400" alt="Registration and quantification pipeline">

<!--![Registration and quantification pipeline](Images/pipeline_registration.svg)
-->


### Key Technical Decisions


<!--
**1. Registration Strategy: B-spline Non-Linear**
- **Alternative considered:** Demons algorithm
- **Decision rationale:** Better balance between accuracy and computational cost
- **Trade-off:** Increased processing time (+30 s) vs. 15% improvement in alignment accuracy

**2. Atlas Choice: MNI 152 with Custom Parcellation**
- **Alternative:** FreeSurfer-based segmentation
- **Decision:** Pre-computed atlas → 10 x faster than subject-specific segmentation
- **Trade-off:** Slight accuracy loss acceptable for clinical workflow speed

**3. Normalization:** Reference region approach (cerebellar gray matter)
- **Validated across:** 5 different PET tracers
- **Robust to:** Scanner variations, reconstruction protocols
-->

1. Registration strategies

Linear registration is an iterative process that uses a 12-parameter affine transformation (3 translations, 3 rotations, 3 scalings, 3 shears) to align the source image globally with the MNI template. Optimization is done by maximizing the likelihood of the tissue segmentation model, comparing the source tissue maps (GM, WM, CSF) to the template tissue probability maps. The optimization is performed using a Gauss-Newton method with a multiresolution scheme: at each iteration, the affine parameters are updated to minimize the sum-of-squared differences between the segmented source tissues and the template priors.

Nonlinear registration is also an iterative, parametric process. The deformation field is represented using cosine basis functions. At each iteration, these coefficients are updated using a regularized Gauss-Newton optimization. The resulting deformation is a smooth, voxelwise field that precisely aligns local anatomical structures with the template MNI space.


### Technology Stack

Core: Python 3.9+ Imaging: NiBabel, SPM12


## 🔬 Validation & Results

### Quantitative Validation

**Dataset:**
- 289 subjects
- 5 different PET tracers (PiB, FMT, FBP, FBB, NAV4694)
- Reference: published results (see References)

**Metrics Achieved:**

Pearson Correlation R² vs published results 

├─ PiB: R² = 1.00 (n=79) 

├─ FMT: R² = 0.96 (n=74) 

├─ FBP: R² = 0.91 (n=46) 

├─ FBB: R² = 0.95 (n=35) 

└─ NAV4694: R² = 0.99 (n=55)



## 🚀 Production & Integration

__Deployment:__

- Integrated into company's flagship software

<!--
## 🎓 Lessons Learned

__What Worked Well:__

1. Early clinical validation → identified edge cases before heavy development
2. Modular pipeline → easy to swap registration backends
3. Extensive automated testing → caught issues before production

__Challenges Overcome:__

1. __PET noise variability: __ Required custom preprocessing per tracer type
   - Solution: Adaptive denoising parameters based on count statistics
1. __MR artifacts: __ Metal dental work caused registration failures
   - Solution: Robust masking + fallback to rigid registration
1. __Speed vs. Accuracy trade-off: __ Initial version too slow (12 min)
   - Solution: GPU acceleration + parameter tuning → 3.2 min

__What I'd Do Differently:__

- Earlier Docker containerization (would have simplified deployment)
- More systematicization of hyperparameter tuning (used ad-hoc approach)
-->

## 🔗 Related Work

__External validation:__

- Huet P., Cavedo E., Longo dos Santos C., Schwarz A.J.
An automated pipeline for Centiloid quantification of amyloid load using multiple PET tracers.
AD/PD 2022 International Conference, Barcelona, 15-20 Mar 2022.

__References:__
- Klunk WE, Koeppe RA, Price JC, Benzinger TL, Devous MD Sr, Jagust WJ, Johnson KA, Mathis CA, Minhas D, Pontecorvo MJ, Rowe CC, Skovronsky DM, Mintun MA. The Centiloid Project: Standardizing quantitative amyloid plaque estimation by PET. Alzheimers Dement. 2015;11(1):1-15.e1-4. doi: 10.1016/j.jalz.2014.07.003. PMID: 25443857

- Navitsky M, Joshi AD, Kennedy I, Klunk WE, Rowe CC, Wong DF, Pontecorvo MJ, Mintun MA, Devous MD Sr. Standardization of amyloid quantitation with florbetapir standardized uptake value ratios to the Centiloid scale. Alzheimers Dement (Amst). 2018;10:357-365. doi: 10.1016/j.dadm.2018.02.002

- Rowe CC, Doré V, Jones G, Baxendale D, Mulligan RS, Bullich S, Stephens AW, De Santi S, Masters CL, Villemagne VL. 18F-Florbetaben PET beta-amyloid binding expressed in Centiloids. Eur J Nucl Med Mol Imaging. 2017;44(12):2053-2059. doi: 10.1007/s00259-017-3749-6

- Battle MR, Joshi AD, Minhas D, Devous MD Sr, Pontecorvo MJ, Rowe CC, Skovronsky DM, Burns C, Masters CL, Southekal S, Vandenberghe R, Van Laere K, Mintun MA, Navitsky M. Centiloid scaling for quantification of brain amyloid with [18F]flutemetamol using multiple processing methods. EJNMMI Res. 2018;8(1):108. doi: 10.1186/s13550-018-0456-7

- Rowe CC, Jones G, Doré V, Pejoska S, Margison L, Mulligan RS, O'Keefe G, Chan JG, Young K, Masters CL, Villemagne VL. Standardized Expression of 18F-NAV4694 and 11C-PiB β-Amyloid PET Results with the Centiloid Scale. J Nucl Med. 2016;57(8):1233-1237. doi: 10.2967/jnumed.115.171595


<!--
## 📁 Repository Contents

```javascript
PET-MR-Brain-Quantification/
├── README.md (this file)
├── architecture_diagram.png
├── technical_approach_detailed.pdf
├── validation_results/
│   ├── correlation_analysis.png
│   ├── metrics_summary.csv
│   └── sample_cases/ (anonymized visualizations)
├── code_samples/
│   └── registration_optimization.py (pseudocode/concept)
└── presentations/
    └── clinical_validation_summary.pdf
-->

