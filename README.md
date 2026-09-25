# Multiple Linear Regression: House Price Analysis

## Project Overview

This project applies **multiple linear regression** to analyze the factors associated with house prices. The analysis was completed using Python and the **Home Value Insights** dataset from Kaggle.

The main goal was to understand how housing characteristics such as square footage, number of bathrooms, lot size, garage size, and neighborhood quality are associated with house prices.

> **Note:** The analysis identifies associations between variables and does not establish causal relationships.

## Research Question

**To what extent are house size, number of bathrooms, lot size, neighborhood quality, and garage size associated with house prices?**

## Dataset

The dataset contains **1,000 observations and 8 variables**.

### Variables

| Variable               | Description                                 |
| ---------------------- | ------------------------------------------- |
| `House_Price`          | Dependent variable representing house price |
| `Square_Footage`       | Size of the house in square feet            |
| `Num_Bedrooms`         | Number of bedrooms                          |
| `Num_Bathrooms`        | Number of bathrooms                         |
| `Year_Built`           | Year the house was built                    |
| `Lot_Size`             | Size of the property lot                    |
| `Garage_Size`          | Garage size/capacity                        |
| `Neighborhood_Quality` | Measure of neighborhood quality             |

**Dataset source:** Kaggle – Home Value Insights
https://www.kaggle.com/datasets/prokshitha/home-value-insights

## Tools and Technologies

* Python
* Pandas
* NumPy
* Statsmodels
* Matplotlib
* Seaborn
* Jupyter Notebook
* GitHub

## Models

### Model 1: Baseline Model

The first model used three predictors:

```text
House_Price ~ Square_Footage + Num_Bathrooms + Neighborhood_Quality
```

### Model 2: Refined Model

The second model added lot size and garage size:

```text
House_Price ~ Square_Footage + Num_Bathrooms + Neighborhood_Quality + Lot_Size + Garage_Size
```

The second model was compared with the baseline model using adjusted R², AIC, BIC, residual standard error, and coefficient stability.

## Key Results

The refined model produced:

| Metric                  |   Model 1 |   Model 2 |
| ----------------------- | --------: | --------: |
| R²                      |    0.9835 |    0.9890 |
| Adjusted R²             |    0.9834 |    0.9889 |
| AIC                     | 23,629.24 | 23,230.07 |
| BIC                     | 23,648.88 | 23,259.52 |
| Residual Standard Error | 32,652.86 | 26,718.35 |

The refined model explained approximately **98.9% of the variation in house prices in the sample**.

In the preferred model:

* `Square_Footage` had a positive and statistically significant association with house price.
* `Num_Bathrooms` had a positive and statistically significant association.
* `Lot_Size` had a positive and statistically significant association.
* `Garage_Size` had a positive and statistically significant association.
* `Neighborhood_Quality` was not statistically significant after controlling for the other variables.

## Regression Diagnostics

Several diagnostic checks were performed to evaluate the model.

### Residual Analysis

Residual plots were examined to assess linearity and possible heteroscedasticity.

### Multicollinearity

Variance Inflation Factor (VIF) was used to assess multicollinearity. The VIF values for the predictors were close to **1**, providing little evidence of problematic multicollinearity.

### Autocorrelation

The Durbin-Watson statistic was approximately **2.05**, which provided little evidence of first-order autocorrelation.

### Normality

A Q-Q plot and normality testing were used to assess the residual distribution. The residuals were not perfectly normally distributed, so this limitation was acknowledged in the analysis.

### Influential Observations

Cook's distance and leverage were examined to identify potentially influential observations. No extremely influential observation was identified.

## Model Refinement

A quadratic term for `Square_Footage` was also tested to investigate whether the relationship with house price was nonlinear.

The quadratic term was not statistically significant and did not meaningfully improve model fit. Therefore, the simpler linear model was retained.

## Project Structure

```text
multiple-linear-regression-house-prices/
│
├── data/
│   └── home_value_insights.csv
│
├── notebooks/
│   └── multiple_linear_regression.ipynb
│
├── figures/
│   ├── residuals_vs_fitted.png
│   ├── qq_plot.png
│   └── cooks_distance.png
│
├── report/
│   └── regression_report.pdf
│
├── README.md
└── requirements.txt
```

## How to Run the Project

1. Clone the repository:

```bash
git clone YOUR-GITHUB-REPOSITORY-URL
```

2. Navigate to the project folder:

```bash
cd multiple-linear-regression-house-prices
```

3. Install the required packages:

```bash
pip install pandas numpy statsmodels matplotlib seaborn jupyter
```

4. Open the Jupyter Notebook:

```bash
jupyter notebook
```

5. Open the notebook in the `notebooks` folder and run the cells.

## Learning Outcomes

Through this project, I practised:

* Building multiple linear regression models
* Interpreting regression coefficients
* Understanding R² and adjusted R²
* Comparing models using AIC and BIC
* Checking multicollinearity using VIF
* Checking residual behavior
* Using the Durbin-Watson statistic
* Identifying influential observations
* Testing a nonlinear relationship
* Understanding the difference between statistical significance and practical interpretation

## Limitations

The analysis is based on the variables available in the dataset. Other factors that may influence house prices were not included. Therefore, the model should not be interpreted as proving that any predictor causes changes in house prices.

## Author

**Joyce Jebichii**

Computer Science | Data Science & Machine Learning

This project was completed as part of my practical learning in **multiple linear regression and statistical modeling**.
