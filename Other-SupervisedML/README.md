# 🧪 CONVERSION RATE CHALLENGE

## 🎯 Project Goals
**Build a predictive model that determines whether a user will subscribe to a newsletter based on minimal behavioral and demographic data.**

---

## 📁 Getting Started with the Data

Located in the `src` folder:

  - conversion_data_train.csv # Training data (with target 'converted')
  - conversion_data_test.csv # Test data (without 'converted' column)
  - conversion_data_test_labels.csv # True labels for test data (for evaluation after submission)


---

## 📊 Exploratory Data Analysis (EDA)

✅ Data description  
✅ Summary statistics  
✅ Outlier detection and handling  
✅ Visualizations (distributions, correlations, etc.)  
✅ Preprocessing (encoding, scaling)

---

## 🧪 Baseline Model – Logistic Regression

✅ Use a template model using `total_pages_visited` as the sole feature  
✅ Train a logistic regression  
✅ Evaluate performance using **F1 Score**  
✅ Make predictions on the test set  
✅ Submit predictions to TA

---

## 📈 Model Improvement

✅ Incorporate more features (`age`, `country`, `source`, `new_user`, etc.)  
✅ Re-train and re-evaluate using **F1 Score**  
✅ Improve preprocessing where necessary  
✅ Generate and submit new predictions

---

## 🔍 Results Analysis & Interpretation

✅ Use model coefficients to interpret feature importance and model behavior  
✅ Discuss limitations and possible biases

---

## 📌 Recommendations

- Try more advanced models (Random Forest, XGBoost)
- Use hyperparameter tuning (GridSearchCV)
- Test with class balancing techniques (e.g., SMOTE, weighted loss)
- Consider feature interactions and polynomial terms

---

## 👤 Author

Project by **Andriana**  
GitHub: [https://github.com/Andrianiniaina/0-Machine-Learning-Projects]
