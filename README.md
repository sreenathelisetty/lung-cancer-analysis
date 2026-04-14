# NCCTG Lung Cancer Survival Analysis

Survival analysis of the NCCTG Lung Cancer dataset (228 patients) using Python and the `lifelines` library.

## Dataset

The dataset comes from the North Central Cancer Treatment Group and is built into R's `survival` package. It is loaded directly from [Rdatasets](https://vincentarelbundock.github.io/Rdatasets/) — no manual download needed.

| Variable | Description |
|---|---|
| `time` | Survival time (days) |
| `status` | 0 = censored, 1 = dead |
| `age` | Age in years |
| `sex` | 1 = Male, 2 = Female |
| `ph.ecog` | ECOG performance score (0-3) |
| `ph.karno` | Karnofsky score rated by physician |
| `pat.karno` | Karnofsky score rated by patient |
| `meal.cal` | Calories consumed at meals |
| `wt.loss` | Weight loss in last 6 months (lbs) |

## Analysis

The notebook covers 8 sections:

1. **Data loading and cleaning** - recoding, missing value assessment
2. **Descriptive statistics** - survival rates and age distribution by sex and ECOG
3. **Kaplan-Meier curves** - overall, by sex, by ECOG score with log-rank tests
4. **Cox Proportional-Hazards model** - univariate and multivariable HRs, forest plot
5. **Parametric survival models** - Weibull AFT, Log-normal AFT compared by AIC
6. **Competing risks** - cumulative incidence functions, cause-specific Cox model
7. **Predicted survival curves** - four contrasting patient profiles
8. **Recommendations** - clinical and statistical recommendations with interpretation

## Key Findings

- Overall median survival: **310 days (~10 months)**
- Females survive significantly longer than males (log-rank p = 0.001)
- ECOG score is the strongest predictor of death (HR = 2.1 per point, p < 0.005)
- Best parametric fit: **Weibull AFT** (lowest AIC)
- Predicted 1-year survival ranges from **77%** (young female, ECOG 0) to **15%** (old male, ECOG 2)

## Plots

| File | Description |
|---|---|
| `plot_01_age_distribution.png` | Age distribution by sex + ECOG bar chart |
| `plot_02_kaplan_meier.png` | KM curves by sex and ECOG |
| `plot_03_cox_forest.png` | Cox model forest plot |
| `plot_04_parametric_models.png` | Parametric models vs KM |
| `plot_05_competing_risks.png` | Cumulative incidence by sex and event type |
| `plot_06_predicted_survival.png` | Predicted survival by patient profile |

## Requirements

```
lifelines
pandas
numpy
matplotlib
seaborn
scipy
```

Install with:

```bash
pip install lifelines pandas numpy matplotlib seaborn scipy
```

## Usage

Open and run the notebook:

```bash
jupyter lab lung_cancer_analysis.ipynb
```
