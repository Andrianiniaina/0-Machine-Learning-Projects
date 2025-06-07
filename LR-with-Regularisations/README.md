# 🛍️ Walmart Sales Forecasting

## 🎯 Project Overview
This project aims to predict weekly Walmart store sales using historical sales data and various associated features.
The goal is to create a robust regression model capable of accurately forecasting sales, thereby facilitating inventory management, staffing, and other business decisions.
## 📁 Data Source
The dataset used for this project is "Walmart_Store_sales.csv," which contains historical sales data from various Walmart stores.
---

## 🔍 Features
The dataset includes the following features:
- **Store**: Store ID.
- **Date**: Sales week.
- **Weekly_Sales**: Weekly sales of the store in question (target variable). - **Holiday_Indicator**: Indicates whether the week is a holiday (1) or not (0).
- **Temperature**: Average temperature in the region.
- **Fuel_Price**: Cost of fuel in the region.
- **CPI**: Consumer Price Index.
- **Unemployment**: Unemployment rate.
---

## 📊 Exploratory Data Analysis (EDA)
The initial EDA revealed:
- **Number of rows**: 42,157
- **Number of columns**: 8
- Basic statistics were generated for all features to understand their distributions and ranges. ---
## 📋 Data Preprocessing
The following steps were performed to prepare the data for modeling:
### ✅ Feature Engineering: Date: "year", "month", "day", and "day of the week"
### ✅ Outlier Removal for the "Temperature", "Fuel Price", "CPI", and "Unemployment" columns
### ✅ Categorical and Numerical Feature Management
---

## 🛠️ Modeling

The problem was formulated as a regression task.
The data was divided into an 80% training set and a 20% test set.

Three different linear regression models were trained and evaluated:

### ✅ Linear Regression (Reference)
A standard linear regression model was used as a reference. - **R² score on the training set**: 0.9820
- **R² score on the test set**: 0.9432
- **MSE on the training set**: 278,922,042.85
- **MSE on the test set**: 847,126,380.08

**Interpretation**:
The model performs well on the training data, but shows a noticeable drop-off on the test set, indicating potential overfitting.

### ✅ Ridge Regression
Ridge regression was applied to correct for overfitting. - **Hyperparameter Tuning**: GridSearchCV
- **Best Hyperparameters**: `{'alpha': 20}`
- **Best Score (Cross-Validation)**: 0.9526
- **R² Score on the Training Set**: 0.9527
- **R² Score on the Test Set**: 0.9520
- **MSE on the Training Set**: 842,506,009.06
- **MSE on the Test Set**: 699,576,146.99

**Interpretation**:
Ridge Regularization significantly reduced overfitting, resulting in a generalized model that performed significantly better than the baseline model.

### ✅ ElasticNet Regression
ElasticNet Regression was also used as a regularization technique. - **Hyperparameter Tuning**: `GridSearchCV`
- **Best Hyperparameters**: `{'alpha': 0.01, 'l1_ratio': 0.2}`
- **R² Score on the Training Set**: 0.9527
- **R² Score on the Test Set**: 0.9525
- **MSE on the Training Set**: 843,267,235.12
- **MSE on the Test Set**: 698,124,195.96

**Interpretation**:
ElasticNet performed very similarly to Ridge, offering a good balance between L1 and L2 regularizations. ---

## 📌 Model Comparison and Results

Comparison of coefficients and performance indicators of the three models:
A bar chart comparing the model coefficients is also available in the notebook, illustrating the impact of regularization on feature importance and magnitude.
---

## 🏆 Conclusion

Both **Ridge** and **ElasticNet** regularizations successfully corrected the overfitting observed in the baseline linear regression model. ElasticNet showed a slight advantage in terms of R² score and a slightly lower mean squared error on the test set, making it a strong candidate for predicting Walmart's weekly sales. The use of regularization is essential to improve the model's generalization on unobserved data. ---
## 🔧 Libraries Used
- `pandas`
- `numpy`
- `sklearn`
- `Pipeline`
- `ColumnTransformer`
- `OneHotEncoder`
- `StandardScaler`
- `SimpleImputer`
- `train_test_split`
- `LinearRegression`
- `Ridge`
- `ElasticNet`
- `cross_val_score`
- `GridSearchCV`
- `r2_score`
- `mean_squared_error`
- `joblib` (for caching)
- `seaborn` (for visualization)

## 👤 Author

Project by **Andriana**  
🔗 GitHub: [https://github.com/Andrianiniaina/0-Machine-Learning-Projects]
