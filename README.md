# Anscombe Quartet Analysis

An exploratory analysis of the [Anscombe quartet](https://en.wikipedia.org/wiki/Anscombe%27s_quartet) — four datasets that share nearly identical summary statistics but look completely different when visualised.

## What we did

### 1. Loaded and described the data
The raw data is in `anscombe_quartet.tsv` (four datasets labelled I–IV, each with 11 (x, y) pairs).

We computed descriptive statistics for each dataset:

| Dataset | n  | x̄      | sx     | ȳ      | sy     | Regression line       | R²     |
|---------|----|--------|--------|--------|--------|-----------------------|--------|
| I       | 11 | 9.0000 | 3.3166 | 7.5009 | 2.0316 | y = 0.5001x + 3.0001 | 0.6665 |
| II      | 11 | 9.0000 | 3.3166 | 7.5009 | 2.0317 | y = 0.5000x + 3.0009 | 0.6662 |
| III     | 11 | 9.0000 | 3.3166 | 7.5000 | 2.0304 | y = 0.4997x + 3.0025 | 0.6663 |
| IV      | 11 | 9.0000 | 3.3166 | 7.5009 | 2.0306 | y = 0.4999x + 3.0017 | 0.6667 |

All four datasets have virtually identical means, standard deviations, and linear regression lines — yet they are structurally very different.

### 2. Created three visualisations (Jupyter notebook)

All plots are in `anscombe_analysis.ipynb` and saved as PNGs.

**Plot 1 — Scatter plots** (`plot1_scatter.png`)
Raw (x, y) points for each dataset side by side. The structural differences become immediately visible:
- Dataset I: roughly linear with natural scatter
- Dataset II: clearly curved (quadratic) relationship
- Dataset III: near-perfect linear fit except one high-leverage outlier
- Dataset IV: all x values are 8 except one extreme point (x=19) that drives the entire regression

**Plot 2 — Scatter plots with regression lines** (`plot2_regression.png`)
The same OLS line overlaid on each panel, making concrete that identical regression lines can describe very different data.

**Plot 3 — Residual plots** (`plot3_residuals.png`)
Residuals (y − ŷ) vs x for each dataset — a standard model-diagnostic tool that flags curvature, outliers, and leverage that the regression line alone hides.

## Files

| File | Description |
|------|-------------|
| `anscombe_quartet.tsv` | Raw data (tab-separated) |
| `anscombe_analysis.ipynb` | Jupyter notebook with all analysis and plots |
| `plan.md` | Iterative planning notes |
| `plot1_scatter.png` | Scatter plots (2×2 grid) |
| `plot2_regression.png` | Scatter plots with regression lines (2×2 grid) |
| `plot3_residuals.png` | Residual plots (2×2 grid) |

## Running the notebook

1. Open `anscombe_analysis.ipynb` in VS Code
2. Select a Python 3 kernel
3. Click **Run All**

Dependencies: `pandas`, `numpy`, `matplotlib`, `scipy`
