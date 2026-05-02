# Neonatal Weight Prediction — Inferential Statistics in R

![R](https://img.shields.io/badge/R-4.x-276DC3?logo=r&logoColor=white)
![RMarkdown](https://img.shields.io/badge/RMarkdown-Report-blue)
![Statistics](https://img.shields.io/badge/Statistics-Inferential-orange)

## Overview

Statistical study and predictive modelling of **neonatal birth weight** using a dataset of 2,500 newborns from three hospitals.
The analysis investigates the influence of maternal and clinical variables on newborn weight, with particular focus on the effect of **maternal smoking** — combining rigorous inferential testing with a multiple linear regression model.

The work demonstrates end-to-end statistical reasoning: from EDA and hypothesis testing through to model selection, residual diagnostics, and real-world prediction validation.

---

## Results

| Model | R² | Adjusted R² | Key predictors |
|-------|----|-------------|----------------|
| Multiple Linear Regression (selected) | ~0.62 | ~0.61 | Gestational age, maternal smoking, BMI, number of pregnancies |

**Key findings:**
- Gestational age is the strongest predictor of birth weight (highest standardised coefficient)
- Maternal smoking has a statistically significant negative effect on birth weight (p < 0.001)
- Nonlinear interaction terms between gestational age and BMI improved model fit
- 6 influential outliers identified and analysed via Cook's distance

**Validation prediction:**
Model estimated neonatal weight for a third pregnancy at week 39 (no ultrasound data) with error within clinical acceptable range.

---

## Project Workflow

1. **Data import** — `neonati.csv` (2,500 records, 12+ variables)
2. **Descriptive analysis** — central tendency, dispersion, distribution by sex and hospital
3. **EDA** — correlation matrix, boxplots, scatter plots (ggplot2)
4. **Hypothesis testing** — t-tests and ANOVA on weight differences by group (sex, hospital, smoking)
5. **Model building** — stepwise multiple linear regression with AIC/BIC selection criteria
6. **Residual diagnostics** — normality (Shapiro-Wilk), homoscedasticity (Breusch-Pagan), influential cases (Cook's distance)
7. **Prediction** — real-world validation on unseen cases

---

## Dataset

| Variable | Type | Description |
|----------|------|-------------|
| `eta_madre` | numeric | Mother's age |
| `n_gravidanze` | integer | Number of pregnancies |
| `fumo` | factor | Maternal smoking (yes/no) |
| `gestazione` | numeric | Gestational age (weeks) |
| `peso` | numeric | **Target** — birth weight (grams) |
| `lunghezza` | numeric | Birth length (cm) |
| `cranio` | numeric | Head circumference (cm) |
| `tipo_parto` | factor | Delivery type |
| `ospedale` | factor | Hospital ID |
| `sesso` | factor | Newborn sex |

---

## Setup

```r
# Install required packages
install.packages(c("ggplot2", "dplyr", "lmtest", "car", "knitr", "rmarkdown"))

# Render the full report
rmarkdown::render("Progetto previsione neonati.Rmd")
```

Output available as PDF and HTML report in the repository.

---

## Technologies

`R 4.x` · `ggplot2` · `dplyr` · `lmtest` · `car` · `RMarkdown`
