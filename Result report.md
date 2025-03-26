## Report Template (reports/final_report.md)

```markdown
# Sales Prediction Analysis Report

## 1. Business Understanding
Predicting sales to optimize advertising budgets across multiple channels.

## 2. Data Overview
- Sources: Advertising spend data + sales records
- Time period: Jan 2018-Dec 2022
- Features:
  - TV ad spend
  - Radio ad spend
  - Digital marketing budget
  - Seasonal indicators
  - Previous sales

## 3. Methodology

### Data Preparation
- Merged multiple data sources
- Handled missing values
- Created time-based features

### Feature Engineering
- Developed:
  - Rolling sales averages
  - Ad spend ratios
  - Seasonality indicators

### Models Evaluated
1. Linear Regression
2. Decision Tree
3. Random Forest
4. XGBoost
5. Time Series ARIMA

## 4. Results

| Model          | R² Score | MAE   | RMSE  |
|----------------|----------|-------|-------|
| Linear Reg     | 0.85     | 1.20  | 1.55  |
| Random Forest  | 0.89     | 0.95  | 1.25  |
| XGBoost        | 0.92     | 0.82  | 1.10  |
| ARIMA          | 0.81     | 1.35  | 1.70  |

## 5. Key Insights
- Digital advertising shows highest ROI
- TV ads have delayed impact (2-week lag)
- Seasonal peaks in Q4 account for 30% of annual sales

## 6. Recommendations
- Reallocate 15% of radio budget to digital
- Increase Q4 ad spend by 20%
- Implement dynamic pricing during peak seasons
