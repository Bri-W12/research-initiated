# An analysis of Anscombe data

## Goal

Analyze data set and visualize it, and see what we want to do next with it.

## Implementation 

-Need to analyze data in anscombe_quartet.tsv
-First, look at the data and generate descriptive statistics 
-Second, create a Juptyr Light notebook in which you will generate plots.
-Propose the types of plots that you would like to generate.
-Save this proposal to the end of this file and let me look at it. 
-I will need to approve this plan and tell you to go ahead before we actually do anything. Please append the plan to the end of this file.

---

## Descriptive Statistics (computed from anscombe_quartet.tsv)

All four datasets share nearly identical summary statistics — this is the famous "trick" of the Anscombe quartet.

| Dataset | n  | x̄      | sx     | ȳ      | sy     | Regression line       | R²     |
|---------|----|--------|--------|--------|--------|-----------------------|--------|
| I       | 11 | 9.0000 | 3.3166 | 7.5009 | 2.0316 | y = 0.5001x + 3.0001 | 0.6665 |
| II      | 11 | 9.0000 | 3.3166 | 7.5009 | 2.0317 | y = 0.5000x + 3.0009 | 0.6662 |
| III     | 11 | 9.0000 | 3.3166 | 7.5000 | 2.0304 | y = 0.4997x + 3.0025 | 0.6663 |
| IV      | 11 | 9.0000 | 3.3166 | 7.5009 | 2.0306 | y = 0.4999x + 3.0017 | 0.6667 |

Means, standard deviations, and regression lines are essentially identical across all four datasets.

---

## Proposed Plots

Three plot types are proposed for the Jupytext Light notebook:

### 1. Scatter plots — 2×2 grid, one panel per dataset
The core Anscombe visualization. Shows raw (x, y) points so the structural differences become immediately visible:
- Dataset I: roughly linear with natural scatter
- Dataset II: clear curved (quadratic) relationship — a linear fit is the wrong model
- Dataset III: near-perfect linear relationship except for one high-leverage outlier
- Dataset IV: all x values are 8 except one extreme point (x=19); that single outlier drives the entire regression

### 2. Scatter plots with regression line overlaid — 2×2 grid
Same as above but with the fitted OLS line drawn through each panel. Makes concrete that the same line fits all four panels despite their very different shapes.

### 3. Residual plots — 2×2 grid
Residuals (y − ŷ) plotted against x for each dataset, a standard model-diagnostic tool:
- Dataset I: roughly random residuals, confirming a linear model is adequate
- Dataset II: clear curved residual pattern, flagging model misspecification
- Dataset III: one extreme residual stands out, flagging the outlier
- Dataset IV: residuals are nearly constant except at x=19, showing leverage

Together these three plot types tell the complete story of why visualisation must accompany statistical summaries.

**Awaiting your approval to proceed with creating the Jupytext Light notebook.**

## Iteration 1

-go ahead and execute your plan
-save it in a Jupyter Notebook that I can start in this VS Code instance
-explain to me how to start a Jupyter Notebook so I can validate your results

## Iteration 2
-make it so that the plots show up as images and are saved as .png files 