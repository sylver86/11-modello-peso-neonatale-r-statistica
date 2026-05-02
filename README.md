# NeoStat — Modello Predittivo del Peso Neonatale (Statistica Inferenziale in R)

![R](https://img.shields.io/badge/R-4.x-276DC3?logo=r&logoColor=white)
![RMarkdown](https://img.shields.io/badge/RMarkdown-Report-blue)
![R2](https://img.shields.io/badge/R²-~0.62-brightgreen)
![Statistics](https://img.shields.io/badge/Statistics-Inferenziale-orange)

## Panoramica

Studio statistico inferenziale end-to-end sul peso neonatale alla nascita su un campione di 2.500 neonati da tre ospedali. Il modello di regressione multipla raggiunge R²≈0.62 con 4 predittori chiave, confermando l'effetto statisticamente significativo del fumo materno (p<0.001). Include diagnostica completa dei residui, rilevamento outlier (Cook's distance) e validazione predittiva su casi reali.

Metodologia statistica rigorosa applicabile in healthcare analytics, pharmaceutical research, qualsiasi contesto dove la significatività statistica e la spiegabilità del modello sono requisiti di business.

## Valore Enterprise

| Settore / Azienda | Rilevanza |
|-------------------|-----------|
| Healthcare & Pharma | Clinical analytics, modelli predittivi su dati sanitari |
| IT Consulting (Accenture, NTT Data) | Statistica inferenziale per regulated industries |
| Ricerca & Accademia | Metodologia statistica rigorosa: ipotesi, diagnostica |
| Insurance | Attuariale: modellazione di fattori di rischio |

## Risultati del Modello

| Modello | R² | Adj. R² | Predittori chiave |
|---------|-----|---------|------------------|
| **Regressione Lineare Multipla (selezionato)** | **~0.62** | **~0.61** | gestazione, fumo materno, BMI, n° gravidanze |

**Findings principali:**
- L'età gestazionale è il predittore più forte (coefficiente standardizzato più alto)
- Il fumo materno ha effetto negativo statisticamente significativo (p<0.001)
- Termini di interazione non-lineari tra età gestazionale e BMI migliorano il fit
- 6 outlier influenti identificati e analizzati via Cook's distance

## Workflow Completo

| Fase | Metodo | Strumento R |
|------|--------|-------------|
| EDA | Correlazioni, boxplot, scatter | ggplot2, dplyr |
| Test ipotesi | t-test, ANOVA per gruppo (sesso, ospedale, fumo) | stats |
| Selezione modello | Stepwise AIC/BIC | MASS |
| Diagnostica residui | Shapiro-Wilk, Breusch-Pagan | lmtest, car |
| Outlier | Cook's distance, leverage plot | car |
| Predizione | Validazione su casi reali (settimana 39) | stats |

## Dataset

| Variabile | Tipo | Descrizione |
|-----------|------|-------------|
| `gestazione` | numeric | Età gestazionale (settimane) |
| `peso` | numeric | **Target** — peso alla nascita (grammi) |
| `fumo` | factor | Fumo materno (sì/no) |
| `bmi_madre` | numeric | BMI materno |
| `n_gravidanze` | integer | Numero di gravidanze |
| `sesso` | factor | Sesso del neonato |
| `ospedale` | factor | Ospedale di provenienza |

## Setup

```r
install.packages(c("ggplot2", "dplyr", "lmtest", "car", "knitr", "rmarkdown"))
rmarkdown::render("Progetto previsione neonati.Rmd")
```

## Stack Tecnologico

`R 4.x` · `ggplot2` · `dplyr` · `lmtest` · `car` · `RMarkdown`

---

---

# NeoStat — Neonatal Weight Prediction (Inferential Statistics in R) 🇬🇧

![R](https://img.shields.io/badge/R-4.x-276DC3?logo=r&logoColor=white)
![R2](https://img.shields.io/badge/R²-~0.62-brightgreen)

## Overview

End-to-end inferential statistical study on birth weight across 2,500 newborns from three hospitals. Multiple linear regression achieves R²≈0.62 with 4 key predictors, confirming a statistically significant negative effect of maternal smoking (p<0.001). Includes full residual diagnostics, outlier detection (Cook's distance), and predictive validation on real cases.

## Model Results

| Model | R² | Adj. R² | Key predictors |
|-------|----|---------|----------------|
| **Multiple Linear Regression** | **~0.62** | **~0.61** | gestational age, maternal smoking, BMI, pregnancies |

**Key findings:**
- Gestational age is the strongest predictor (highest standardised coefficient)
- Maternal smoking has a statistically significant negative effect (p<0.001)
- Non-linear interaction terms between gestational age and BMI improved model fit
- 6 influential outliers identified and analysed via Cook's distance

## Workflow

| Phase | Method | R Tool |
|-------|--------|--------|
| EDA | Correlations, boxplots, scatter | ggplot2, dplyr |
| Hypothesis testing | t-test, ANOVA by group (sex, hospital, smoking) | stats |
| Model selection | Stepwise AIC/BIC | MASS |
| Residual diagnostics | Shapiro-Wilk, Breusch-Pagan | lmtest, car |
| Outlier detection | Cook's distance, leverage plots | car |
| Prediction | Validation on real cases (week 39) | stats |

## Setup

```r
install.packages(c("ggplot2", "dplyr", "lmtest", "car", "knitr", "rmarkdown"))
rmarkdown::render("Progetto previsione neonati.Rmd")
```

## Technologies

`R 4.x` · `ggplot2` · `dplyr` · `lmtest` · `car` · `RMarkdown`
