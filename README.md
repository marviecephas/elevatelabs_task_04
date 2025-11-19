# Task 4: Classification with Logistic Regression (Breast Cancer Prediction)

### Objective
To build a binary classifier using **Logistic Regression** to predict cell status (Malignant/Benign), focusing on classification evaluation metrics like Precision, Recall, and ROC-AUC.

### Dataset & Preprocessing
* **Dataset:** Breast Cancer Wisconsin Dataset (Predicting 'diagnosis').
* **Cleaning:** Irrelevant columns (`id`, `Unnamed: 32`) were successfully dropped. The dataset confirmed no major null values.
* **Target Encoding:** The categorical target variable (`diagnosis`) was mapped to numerical values (**Malignant = 1**, **Benign = 0**). This is mandatory for Scikit-learn classification models.
* **Feature Scaling:** All 30 predictor features were standardized using **`StandardScaler`**. This is critical for Logistic Regression (which uses Gradient Descent) to ensure fast convergence and stable, comparable coefficients.

---

### Model Evaluation: Focusing on Classification Metrics

In medical diagnosis, **Recall** is often the most critical metric, as missing a malignant case (False Negative) is more costly than a false alarm (False Positive).

| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **Precision** | **0.9762** | Out of all predictions the model flagged as **Malignant (1)**, this is the percentage that were actually correct. (Measures confidence in positive predictions). |
| **Recall (Sensitivity)** | **0.9535** | Out of all **actual Malignant (1)** cases, this is the percentage the model correctly identified (**low False Negatives**). |
| **F1-Score** | **0.9647** | The harmonic mean of Precision and Recall, providing a single balanced measure of the model's performance. |
| **ROC-AUC** | **0.9974** | Measures the model's overall ability to distinguish between the two classes across all possible thresholds. A score near **1.0 is excellent**. |

#### **Confusion Matrix Analysis (Example Structure)**

The **Confusion Matrix** visually summarizes the model's prediction breakdown:
* **True Positives (TP):** 70 (Malignant cases correctly identified)
* **False Negatives (FN):** 1 (Malignant cases that were missed—**Critical Error Type**)
* **False Positives (FP):** 2 (Benign cases incorrectly flagged as Malignant)

---

### Conceptual Insights

* **Model Function:** Logistic Regression used the **Sigmoid function** to convert the linear output into a probability between 0 and 1, making the model interpretable as a classifier. 
* **Imbalance & Risk:** Due to the high-stakes nature of medical diagnosis, the focus on achieving high **Recall** is the primary success factor, ensuring few Malignant cases are missed.
