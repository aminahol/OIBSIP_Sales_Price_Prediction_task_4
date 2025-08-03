# Sales Prediction 
Oasis InfoByte Internship | Task 5

A machine learning project that predicts sales based on advertising spend across TV, Radio, and Newspaper channels using multiple regression algorithms.

## Objectives

- Analyze the relationship between advertising spend and sales performance
- Compare multiple machine learning models for sales prediction accuracy
- Identify which advertising channels contribute most effectively to sales
- Determine the optimal model for sales forecasting

## Dataset

The advertising dataset contains 200 samples with 4 features:
- **TV**: Advertising spend on TV (thousands of dollars)
- **Radio**: Advertising spend on Radio (thousands of dollars)  
- **Newspaper**: Advertising spend on Newspaper (thousands of dollars)
- **Sales**: Sales revenue (thousands of units) - Target variable

No missing values or duplicates were found. Sales distribution shows slight positive skewness (0.41), with most values clustered toward the lower end.

## Methodology

### Data Exploration
- Conducted correlation analysis revealing TV advertising has the strongest relationship with sales
- Generated pairplots to visualize linear and non-linear relationships between features and target
- Performed outlier detection using box plots - no significant outliers identified

### Model Selection Rationale
Three regression models were chosen to capture different relationship patterns:

**Linear Regression**: Baseline model assuming linear relationships between advertising spend and sales.

**Random Forest**: Ensemble method using multiple decision trees to capture non-linear patterns and feature interactions without overfitting.

**XGBoost**: Gradient boosting algorithm that builds models sequentially, correcting errors from previous models while applying regularization.

### Evaluation Strategy
- Used 80-20 train-test split with fixed random state for reproducible results
- Evaluated models using three complementary metrics:
  - RMSE: Penalizes larger prediction errors more heavily
  - R² Score: Measures proportion of variance explained by the model
  - MAE: Provides interpretable average prediction error

## Results

| Model | RMSE | R² Score | MAE |
|-------|------|----------|-----|
| Linear Regression | 1.78 | 0.90 | 1.46 |
| Random Forest | 0.77 | 0.98 | 0.62 |
| XGBoost | 0.82 | 0.98 | 0.70 |

### Key Findings
- Random Forest achieved the best overall performance with lowest RMSE (0.77) and MAE (0.62)
- Both ensemble methods significantly outperformed Linear Regression, reducing RMSE by over 55%
- High R² scores (0.98) for ensemble methods indicate they capture 98% of sales variance
- TV advertising shows strongest correlation with sales, followed by Radio, while Newspaper has minimal impact

## Conclusion

The analysis demonstrates that ensemble methods (Random Forest and XGBoost) are substantially more effective than linear approaches for sales prediction in this advertising context. The superior performance of these models suggests non-linear relationships and feature interactions play important roles in determining sales outcomes.

From a business perspective, the results indicate TV advertising provides the highest return on investment, while newspaper advertising shows limited effectiveness. The high accuracy achieved by ensemble models (R² = 0.98) makes them reliable tools for sales forecasting and advertising budget optimization.

The Random Forest model is recommended for deployment due to its combination of highest accuracy, interpretability, and robust performance across all evaluation metrics.
