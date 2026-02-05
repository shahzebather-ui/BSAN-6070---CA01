# BSAN-6070---CA01

# CA01 — House Price Prediction (EDA + Preprocessing + Collinearity)

This project completes CA01 using the Ames Housing training dataset. The notebook covers:
* Part 1: Data Understanding (EDA)
* Part 2: Preprocessing (missing values, outliers, encoding, scaling, health checks)
* Part 3: Post Processing (collinearity visualization + feature selection discussion only)

Notebook: `CA01_Shahzeb_Ather.ipynb`

---

## Dataset
Training data is loaded directly from GitHub:

`https://github.com/ArinB/MSBA-CA-Data/raw/main/CA01/house-price-train.csv`

Target variable: `SalePrice`

---

## What’s inside the notebook

### Part 1: Data Understanding (EDA)
* Univariate analysis (histograms, boxplots, bar charts)
* Bivariate analysis (scatter plots, boxplots, correlation heatmap)
* Multivariate analysis (selected-feature heatmap)
* Data Quality findings (missing values, outliers, skewness, initial collinearity signals)

### Part 2: Preprocessing
* Missing values
  * Categorical: filled with `"None"`
  * Numerical: imputed using median
* Outliers
  * Detected using boxplots and IQR logic
  * Handled using IQR capping (winsorization via `clip`)
* Encoding
  * One-hot encoding with `pd.get_dummies(drop_first=True)`
* Scaling
  * Standardization using `StandardScaler`
  * Applied to numerical features only (not the target)
* Stability & health checks
  * Missing values confirmed as 0
  * Dataset shape and data types checked

### Part 3: Collinearity (as required)
* Collinearity heatmap (numeric features only, masked triangle for readability)
* Identification of redundant feature pairs (example: `GrLivArea` vs `TotRmsAbvGrd`, `GarageCars` vs `GarageArea`)
* Discussion of potential feature removal to reduce multicollinearity

Note: The assignment scope is followed. No class imbalance handling and no additional dimensionality reduction beyond collinearity work.

---

## Tech Stack
* Python 3
* pandas, numpy
* matplotlib, seaborn
* scikit-learn

---

## How to Run

### Option 1: Jupyter Notebook
1. Clone/download this repo
2. Install dependencies
3. Open and run the notebook

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook
