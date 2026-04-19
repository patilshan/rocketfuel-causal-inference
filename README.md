# 🎯 RocketFuel — Ad Effectiveness & Causal Inference

> Measuring the true causal impact of digital ad exposure on handbag purchase conversions using a randomized experiment with 588K+ users.

<p align="left">
  <img src="https://img.shields.io/badge/R-276DC3?style=flat-square&logo=r&logoColor=white" alt="R"/>
  <img src="https://img.shields.io/badge/dplyr-276DC3?style=flat-square" alt="dplyr"/>
  <img src="https://img.shields.io/badge/ggplot2-276DC3?style=flat-square" alt="ggplot2"/>
  <img src="https://img.shields.io/badge/lmtest-276DC3?style=flat-square" alt="lmtest"/>
  <img src="https://img.shields.io/badge/sandwich-276DC3?style=flat-square" alt="sandwich"/>
</p>

---

## Problem

TaskaBella, a luxury handbag retailer, ran a digital ad campaign through RocketFuel's DSP platform but needed to know whether the ads were actually *causing* purchases — or if the people who saw ads would have bought anyway. With 588K+ users split into treatment (shown real ads) and control (shown PSAs), the goal was to isolate the true causal effect of ad exposure on conversion.

## Approach

- Validated the experimental design by checking covariate balance (total impressions, day/hour of exposure) across treatment and control groups
- Computed conversion rates and constructed 95% confidence intervals for both groups
- Estimated the Average Treatment Effect (ATE) — the incremental lift from ad exposure
- Ran a regression-based ATE with heteroskedasticity-robust standard errors (HC3) controlling for impression volume, day, and hour
- Performed subgroup analysis across 10 impression-deciles to identify where ads had the strongest impact

## Key Results

| Metric | Detail |
|---|---|
| **Dataset** | 588,101 users — 96% treatment, 4% control |
| **Control Conversion Rate** | 2% |
| **Treatment Conversion Rate** | 3% |
| **Average Treatment Effect** | +1 percentage point (CI: 0.8%–1.2%), statistically significant |
| **Regression ATE (with controls)** | 0.76% lift (p < 0.001), robust to covariates |
| **Strongest Impact** | 9th and 10th impression deciles showed the largest treatment–control gap (5.2% vs 3.5% and 14.6% vs 8.4%) |

## How to Run

```bash
# Clone the repo
git clone https://github.com/patilshan/rocketfuel-causal-inference.git
cd rocketfuel-causal-inference

# Open in RStudio and run the analysis
# Required packages:
install.packages(c("readxl", "dplyr", "ggplot2", "psych", "lmtest", "sandwich", "knitr"))
```

## Project Structure

```
├── Rocketfuel.pdf       # Full analysis report with code, plots, and results
└── README.md
```

## What I Learned

- How to validate a randomized experiment by checking covariate balance before drawing causal conclusions
- The importance of using heteroskedasticity-robust standard errors when treatment and control groups have unequal variance
- That ad effectiveness is not uniform — subgroup analysis by impression decile revealed the causal effect concentrates among heavy-exposure users (top 20%)

---

<p align="center">
  <a href="https://github.com/patilshan">← Back to profile</a>
</p>
