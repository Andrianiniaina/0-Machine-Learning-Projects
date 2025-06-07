# Walmart Sales Prediction

## Project Overview

This project focuses on predicting weekly sales for Walmart stores using historical sales data and various related features. The goal is to build a robust regression model that can accurately forecast sales, helping with inventory management, staffing, and other business decisions.

## Table of Contents

- Project Overview
- Data Source
- Features
- Exploratory Data Analysis (EDA)
- Data Preprocessing
  - Handling Missing Value
  - Feature Engineering
  - Outlier Removal
  - Categorical and Numerical Feature Management
- Modeling
  - Linear Regression (Baseline)
  - Ridge Regression
  - ElasticNet Regression
- Model Comparison and Results
- Conclusion
- How to Run the Project
- Libraries Used

---

## Data Source

The dataset used for this project is `Walmart_Store_sales.csv`, containing historical sales data for various Walmart stores.

---

## Features

The dataset includes the following features:

- **Store**: The store ID.
- **Date**: The week of sales.
- **Weekly_Sales**: Weekly sales for the given store (target variable).
- **Holiday_Flag**: Indicates whether the week is a holiday week (1) or not (0).
- **Temperature**: Average temperature in the region.
- **Fuel_Price**: Cost of fuel in the region.
- **CPI**: Consumer Price Index.
- **Unemployment**: Unemployment rate.

---

## Exploratory Data Analysis (EDA)

Initial EDA revealed:

- **Number of rows**: 42157
- **Number of columns**: 8
- No missing values in the target variable (`Weekly_Sales`) after initial cleanup.
- Basic statistics were generated for all features to understand their distributions and ranges.

---

## Data Preprocessing

The following steps were performed to prepare the data for modeling:

### Handling Missing Values

- Rows with missing `Weekly_Sales` were dropped.
- For other features, a `SimpleImputer` with a `most_frequent` strategy was used within the preprocessing pipeline.

### Feature Engineering

- The `Date` column was transformed into numerical features: `year`, `month`, `day`, and `weekday`. The original `Date` column was then dropped.

### Outlier Removal

Outliers for numerical features (`Temperature`, `Fuel_Price`, `CPI`, `Unemployment`) were removed using the **3-standard deviation rule**. Values outside the range $[X̄ - 3σ, X̄ + 3σ]$ were considered outliers.

### Categorical and Numerical Feature Management

- **Categorical features**: `Store`, `Holiday_Flag`
  - Preprocessed using `SimpleImputer(strategy='most_frequent')` followed by `OneHotEncoder(handle_unknown='ignore', drop='first')`.
- **Numerical features**: `Temperature`, `Fuel_Price`, `CPI`, `Unemployment`, `year`, `month`, `day`, `weekday`
  - Preprocessed using `SimpleImputer(strategy='most_frequent')` followed by `StandardScaler()`.
- A `ColumnTransformer` was used to apply these transformations.
- The entire preprocessing flow was encapsulated in a `Pipeline` with `joblib.Memory` for caching.

---

## Modeling

The problem was framed as a regression task. The data was split into an 80% training set and a 20% test set. Three different linear regression models were trained and evaluated:

### Linear Regression (Baseline)

- A standard `LinearRegression` model was used as a baseline.
- **R² score on training set**: 0.9820
- **R² score on test set**: 0.9432
- **MSE on training set**: 278,922,042.85
- **MSE on test set**: 847,126,380.08
- **Interpretation**: The model shows good performance on the training data but a noticeable drop on the test set, indicating potential overfitting.

### Ridge Regression

- `Ridge` regression was applied to address overfitting.
- **Hyperparameter tuning**: `GridSearchCV` was used to find the optimal `alpha` value.
  - **Best hyperparameters**: `{'alpha': 20}`
  - **Best score (cross-validation)**: 0.9526
- **R² score on training set**: 0.9527
- **R² score on test set**: 0.9520
- **MSE on training set**: 842,506,009.06
- **MSE on test set**: 699,576,146.99
- **Interpretation**: Ridge regularization significantly reduced overfitting, leading to a much better generalized model compared to the baseline.

### ElasticNet Regression

- `ElasticNet` regression was also employed as a regularization technique.
- **Hyperparameter tuning**: `GridSearchCV` was used to find the optimal `alpha` and `l1_ratio`.
  - **Best hyperparameters**: `{'alpha': 0.01, 'l1_ratio': 0.2}`
- **R² score on training set**: 0.9527
- **R² score on test set**: 0.9525
- **MSE on training set**: 843,267,235.12
- **MSE on test set**: 698,124,195.96
- **Interpretation**: ElasticNet performed very similarly to Ridge, offering a good balance between L1 and L2 regularization.

---

## Model Comparison and Results

A comparison of the coefficients and performance metrics for all three models:

| Metric         | Linear Regression (No Regularization) | Ridge Regression | ElasticNet Regression |
|----------------|---------------------------------------|------------------|-----------------------|
| **R² (Train)** | 0.9820                                | 0.9527           | 0.9527                |
| **R² (Test)** | 0.9432                                | 0.9520           | 0.9525                |
| **MSE (Train)**| 278,922,042.85                        | 842,506,009.06   | 843,267,235.12        |
| **MSE (Test)** | 847,126,380.08                        | 699,576,146.99   | 698,124,195.96        |

A bar chart comparing the coefficients of the models is also available in the notebook, demonstrating how regularization impacts feature importance and magnitude.

---

## Conclusion

Both **Ridge** and **ElasticNet** regularization successfully addressed the overfitting observed in the baseline linear regression model. ElasticNet showed a slight edge in test R² score and slightly lower MSE on the test set, making it a strong contender for predicting Walmart weekly sales. The use of regularization is crucial for improving model generalization on unseen data.

---

## How to Run the Project

1.  **Clone the repository**:
    ```bash
    git clone <repository_url>
    cd <repository_name>
    ```
2.  **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```
    (You'll need to create a `requirements.txt` file containing the libraries listed below.)
3.  **Run the Jupyter Notebook**:
    ```bash
    jupyter notebook walmart_sales_prediction.ipynb
    ```
    (Assuming your notebook is named `walmart_sales_prediction.ipynb` and placed in the root of your project.)

---

## Libraries Used

-   `pandas` (for data manipulation)
-   `numpy` (for numerical operations)
-   `sklearn` (for preprocessing, modeling, and evaluation)
    -   `Pipeline`
    -   `ColumnTransformer`
    -   `OneHotEncoder`
    -   `StandardScaler`
    -   `SimpleImputer`
    -   `train_test_split`
    -   `LinearRegression`
    -   `Ridge`
    -   `ElasticNet`
    -   `cross_val_score`
    -   `GridSearchCV`
    -   `r2_score`
    -   `mean_squared_error`
-   `joblib` (for caching)
-   `seaborn` (for data visualization)
-   `matplotlib.pyplot` (for plotting)
```

## 👤 Author

Project by **Andriana**  
🔗 GitHub: [https://github.com/Andrianiniaina/0-Machine-Learning-Projects]
