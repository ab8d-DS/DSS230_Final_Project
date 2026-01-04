# Instacart Reorder Prediction (User–Product)

## Project Goal
Predict whether a **(user, product)** pair will be **reordered in the user’s next order** (binary classification).
Predict days until next order for a user (regression).
## Dataset
This project uses the Instacart Market Basket Analysis dataset:
- `orders`
- `order_products__prior`
- `order_products__train`
- `products`, `aisles`, `departments`

## Approach
1. **Build candidate set**: all unique `(user_id, product_id)` pairs from prior orders (products a user has bought before).
2. **Time-aware split**: train on earlier orders, validate on later orders to avoid data leakage.
3. **Feature engineering**: create user-level and user–product level features (e.g., purchase counts, reorder rates, recency/gaps).
4. **Modeling**: baseline Logistic Regression + tuned models (SVM/KNN, etc.).
5. **Evaluation**: focus on **ROC-AUC** and **Average Precision (AP)** due to class imbalance. Also analyze precision/recall at different thresholds.
6. **Calibration**: calibrate LinearSVC and other models scores to probabilities using `CalibratedClassifierCV`, then evaluate with calibration curve and Brier score.

## Workload
-Abdullah: EDA,Preprocess,Merging,Feature engineering,outliers detection,Encoding comparison, classification task implemented logistic,KNN,LinearSVC,Decision Tree (files 01 and 02).

-Yasser: Regression Task -> linear,ridge,random forest.(file 04)

## Notes
-We finshed 30% ~ 40% from the project.
-Each one is expected to know and understand his (OWN WORK) i hope. 