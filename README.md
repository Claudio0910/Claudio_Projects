# Assignment Overview

This repository contains notes on the MFE Financial Econometrics Practical Work 1 (2025-26). The exercise includes both a written report and code submission. Below is a concise breakdown of requirements and tasks extracted from the provided brief.

## General Instructions
- Group project: teams of three or four; teams of two require approval and teams of one or more than four are not permitted. Group members should be listed in alphabetical order without indicating the group number.
- Submission deadlines: upload the report by 12 noon, 16th January 2026; the autograder code is due by 12 noon, 16th January 2026.
- Report length: limit to 6 pages or 2,000 words (excluding a cover sheet or bibliography). Figures, equations, and explanatory text together must not exceed 8 pages/2,000 words.

## Part 1 – Portfolio Analysis
1. Build tracking portfolios for Value and Momentum across six prescribed model types using out-of-sample regression, then compare out-of-sample R-squared values.
2. Evaluate how different data subsets (full series 1940–1994, 1940–1979, 1980–1994) affect estimated coefficients beta and out-of-sample R-squared. Discuss how changing data periods influences results.
3. Assess whether any estimator produces negative expected factor returns; interpret economic implications.
4. Compare performance when tracking the long side versus the full long/short portfolio of each factor; report whether results differ materially.
5. Identify which two or three best models/components stand out overall; consider whether combining techniques could improve outcomes.

## Notes on Tracking Regressions
- Portfolio return being tracked: R_k,t.
- Regressors: asset returns R_j,t; tracking model R_k,t = sum(beta_j * R_j,t) + epsilon_t.

## Part 2 – Code Requirements (Autograder)
Provide a Python file with only function definitions and imports (no top-level execution) implementing:

1. oos_r_squared(yhat, ybar, mu): compute out-of-sample R-squared for forecasts yhat versus actuals y and average ybar. Return a scalar out-of-sample R-squared.
   - Inputs: yhat (pandas Series aligned with y), ybar (pandas Series of same shape, e.g., forecast of ybar), and mu (scalar mean y).

2. oos_residuals(y, x, beta, first, last): compute residuals over an index range [first, last] when forecasting y with regressors x and coefficients beta. Indexing is by integers matching y and x.
   - Inputs: y (pandas Series with DatetimeIndex), x (pandas DataFrame with same index as y), beta (list/array of betas with an intercept as the last element), first/last (inclusive string dates).
   - Residuals should be sliced by date range and returned as a Series.

## Submission Packaging
- Autograder submission must be a .py file—Jupyter notebooks are not accepted. The file should contain only imports and function definitions; no analysis code or execution.
- Example structure: place functions after imports, leaving a minimal stub that can be imported without side effects.

