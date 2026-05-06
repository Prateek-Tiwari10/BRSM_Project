# BRSM Project: Event Segmentation and Boundary Effects on Recognition Memory

**Course:** BRSM (Behavioural Research & Statistical Methods)
**Team:** Vibe Coders
**Repository**: [GitHub Repository](https://github.com/Prateek-Tiwari10/BRSM_Project)

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Research Question](#research-question)
3. [Theoretical Background](#theoretical-background)
4. [Why This Study Matters](#why-this-study-matters)
5. [Experimental Design](#experimental-design)
6. [Dataset Description](#dataset-description)
7. [Data Cleaning &amp; Preprocessing](#data-cleaning--preprocessing)
8. [Statistical Analysis Approach](#statistical-analysis-approach)
9. [Key Findings](#key-findings)
10. [File Structure](#file-structure)
11. [How to Reproduce the Analysis](#how-to-reproduce-the-analysis)
12. [Design Decisions &amp; Rationale](#design-decisions--rationale)
13. [Dependencies](#dependencies)
14. [Team Contributions](#team-contributions)
15. [References](#references)

---

## Project Overview

This project investigates **how the temporal position of a video clip's ending relative to natural event boundaries affects recognition memory for individual video frames**. The study tests predictions from **Event Segmentation Theory (EST)**, which proposes that humans spontaneously segment continuous experiences into discrete events, and that event boundaries enhance memory encoding and consolidation.

### Core Research Question

**Does disrupting natural event boundaries impair memory for video frames, particularly for frames adjacent to those boundaries?**

---

## Research Question

We examined whether participants who viewed videos ending at **natural event boundaries** (e.g., a person completing an action) show better recognition memory compared to participants who viewed videos **truncated abruptly before reaching the boundary** (mid-event).

**Primary Hypotheses:**

1. **H1 (Main Effect):** Participants in the Natural Boundary (NB) condition will demonstrate higher overall recognition accuracy than those in the Abrupt Boundary (AB) condition.
2. **H2 (Boundary Frame Advantage):** The NB advantage will be significantly stronger for frames from 0-3 seconds before the boundary (BB frames) compared to frames from the middle of events (EM frames).
3. **H3 (Null Effect on Event-Middle Frames):** NB and AB conditions will not differ significantly on recognition accuracy for EM frames, as these frames are temporally distant from the disrupted boundary.

---

## Theoretical Background

### Event Segmentation Theory (EST)

**Event Segmentation Theory** (Zacks et al., 2007) proposes that:

- Humans spontaneously parse continuous experience into discrete events
- The cognitive system maintains **predictive models** of what will happen next
- When predictions fail (e.g., scene changes, action shifts), the system experiences **prediction error**
- These prediction errors signal **event boundaries**
- At boundaries, the cognitive system "saves" the current event representation to long-term memory while preparing to encode a new event

### The Boundary Advantage Effect

**Swallow et al. (2009)** demonstrated the **Boundary Advantage Effect**: superior memory for information presented at event boundaries compared to event middles. This occurs because:

1. **Enhanced attention** at boundaries due to prediction error
2. **Memory consolidation** of the completed event model
3. **Preparation for new encoding** as a new event begins

### Study Predictions

If natural event boundaries enhance memory encoding through these mechanisms, then **artificially truncating videos before they reach natural boundaries** should:

- **Prevent** the normal boundary-related memory enhancement
- **Impair** recognition for frames that would have been near the (now absent) boundary
- **Weaken** overall event memory by interrupting the event model updating process

---

## Why This Study Matters

### Theoretical Significance

1. **Tests Event Segmentation Theory predictions** in a controlled experimental paradigm
2. **Isolates the causal role** of event boundaries in memory encoding (not just correlational)
3. **Extends knowledge** about how temporal structure affects memory for dynamic visual information

### Practical Applications

1. **Video editing and multimedia design:** Cutting videos at natural boundaries may optimize viewer comprehension and memory retention
2. **Educational materials:** Structuring instructional videos around natural event boundaries could enhance learning outcomes
3. **Human-computer interaction:** Understanding event segmentation can inform design of video interfaces and content delivery systems
4. **Eyewitness memory:** Insight into how event structure affects memory for real-world dynamic events

---

## Experimental Design

### Design Type

**2 × 2 Mixed Design:**

- **Between-subjects factor:** Condition (NB vs AB)
- **Within-subjects factor:** Frame Type (BB vs EM)you want, I can also tighten wording in the “Bonferroni Correction” subsection to match the new nonparametric

### Independent Variables

#### 1. Condition (Between-Subjects)

- **NB (Natural Boundary):** Videos ended at natural event boundaries
  - Example: A person completing a hand gesture, finishing pouring water, closing a door
- **AB (Abrupt Boundary):** Videos were truncated 1-5 seconds **before** the natural boundary
  - Example: Stopping mid-gesture, mid-pour, mid-door-closing

#### 2. Frame Type (Within-Subjects)

- **BB (Before Boundary):** Frames extracted from 0-3 seconds before the natural event boundary
  - These frames are most proximal to the manipulated boundary
- **EM (Event Middle):** Frames extracted from the middle of the event, far from boundaries
  - These frames serve as a control to test boundary-specificity

### Dependent Variables

1. **Recognition Accuracy (Primary DV):** Binary (0 = incorrect, 1 = correct identification of target frame)
2. **Response Time (Secondary DV):** Time in seconds from stimulus onset to response
3. **Confidence Rating (Secondary DV):** Self-rated confidence (1-5 scale)

### Procedure

1. **Encoding Phase:**
   - Participants viewed 40 short video clips (17-57 seconds each)
   - Participants viewed 40 short video clips (17-57 seconds each)
   - Videos depicted everyday activities (cooking, cleaning, object manipulation)
   - Random assignment to NB or AB condition
2. **Recognition Phase:**
   - 40 forced-choice trials (one per video)
   - 40 forced-choice trials (one per video)
   - Each trial: Two frames presented side-by-side
     - **Target:** Frame actually shown in the video
     - **Lure:** Similar frame NOT shown in the video
   - Participants selected which frame they recognized
   - Confidence rating collected immediately after each decision
3. **Demographics:**
   - Age, gender, handedness, vision status collected post-experiment
   - Age, gender, handedness, vision status collected post-experiment

### Participant Exclusion Criteria

- Participants with **< 20 valid trials** excluded from analysis (incomplete/corrupted data)
- This ensured sufficient data per participant for reliable mean accuracy estimates

---

## Dataset Description

### Data Sources

1. **Recognition Data:**
   - Individual CSV files per participant
   - Individual CSV files per participant
   - Location: `BRSM data csv/`
   - Naming convention: `sub[ID]_[Condition]_recognitionstage_[timestamp].csv`
2. **Demographic Data:**
   - Single Excel file: `Demographic data.xlsx`
   - Single Excel file: `Demographic data.xlsx`
   - Contains: Age, Gender, Handedness, Vision status per participant
3. **Stimulus Metadata:**
   - `abruptmovies.csv`: List of movies in AB condition
   - `naturalmovies.csv`: List of movies in NB condition
   - `target_and_lures.csv`: Frame pairs used in recognition trials

### Sample Characteristics

- **Final analytic sample:** 165 participants (after exclusions)
- **Complete demographic records:** 185 participants
- **Age (complete records):** M = 22.3 years, SD = 2.2, Range = 19-34 years
- **Gender (complete records):** Female = 50, Male = 135
- **Handedness (complete records):** Right-handed = 176, Left-handed = 9
- **Vision (complete records):** Normal = 106, Corrected-to-normal = 77, Uncorrected difficulty = 2

### Condition Assignment

- **NB Condition:** 87 participants
- **AB Condition:** 78 participants
- Age and gender balanced across conditions (D1--D2 non-significant)

### Trial Structure

- **40 trials per participant** (targeted)
- Post-exclusion trial rows: **6,487**
- Each trial tests either BB or EM frame (counterbalanced within-subjects)

---

## Data Cleaning & Preprocessing

### Why Data Cleaning Was Necessary

Raw data from PsychoPy experiments often contains:

- Inconsistent string formatting (brackets, extra spaces)
- Missing values from incomplete trials
- Extreme outliers from accidental key presses or inattention
- Redundant columns from experimental software
- Session timing anomalies (excessive delays between phases)

### Cleaning Pipeline (Implementation)

#### Step 1: Participant and condition alignment

- Build `participant_id` from the demographic file and drop missing IDs.
- Sync `Condition` from participant CSV filenames (ground truth).

#### Step 2: Encoding time exclusion

- Exclude participants with encoding time > 27.05 minutes.
- Encoding time = `recognition.started` minus `instruction_2.stopped` (minutes).

#### Step 3: Trial-level parsing and filters

- Parse `Accuracy`, `RT`, and `Confidence` as numeric.
- Keep only valid trials (movie 1--40, Accuracy in {0,1}).
- RT filters: remove `RT < 0.2 s` and `RT > mean + 3 SD` (computed from trial RTs).

#### Step 4: Frame type derivation

- `FrameType` from `target_img` filename: `BB` if contains "BB", `EM` if contains "EM".

#### Step 5: Aggregate for analysis

- Participant-level means for accuracy.
- Participant x FrameType means for BB/EM comparisons.

#### Step 6: Demographic merge

- Merge participant-level performance with demographic fields for D1--D3 checks.

---

## Statistical Analysis Approach

### Why These Methods Were Chosen

#### 1. Nonparametric Tests

**Decision:** Use nonparametric tests because the data are not normally distributed.

**Rationale:**

- Nonparametric tests do not assume normality.
- More appropriate for skewed or non-normal accuracy distributions.
- Robust to outliers and uneven variance patterns.
- Aligns with the final analysis workflow used in the report.

**Tests Used in the Report:**

- **H1:** ART ANOVA, Mann-Whitney U, Permutation Test, Median Test
- **H2:** ART ANOVA, Wilcoxon Signed-Rank, Sign Test, Friedman Test
- **H3:** ART ANOVA, Mann-Whitney U, Permutation Test, Bootstrap CI
- **H4:** ART ANOVA (interaction), Mann-Whitney (advantage), Permutation Test, Friedman Test
- **H5:** Spearman correlations, Mann-Whitney, Interaction GLMM, Permutation Test
- **H6:** Kruskal-Wallis, ART ANOVA (interaction), Mann-Whitney, Permutation Test
- **H7:** Levene, Brown-Forsythe, Permutation Test, Bootstrap CI
- **H8:** Spearman, Linear Regression, Median Split, Permutation Test

---

#### 2. Bonferroni Correction for Multiple Comparisons

**Decision:** Apply Bonferroni correction to the four primary hypotheses.

**Rationale:**

- Multiple nonparametric tests are run per hypothesis, increasing false-positive risk.
- Bonferroni controls the family-wise error rate for the primary set.
- Adjusted alpha = 0.05 / 4 = **0.0125**.

**Alternative Methods Considered:**

| Method                 | Why Not Used                                                     |
| ---------------------- | ---------------------------------------------------------------- |
| Holm-Bonferroni        | More complex; minimal power gain with k=4                        |
| Benjamini-Hochberg FDR | For exploratory studies with many tests; we have 4 planned tests |
| No correction          | Unacceptable inflation of FWER (18.6%)                           |

**Which Tests Use Bonferroni?**

- **Primary tests (alpha = 0.0125):** H1--H4 (confirmatory hypotheses)
- **Demographic tests (alpha = 0.05):** D1--D3 (exploratory checks, separate family)

**Trade-off Accepted:**

- Bonferroni is conservative, but it keeps the confirmatory results reliable.

---

#### 3. Demographic Tests (Exploratory Analyses)

**Decision:** Report demographic tests with **unadjusted alpha = 0.05**

**Tests Conducted:**

- **D1:** Age balance (NB vs AB) [Randomization check]
- **D2:** Gender balance (NB vs AB) [Randomization check]
- **D3:** Age x Accuracy relationship [Exploratory]

**Rationale for No Correction:**

1. **Separate hypothesis family** from primary tests
2. **Exploratory nature** (not confirmatory hypotheses)
3. **Randomization checks** (D1, D2) verify experimental validity, not test theory
4. **Moderator analyses** (D3) are hypothesis-generating

Applying Bonferroni here would be overly conservative and is not standard practice for auxiliary analyses.

---

### Statistical Assumptions

#### Tested and Verified:

1. **Independence of observations:** ✓ (participant-level aggregation)
2. **Random sampling:** ✓ (convenience sample typical of psychology)
3. **Nonparametric robustness:** ✓ (tests do not require normality)

---

## Key Findings

### Summary of Hypothesis Decisions (H1--H8)

- **H1 (Condition effect):** Pass
- **H2 (Boundary advantage):** Fail under the decision rule (boundary advantage evident, but rule not met)
- **H3 (Event-middle stability):** Pass
- **H4 (Interaction):** Fail
- **H5 (Confidence--accuracy relationship):** Fail
- **H6 (Difficulty moderation):** Pass
- **H7 (Variability effect):** Fail
- **H8 (Encoding strength):** Fail

### Demographic Checks (D1--D3)

- **D1 (Age balance):** Fail (non-significant)
- **D2 (Gender balance):** Fail (non-significant)
- **D3 (Age x Accuracy):** Fail (non-significant)

### Conclusions (From Report)

- Natural boundaries improve memory accuracy, consistent with an encoding-based effect.
- Response time shows no reliable change across conditions.
- The benefit is general rather than strictly boundary-specific.
- Boundary advantages are stronger under higher difficulty.
- Event-middle memory remains stable across conditions.
- Confidence--accuracy alignment does not improve.
- Variability and encoding duration show no reliable effects.
- Demographic factors do not influence outcomes.
- Boundary completion matters more than proximity to the boundary.
- Interrupting events before completion reduces memory globally.

---

## File Structure

```
BRSM_Project/
│
├── BRSM data csv/
│   ├── sub*_AB_recognitionstage_*.csv   # Participant CSVs (AB)
│   ├── sub*_NB_recognitionstage_*.csv   # Participant CSVs (NB)
│   └── Sub*_recognitionstage_*.csv      # Early files with capitalized prefix
│
├── datafile/
│   ├── Demographic data.xlsx            # Demographics (Age, Gender, Handedness, Vision)
│   ├── abruptmovies.csv                 # AB condition movie list
│   ├── naturalmovies.csv                # NB condition movie list
│   └── target_and_lures.csv             # Frame pairs used in recognition trials
│
├── endsemwork/
│   ├── data_eda.Rmd                      # End-sem EDA pipeline
│   ├── hypotheses_results.Rmd            # End-sem tests and results
│   ├── report.tex                        # End-sem LaTeX report
│   └── report.pdf                        # Compiled report
│
├── midsemwork/
│   └── ...
│
└── README.md                             # THIS FILE

```

### Key Files Explained

#### Analysis Files

1. **`endsemwork/data_eda.Rmd`**

   - **Purpose:** End-sem data processing and EDA pipeline
   - **Output:** Figures in `output_plots/`
2. **`endsemwork/hypotheses_results.Rmd`**

   - **Purpose:** End-sem hypothesis tests and summary tables
3. **`endsemwork/report.tex`**

   - **Purpose:** Final LaTeX report used for submission

#### Data Files

- **Individual CSVs:** One per participant, ~40 rows (trials) per file in `BRSM data csv/`
- **Demographic data.xlsx:** Master demographic sheet in `datafile/`
- **Stimulus metadata CSVs:** Reference files for video stimuli classification in `datafile/`

---

## Design Decisions & Rationale

### 1. Why Mixed Design (Between + Within)?

**Decision:** Use between-subjects manipulation for Condition, within-subjects for Frame Type

**Rationale:**

**Between-subjects (Condition):**

- ✓ Avoids carryover effects (seeing both NB and AB versions of same video)
- ✓ Prevents participants from inferring experimental manipulation
- ✓ Eliminates practice effects on boundary detection
- ✗ Requires larger sample size (N = 163 vs ~82 for within-subjects)

**Within-subjects (Frame Type):**

- ✓ Controls individual differences (each person is their own control)
- ✓ Increases statistical power for frame type comparisons
- ✓ Reduces required sample size
- ✓ BB and EM frames occur naturally within same video (unavoidable)

**Hybrid approach** balances power, validity, and feasibility.

---

### 2. Why 40 Trials Per Participant?

**Decision:** Each participant completes 40 recognition trials (one per video)

**Rationale:**

- **Reliability:** 40 trials provides stable mean accuracy estimates (Hedge et al., 2018)
- **Attention span:** ~15-20 minutes prevents fatigue
- **Counterbalancing:** 20 BB trials + 20 EM trials balances frame type exposure
- **Sufficient power:** With 163 participants × 40 trials = 6,520 observations
- Alternative (fewer trials) would reduce measurement reliability

---

### 3. Why Exclude Participants with < 20 Trials?

**Decision:** Participants with < 20 valid rows excluded from analysis

**Rationale:**

- 40 trials expected; < 20 suggests incomplete data (< 50% completion)
- Mean estimates unreliable with small trial counts (high standard error)
- Likely causes: Software crash, early withdrawal, data corruption
- **Conservative threshold:** Retains participants with minor data loss (≥20/40 = 50%)
- Alternative (stricter threshold like < 35) would reduce sample size unnecessarily

**Impact:** 22/185 participants excluded (11.9% exclusion rate, acceptable)

---

### 4. Why Mean + 3 SD for RT Outliers?

**Decision:** Remove RT observations exceeding Mean + 3 SD = 5.08 seconds

**Rationale:**

**3 SD chosen because:**

- Standard in psychology and cognitive science
- Captures ~99.7% of normal distribution (retains most data)
- More conservative than 2 SD (which would exclude ~5% of data)
- Less conservative than no removal (which inflates variance estimates)

**Alternative methods considered:**

| Method                          | Why Not Used                                               |
| ------------------------------- | ---------------------------------------------------------- |
| 2 SD                            | Too aggressive (excludes ~5% of normal data)               |
| Median Absolute Deviation (MAD) | Less interpretable; similar results                        |
| No removal                      | Inflates variance; violates normality for parametric tests |
| Fixed cutoff (e.g., 3 seconds)  | Arbitrary; not data-driven                                 |

**Result:** 87/6,520 trials removed (1.3%, minimal impact)

---

### 5. Why Participant-Level Aggregation?

**Decision:** Aggregate trial-level data to participant means before t-tests

**Rationale:**

**Statistical requirement:**

- t-tests assume **independent observations**
- Trials from same participant are **correlated** (non-independent)
- Violating independence inflates Type I error rate

**Why not mixed-effects models?**

Mixed-effects models (e.g., `lme4::lmer()`) can handle trial-level data with random intercepts for participants. We chose aggregation because:

| Aggregation (Used)             | Mixed-Effects (Not Used)           |
| ------------------------------ | ---------------------------------- |
| ✓ Simple and transparent      | ✗ More complex to report          |
| ✓ Standard in psychology      | ✗ Requires additional assumptions |
| ✓ Robust to violations        | ✗ Model convergence issues common |
| ✓ Easy to verify by reviewers | ✗ Model specification debatable   |

For **balanced designs** with **sufficient trials per participant**, aggregation and mixed-effects yield **nearly identical results** (Judd et al., 2012).

---

### 6. Why Bonferroni (Not Other Corrections)?

**Decision:** Apply Bonferroni correction (alpha = 0.05/4 = 0.0125)

**Comparison of methods:**

| Method                 | FWER Control | Power           | Complexity | Used?  |
| ---------------------- | ------------ | --------------- | ---------- | ------ |
| **Bonferroni**   | ✓ Exact     | Moderate        | Low        | ✓ YES |
| Holm-Bonferroni        | ✓ Exact     | Slightly higher | Moderate   | ✗ No  |
| Šidák                | ✓ Exact     | Slightly higher | Low        | ✗ No  |
| Benjamini-Hochberg FDR | ✗ FDR only  | High            | Moderate   | ✗ No  |
| No correction          | ✗ Inflated  | Highest         | None       | ✗ No  |

**Bonferroni chosen because:**

- Most conservative (minimizes false discoveries)
- Standard in psychology for small number of tests (k ≤ 10)
- Simple to communicate to non-statisticians
- Reviewers expect it for confirmatory hypotheses

**Not Holm-Bonferroni because:**

- Marginal power gain (~2%) not worth added complexity
- Requires ranking p-values (order matters)
- Less familiar to general audience

**Not FDR because:**

- FDR controls expected proportion of false discoveries (not FWER)
- Appropriate for exploratory studies with many tests (k > 50)
- We have 4 planned confirmatory tests

---

### 7. Why These Visualizations?

**Figures Included in Condensed Report:**

| Figure                                       | Purpose                                              | Design Choice                                              |
| -------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------------- |
| **Figure 1: Violin Plot (Condition)**  | Show distribution shape, outliers, central tendency  | Violin shows full distribution (better than boxplot alone) |
| **Figure 2: Density Plot**             | Compare probability distributions between conditions | Smooth curves easier to compare than histograms            |
| **Figure 3: Violin Plot (Frame Type)** | Demonstrate Boundary Advantage Effect (BB > EM)      | Consistent with Figure 1 for comparability                 |
| **Figure 4: Bar Chart with 95% CI**    | Quantify interaction (Condition × Frame Type)       | Error bars show statistical uncertainty                    |
| **Figure 5: Heatmap**                  | Visualize 2×2 interaction pattern                   | Intuitive color gradient (dark blue = high accuracy)       |

**Design Principles:**

- **Color scheme:** Consistent across figures (NB = blue, AB = red, BB = green, EM = orange)
- **Theme:** Clean, minimal distraction (theme_classic base)
- **Annotations:** Every figure has interpretation paragraph

---

### 9. Why Include Demographic Tests?

**Decision:** Report 4 demographic tests (D1-D4) despite not being primary hypotheses

**Rationale:**

**D1 & D2 (Randomization checks):**

- Essential for experimental validity
- Confirm random assignment succeeded
- Standard requirement in experimental psychology

**D3 & D4 (Moderator analyses):**

- Address potential alternative explanations
- Exploratory (hypothesis-generating)
- Inform future research

**Transparency:** Including non-significant results prevents publication bias

## Team Contributions

### Meet Ghelani (2025201096)

**Responsibilities:**

- Data cleaning and preprocessing pipeline
- Participant exclusion criteria implementation
- RT outlier detection algorithm (Mean + 3 SD)
- Demographic data integration (merging CSVs with Excel)
- Data aggregation functions (participant_level, participant_frametype)

**Key Code Contributions:**

- `read_participant()` function (CSV reading with error handling)
- Participant exclusion logic (< 20 trials filter)
- RT cutoff calculation and filtering
- Demographic data merging pipeline

---

### Prateek Tiwari (2025201037)

**Responsibilities:**

- Statistical analysis implementation
- Hypothesis testing
- Bonferroni correction calculation and application
- Effect size calculations (Cohen's d for all comparisons)
- Descriptive statistics computation (means, SDs, CIs)
- Demographic analysis (4 exploratory tests D1-D4)

**Key Code Contributions:**

- `cohens_d()` function (pooled SD calculation)
- Welch t-test implementations (t1, t2, t3, t4)
- Bonferroni alpha adjustment
- Demographic tests (age/gender balance, moderators)
- Results summary tables

### Collaborative Work

All team members contributed to:

- Conceptual design and hypothesis formulation
- Experimental design understanding
- Interpretation of statistical findings
- Report writing and editing
- GitHub collaboration (commits, pull requests)
- Presentation preparation

---

## References

### Primary Sources

**Zacks, J. M., Speer, N. K., Swallow, K. M., Braver, T. S., & Reynolds, J. R. (2007).** Event perception: A mind-brain perspective. *Psychological Bulletin*, *133*(2), 273-293. https://doi.org/10.1037/0033-2909.133.2.273

- Original formulation of Event Segmentation Theory
- Describes predictive models and event boundaries
- Neural substrates of event segmentation

**Swallow, K. M., Zacks, J. M., & Abrams, R. A. (2009).** Event boundaries in perception affect memory encoding and updating. *Journal of Experimental Psychology: General*, *138*(2), 236-257. https://doi.org/10.1037/a0015631

- Demonstrates the Boundary Advantage Effect
- Shows enhanced memory at event boundaries vs middles
- Theoretical foundation for current study

---

### Methodological References

**Delacre, M., Lakens, D., & Leys, C. (2017).** Why psychologists should by default use Welch's t-test instead of Student's t-test. *International Review of Social Psychology*, *30*(1), 92-101. https://doi.org/10.5334/irsp.82

- Justification for Welch's t-test as default choice

**Hedge, C., Powell, G., & Sumner, P. (2018).** The reliability paradox: Why robust cognitive tasks do not produce reliable individual differences. *Behavior Research Methods*, *50*, 1166-1186. https://doi.org/10.3758/s13428-017-0935-1

- Discusses trial count requirements for reliable estimates

**Judd, C. M., Westfall, J., & Kenny, D. A. (2012).** Treating stimuli as a random factor in social psychology: A new and comprehensive solution to a pervasive but largely ignored problem. *Journal of Personality and Social Psychology*, *103*(1), 54-69. https://doi.org/10.1037/a0028347

- Compares aggregation vs mixed-effects approaches

**Wilson, G., Bryan, J., Cranston, K., Kitzes, J., Nederbragt, L., & Teal, T. K. (2017).** Good enough practices in scientific computing. *PLOS Computational Biology*, *13*(6), e1005510. https://doi.org/10.1371/journal.pcbi.1005510

- Best practices for reproducible research

---

## Contact

**Repository**: [GitHub Repository](https://github.com/Prateek-Tiwari10/BRSM_Project)

**Team Members:**

- Meet Ghelani (2025201096)
- Prateek Tiwari (2025201037)

**Course:** BRSM (Behavioural Research & Statistical Methods)
**Semester:** Spring 2026

---
