# World Stock Prices Statistical Analysis

This project analyzes global stock price trends using statistical inference and regression techniques. It leverages a real-world dataset from Kaggle, performing hypothesis testing, confidence interval estimation, correlation analysis, and both simple and multiple linear regression modeling to uncover insights from historical stock data.

##  Dataset

- **Source**: [Kaggle - World Stock Prices Dataset](https://www.kaggle.com/datasets/swaptr/complete-stock-market-dataset)
- **Features**:
  - Open, High, Low, Close prices
  - Volume, Dividends, Stock Splits
  - Categorical data: Brand Name, Ticker, Industry Tag, Country

##  Key Steps & Techniques

### Data Preprocessing
- Checked and confirmed no missing values
- Ordinal encoding applied to categorical columns (`Brand_Name`, `Ticker`, `Industry_Tag`, `Country`)

### Sampling & Hypothesis Testing
- Random sampling (100, 200 samples) to estimate means and proportions
- Calculated z-scores and confidence intervals for:
  - `Open`, `Close`, `High`, `Low`, `Volume`, `Dividends`
- One-sample and two-sample tests for both means and proportions

### Correlation Analysis
- Pearson correlation coefficients computed between `Close` price and:
  - `Volume`, `Ticker`, `Brand Name`, `Industry Tag`, `Country`, `High`, `Low`

### Regression Modeling
- **Simple Linear Regression**:
  - Modeled `Close` as a function of individual features like `Open`, `High`, `Volume`, etc.
  - Visualized regression lines and residual plots

- **Multiple Linear Regression**:
  - Three feature groups evaluated:
    - [Open, High, Low]
    - [Volume, Dividends, Ticker]
    - [Brand Name, Industry Tag, Country]
  - R² and adjusted R² values compared for each model

## Results & Observations

| Feature Set                             | Adjusted R² |
|----------------------------------------|-------------|
| `Open`, `High`, `Low`                  | 0.9999      |
| `Volume`, `Dividends`, `Ticker`        | 0.0313      |
| `Brand_Name`, `Industry_Tag`, `Country`| 0.0125      |

- High correlation observed between `Close` and `High` price (almost 1)
- Categorical features showed weak linear correlation
- `High`, `Low`, and `Open` are strong predictors for `Close`

##  Requirements

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
