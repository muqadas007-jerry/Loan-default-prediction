

# 💸 Loan Default Prediction

## 📝 Objective
Build a classification model to predict whether a loan applicant will default using the Lending Club dataset. The model helps lenders identify high-risk applicants and reduce potential defaults.

---

## 📂 Dataset
- **Source:** Lending Club Loan Dataset (or HMEQ dataset)
- **Target variable:** `BAD` (1 = default, 0 = non-default)
- **Size:** ~6,000 records
- **Features:** Financial data, credit history, loan purpose, etc.

---

## 🛠️ Steps Performed

### 1. Data Preprocessing
- Loaded the dataset using `pandas`
- Handled **missing values**:
  - **Numerical columns**: Imputed using **median**
  - **Categorical columns**: Imputed using **most frequent**
- Encoded categorical features using **Label Encoding**
- Scaled numerical features using **StandardScaler**

### 2. Train-Test Split
- Used `train_test_split()` to split the data into 80% training and 20% testing
- Stratified sampling to maintain class distribution

### 3. Dealing with Class Imbalance
- Initially trained without balancing
- Recommended use of **SMOTE** (Synthetic Minority Oversampling Technique) for improving recall

### 4. Model Training
- Trained a **Support Vector Machine (SVM)** model using `sklearn`
- (Optional: Also suggest trying **LightGBM** or **XGBoost** for better performance)

### 5. Evaluation Metrics
Used the following metrics for evaluation:
- **Precision**
- **Recall**
- **F1 Score**
- **Classification Report** from `sklearn.metrics`

---

## 📊 Results

| Metric      | Score |
|-------------|-------|
| Precision   | 0.98  |
| Recall      | 0.40  |
| F1 Score    | 0.57  |

> Note: The model is highly precise but has lower recall. This means it catches real defaulters well when it flags them, but it misses many.

---

## 📌 Recommendations
1. Use SMOTE or similar techniques to balance the dataset.
2. Try ensemble models like **LightGBM** or **Random Forest** for potentially better performance.
3. Use **SHAP values** to interpret important features influencing loan defaults.
4. Adjust classification threshold to optimize recall vs precision depending on business need.
5. Regularly retrain the model with updated data to keep up with financial trends.

---

