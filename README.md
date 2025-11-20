# German Credit Risk Modelling

This project represents my complete end-to-end workflow for modelling credit risk using the German Credit dataset. I explored the dataset, performed data preprocessing, trained several machine learning models, and calculated Probability of Default (PD) and Expected Loss (EL) to identify and evaluate customer credit behaviour and financial risk.

---

## 🎯 Project Objectives

Through this project, I aimed to answer three key questions:

1. **Which customer and financial characteristics influence good vs bad credit?**  
2. **Which machine learning model performs best for predicting credit risk?**  
3. **How can PD, EL, and risk segmentation be used to identify high-risk customers?**

---

## 📂 Dataset

The project uses the German Credit dataset stored as:

- `german_credit_data.csv`

It contains customer information such as:

- Age  
- Credit amount  
- Loan duration  
- Housing type  
- Saving account status  
- Checking account status  
- Purpose of credit  

These features form the basis of my analysis and model training.

---

📁 Project Structure

├── German_Credit_Risk_Modelling.ipynb          # Main notebook
├── german_credit_data.csv                      # Dataset
├── modeling.py                                 # ML model training code
├── risk_metrics.py                             # PD, EL, and risk metrics
├── README.md                                   # Documentation
└── data_preprocessing.py (optional)            # Preprocessing utilities


yaml
Copy code

---

## ⚙️ modeling.py

This file contains all machine learning model development and evaluation steps.

Models implemented:
- Logistic Regression  
- Random Forest  
- XGBoost  
- WOE Logistic Regression  

Metrics generated:
- Accuracy  
- ROC-AUC  
- Confusion Matrix  
- Classification Report  

It also includes automatic comparison logic to pick the best-performing model.

---

## 📊 risk_metrics.py

This file contains all functions related to financial risk calculations.

It includes:
- Probability of Default (PD) calculation  
- Expected Loss (EL = PD × LGD × EAD)  
- Identification of high EL customers  
- Creation of Low, Medium, and High risk segments  

These calculations help translate model outputs into actionable credit risk insights.

---

## 🔍 How My Project Answers the 3 Questions

### **1️⃣ Factors that influence credit risk**

In the notebook, I performed:
- Dataset shape, column, and unique value exploration  
- Distribution plots for Age, Credit Amount, Duration  
- Count plots for categorical variables (Sex, Job, Housing, Saving accounts, Checking account, Purpose)  
- Scatter plots and correlation heatmaps  

I also built a **synthetic risk score** using Credit Amount, Duration, savings, checking account status, housing, and purpose. This was converted into a binary Target (0 = good, 1 = bad) for modelling.

---

### **2️⃣ Comparing credit risk models**

I trained and evaluated four models:
- Logistic Regression  
- Random Forest  
- XGBoost  
- WOE Logistic Regression  

For each model, I computed:
- Accuracy  
- ROC-AUC  
- Confusion Matrix  
- Classification Report  

The model with the **highest AUC** was chosen as the best predictor of credit risk.

---

### **3️⃣ PD, EL, and identifying high-risk customers**

Using the best model:
- I computed **Probability of Default (PD)** for each customer  
- Then calculated **Expected Loss (EL = PD × LGD × EAD)**  
  - EAD = Credit Amount  
  - LGD = 45%  

I sorted customers by EL to identify those who pose the highest financial risk.  
I also created **Low / Medium / High** PD-based risk segments.

---

## ▶️ How to Run This Project

### **Step 1: Clone the repository**
git clone <your-repo-url>
cd <your-repo-folder>

markdown
Copy code

### **Step 2: Install all dependencies**
pip install -r requirements.txt

markdown
Copy code

### **Step 3: Run the notebook**
Open and execute:
- `German_Credit_Risk_Modelling.ipynb`

Make sure `german_credit_data.csv` is available in the same directory.

### **Step 4 (Optional): Import helper modules**
import modeling
import risk_metrics

yaml
Copy code

---

## 📦 Requirements

This project uses the following Python libraries:

- pandas  
- numpy  
- scikit-learn  
- xgboost  
- category_encoders  
- matplotlib  
- seaborn  

These can be listed in a `requirements.txt` file.

---

## 🚀 Future Enhancements

In future extensions of this project, I plan to:

- Add SHAP value explanations for model interpretability  
- Use GridSearchCV for model hyperparameter tuning  
- Build a Streamlit dashboard for PD & EL visualisation  
- Add calibration metrics and reliability diagrams for better model evaluation  

---
