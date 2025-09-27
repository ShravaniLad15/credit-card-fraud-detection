# Credit Card Fraud Detection using Logistic Regression

This project applies **Logistic Regression** to detect fraudulent transactions in credit card payments using the [Kaggle Credit Card Fraud Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud).  

The dataset is highly **imbalanced**, with only **0.17% fraud cases**, making this a challenging and realistic ML problem in the financial domain.  

---

## 📊 Dataset
- **Source**: [Kaggle – Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)  
- **Size**: 284,807 transactions  
- **Fraud cases**: 492 (~0.17%)  
- **Features**:  
  - `V1`–`V28`: Anonymized features from PCA  
  - `Amount` and `Time`: Transaction details  
  - `Class`: Target variable (0 = Legit, 1 = Fraud)  

---

## 🛠️ Steps Followed
1. **Data Exploration**
   - Checked shape, columns, null values (none found)
   - Verified class imbalance (majority legit transactions)
2. **Preprocessing**
   - Scaled `Amount` and `Time` features
   - Retained anonymized PCA features
3. **Train/Test Split**
   - 80/20 split with `stratify=y` to preserve class balance
4. **Modeling**
   - Logistic Regression (`class_weight='balanced'`)
   - Predicted fraud probability & applied threshold
5. **Evaluation**
   - Confusion Matrix
   - Classification Report (precision, recall, F1-score)
   - ROC-AUC Score
   - ROC Curve & Precision-Recall Curve visualization  

---

## 📈 Results
- **ROC-AUC Score:** ~0.97  
- **Recall for Fraudulent Cases (Class 1):** ~92%  
- **Accuracy:** ~98% (not meaningful due to imbalance)  

**Interpretation:**  
The model was able to identify the majority of fraudulent transactions (high recall), while maintaining strong overall ROC-AUC performance.  
Precision remains low, which is a common challenge in highly imbalanced datasets.  
