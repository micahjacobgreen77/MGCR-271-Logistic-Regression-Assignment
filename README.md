# NFL Wins and Losses: Gaining Deeper Insights

A logistic regression analysis of the 2024 NFL regular season, built for MGCR 271 (BCom General Management, Desautels Faculty of Management, McGill University).

Authors: Shaya Behmard, Micah Green, Manan Malik, Bern Mebane, Ethan Riml, Andrew Yukhno  
Instructor: Gary Ng  
Submitted: November 25, 2025

## Overview

This project investigates which game-level and season-level factors help predict the probability of an NFL team winning a game. Using 544 team-game observations from the 2024 regular season (balanced: 272 wins / 272 losses), we built a logistic regression model and tested hypotheses on defensive performance, offensive efficiency, and roster stability.

## Data

- Source: https://www.pro-football-reference.com/
- Observations: 544 team-games (2024 regular season), balanced at 272 wins / 272 losses
- Dependent variable: Win = 1, Loss = 0

### Independent variables (summary)
- Points Allowed — Quantitative (game-level) — Expected negative relationship with winning
- Punts — Quantitative (game-level) — Expected negative relationship with winning
- Redzone Touchdown Rate — Quantitative (season-level) — Expected positive relationship with winning
- Total Injuries — Quantitative (season-level) — Expected negative relationship with winning
- Total Salary Cap — Quantitative (season-level) — Expected positive relationship with winning
- RB Receiving Yards Allowed — Quantitative (season-level) — Expected negative relationship with winning
- Sunday vs. Non-Sunday Game — Categorical (game-level) — Expected effect uncertain

Note: Points Scored was considered but excluded because it caused complete separation in the model.

## Hypotheses

1. Points Allowed: H₀: β₁ = 0 vs. Hₐ: β₁ < 0
2. Redzone Touchdown Rate: H₀: β₂ = 0 vs. Hₐ: β₂ > 0
3. Total Injuries: H₀: β₃ = 0 vs. Hₐ: β₃ < 0

All tests at α = 0.05.

## Methodology

- Exploratory data analysis: distributions, missingness, class balance, and visualizations.
- Preprocessing: missing-value handling, encoding categorical variables, and scaling when appropriate.
- Feature engineering and selection: candidate features were evaluated and weaker predictors removed.
- Modeling: logistic regression fitted incrementally (variables added one at a time), evaluated using AIC, McFadden R², and classification performance.
- Validation: model selection used statistical significance and goodness-of-fit criteria; the categorical schedule variable (Sunday) was retained per project requirements despite insignificance.

## Final model (selected predictors)

Independent variables: Injuries, Points Allowed, Punts, Redzone TD Rate, Sunday/Not

| Variable | Coefficient | p-value | Significant (α = 0.05) |
|---|---:|---:|:---:|
| Points Allowed | −0.190 | 0.000 | Yes |
| Punts | −0.253 | 0.000 | Yes |
| Redzone TD Rate | 5.503 | 0.001 | Yes |
| Injuries | −0.0026 | 0.287 | No |
| Sunday/Not | −0.019 | 0.957 | No |

## Model fit and accuracy
- McFadden R² = 0.330; Adjusted R² = 0.317
- Overall classification accuracy ≈ 77%

## Key findings
- Points Allowed is the strongest predictor: each additional point allowed reduces the odds of winning by roughly 17% (odds ratio ≈ 0.83), supporting Hypothesis 1.
- Redzone Touchdown Rate strongly increases win probability, supporting Hypothesis 2.
- Total Injuries is not statistically significant after controlling for in-game variables, so Hypothesis 3 is not supported; likely because injuries were measured at the season level.
- Sunday vs. non-Sunday scheduling shows no meaningful effect.

## Recommendations
Teams aiming to improve win percentage should prioritize:
1. Reducing points allowed (defensive improvements).
2. Sustaining drives and reducing punts.
3. Improving redzone touchdown conversion efficiency.

## Limitations & future work
- Several predictors are season-level constants repeated across games (e.g., injuries, salary cap), reducing within-team variation and limiting causal interpretation.
- Public data sources may introduce sampling or measurement bias.
- Future analyses could incorporate game-level injury reports, additional in-game metrics (turnover differential, yards per play, third-down conversions), non-linear models, or multi-season data for more stable estimates.

## Files included
- `Group_006_Project.pdf` — Full paper including data appendix with summary statistics, figures, and regression output (Figures 1–30)
- `data.xlsx` — Spreadsheet containing the dataset used for the analysis (please confirm the exact filename if it differs)

## Citation
Gifford, M., & Bayrak, T. (2023). A predictive analytics model for forecasting outcomes in the National Football League games using decision tree and logistic regression. Decision Analytics Journal, 8, 100296. https://doi.org/10.1016/j.dajour.2023.100296

## Contact
- Micah Green — GitHub: https://github.com/micahjacobgreen77
