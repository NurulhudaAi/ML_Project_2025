# High Salary Prediction using Artificial Neural Network (ANN)

This project predicts whether an individual earns a **high salary (1)** or **low salary (0)** based on demographic, educational, and occupational data.  
The goal is to compare several machine learning models and determine which performs best for salary classification.

---

## 1. Project Overview
- **Dataset size:** 20,900 census records  
- **Original features:** 18  
- **Processed variables:** 49 (after encoding and scaling)  
- **Target variable:** `label` → 1 = High Salary, 0 = Low Salary  

### Objective
To develop, train, and evaluate multiple machine learning models — including **Random Forest**, **XGboots**, **K-Nearest Neighbors (KNN)**, and **Artificial Neural Network (ANN)** — for accurate salary prediction.

---

## ⚙️ 2. Tools and Libraries
- **Languages:** Python 3.11  
- **Libraries:** `pandas`, `numpy`, `seaborn`, `matplotlib`, `scikit-learn`, `joblib`, `json`  
- **Environment:** Jupyter Notebook (Docker / VS Code)

---

## 3. Data Preparation
1. **Data Loading** – Read train, test, and live datasets  
2. **Handle Missing Values** – Mode for categorical, mean for numerical  
3. **Encoding** – Ordinal for `education`, One-Hot for `workclass`, `occupation`, `relationship`, `sex`  
4. **Feature Scaling** – Standardized numeric features (`StandardScaler`)  
5. **Integration** – Combined all processed data → final train/test/live CSVs  
6. **Final Output** – 49 ready-to-use modeling features

---

## 4. Model Development

### **Artificial Neural Network (ANN)**
Implemented using `sklearn.neural_network.MLPClassifier`.

| Parameter | Value |
|------------|--------|
| Hidden Layers | (20, 10) |
| Activation | Logistic (Sigmoid) |
| Solver | SGD |
| Learning Rate | 0.1 |
| Batch Size | 32 |
| Max Iterations | 1000 |
| Regularization (α) | 0.0 |
| Random State | 0 |

Models and configurations saved under `model/` folder (`model.joblib`, `config.json`).

---

## 5. Evaluation and Results

### **Model Performance (ANN)**
| Metric | Low Salary (0) | High Salary (1) | Weighted Avg |
|:-------|:---------------:|:---------------:|:-------------:|
| Precision | 0.872 | 0.804 | 0.843 |
| Recall | 0.854 | 0.827 | 0.842 |
| F1-Score | 0.863 | 0.815 | **0.843** |
| **Accuracy** |  | – | **0.842** |

> The ANN achieved **84.2% accuracy**, showing balanced precision and recall.

---

### **Model Comparison**
| Model | Accuracy | Precision | Recall | F1-Score | 
|:------|:----------:|:----------:|:----------:|:----------:|
| **KNN** | 0.79 | 0.73 | 0.78 | 0.75 | 
| **XGB** | 0.81 | 0.76 | 0.79 | 0.78 | 
| **Random Forest** | 0.81 | 0.78 | 0.79 | 0.75 | 
| **ANN (20,10)** | **0.84** | **0.80** | **0.82** | **0.81** |

> The ANN model outperformed both Logistic Regression and Random Forest in all major metrics, demonstrating better ability to learn complex relationships.

---

## 6. Discussion and Reflection

### **Trade-offs**
- ANN offers high accuracy but requires longer training and less interpretability.  
- Tree-based models (Random Forest) are easier to explain but slightly less accurate.  

### **Overfitting**
- Minimal risk observed; model reached the iteration limit, suggesting slight underfitting.  
- Future models can apply **early stopping** or **regularization** to improve convergence.

### **Limitations**
- Encoded categorical ranges (e.g., age-group 0–4) may oversimplify data.  
- Mean/mode imputation may introduce minor bias.  
- ANN lacks transparency for feature influence.

### **Improvements**
- Apply **grid search** for hyperparameter tuning.  
- Use **dropout** or **L2 regularization** to avoid overfitting.  
- Test deeper ANN architectures or **XGBoost**.  
- Add **SHAP/LIME** for interpretability.

---

## 8. Conclusion
The ANN achieved the **highest accuracy (84%)**, outperforming both Random Forest and Logistic Regression.  
It effectively classified high-income individuals using demographic and occupational features, though further tuning and interpretability improvements are recommended for real-world use.

---

**University:** Mae Fah Luang University  
**Course:** Machine Learning (Project)  
📅 **Date:** 9 November 2025
