# CIE 2 – Activity 1: Multiple Linear Regression (AD3304)

Course: Regression and Classification Algorithms, T.Y. B.Tech AI \& DS, Sem V, 2026–27
Author: Ayush Rajgure | Roll No.: AD3304 | AI \& DS, Div C 
https://github.com/complexiota

## What this activity does

Explains and forecasts diabetes disease progression from baseline measurements using multiple linear regression, including a hand-calculated normal-equation worksheet verified against scikit-learn.

## Dataset

Diabetes dataset (442 patients, 9 numeric features used: age, bmi, bp, s1–s6; target = progression after 1 year). `sex` excluded on purpose.
Source: Efron, Hastie, Johnstone \& Tibshirani (2004), *Least Angle Regression*, Annals of Statistics. https://www4.stat.ncsu.edu/\~boos/var.select/diabetes.html (loaded with `sklearn.datasets.load\_diabetes(scaled=False)`).

## Work completed

Data checks, scatter plots and correlation heatmap, manual X, XᵀX, Xᵀy and solved b (7 observations, bmi and bp), library verification, 80:20 split (353 / 89), mean and single-feature baselines, multiple regression, standardised coefficients, residual plots, VIF, one improvement (drop s1 and s2), new prediction, decision log and limitations.

## Key results (test set, n = 89)

|Model|RMSE|R²|Adj R²|
|-|-|-|-|
|Mean baseline|73.2|-0.01|-0.01|
|Single feature (bmi)|63.7|0.23|0.22|
|Multiple (9 features)|54.7|0.44|0.37|
|Reduced (7 features)|54.1|0.45|0.40|

s1 (VIF ≈ 55) and s2 (≈ 36) are highly collinear; dropping them keeps performance. Not for individual treatment decisions.

## Reproduce

`pip install numpy pandas scikit-learn matplotlib seaborn`, then run the notebook top to bottom (seed 42).

