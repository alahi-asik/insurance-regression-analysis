# Medical Insurance Charges Prediction

## Project Overview
A multiple linear regression model to predict individual annual medical insurance 
charges using demographic and health features from the Medical Cost Personal Dataset.

**Dataset:** insurance.csv (1,338 samples, 7 columns)  
**Target Variable:** `charges` — annual medical insurance cost (USD)  
**Environment:** Python 3.9+, Google Colab

---

## Project Structure
- `insurance_regression_analysis_Asik.ipynb` — main notebook
- `Project_Proposal_Asik.pdf` — project proposal
- `Summative_Report_Asik.pdf` — project summary report
- `requirements.txt` — package dependencies
- `insurance.csv` — dataset

---

## How to Run
1. Open `insurance_regression_analysis_Asik.ipynb` in Google Colab
2. Upload `insurance.csv` to the root of my Google Drive (not inside any folder)
3. Run all cells top to bottom

---

## Methodology
1. **Data Quality Check** — missing values, data types, outlier inspection
2. **Exploratory Data Analysis** — 4 visualizations with rationale:
   - Histogram of insurance charges (right-skewed distribution)
   - Scatter plot of age vs. charges coloured by smoker status
   - Scatter plot of BMI vs. charges
   - Correlation heatmap of all encoded features
3. **Data Preparation** — Label encoding of categorical variables (sex, smoker, region)
4. **Model Training** — Multiple Linear Regression with 80/20 train/test split
5. **Model Evaluation** — R², RMSE, MAE, Actual vs Predicted plot, Residual plot
6. **Conclusions** — interpretation of coefficients and model limitations

---

## Results
| Metric | Value |
|---|---|
| R² (Test Set) | 0.7833 |
| RMSE (Test Set) | $5,799.59 |
| MAE | reported in notebook |

**Key finding:** Smoker status is by far the most influential predictor, adding 
approximately **$23,648** to predicted charges — far outweighing the effect of 
age, BMI, or region.

---

## Key Findings
- The model explains **78% of the variance** in insurance charges
- `smoker` is the strongest predictor by a large margin
- **Age** contributes approximately **$257** per additional year
- **BMI** adds approximately **$336** per unit increase
- `sex` and `region` have minimal impact on charges
- The model performs well for lower charges but underestimates high-cost cases

---

## Limitations
- Linear regression assumes a linear relationship between features and charges
- The right-skewed target variable violates normality assumptions slightly
- Label encoding of categorical variables assumes ordinal relationships

---

## Future Work
- Apply log-transformation to charges to reduce skewness
- Explore non-linear models (Random Forest, XGBoost)
- Use one-hot encoding instead of label encoding for categorical variables

---

## Requirements
pip install numpy pandas matplotlib seaborn scikit-learn scipy
