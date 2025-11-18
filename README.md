# Week_5_AI-Development-Workflow-Assignment
Understanding the AI Development Workflow
# Student Dropout & Hospital Readmission Prediction Project

This repository contains a complete end-to-end Machine Learning workflow covering two domains:
1. **Education** – Predicting student dropout risk.
2. **Healthcare** – Predicting 30-day patient readmission risk.

The project includes: problem definitions, data strategies, preprocessing pipelines, model development, evaluation, deployment considerations, ethics, critical thinking, and a full workflow diagram.

---

## 📌 Part 1: Short Answer Questions

### **1. Problem Definition (Student Dropout Prediction)**
**Objective:** Predict which students are at high risk of dropping out during the next academic year.

**Objectives (3):**
- Identify risk students at least 3 months before disengagement.
- Provide actionable insights for counselors.
- Reduce dropout rate by 10% within one year.

**Stakeholders:**
- School administrators & counselors.
- Students and families.

**KPI:**
- **Precision@Top10%** — optimizes limited intervention resources.

---

### **2. Data Collection & Preprocessing**
**Data Sources:**
1. Student Information System (SIS)
2. LMS logs

**Potential Bias:**
- Sampling bias due to unequal internet access.

**Preprocessing Steps:**
- Missing data handling
- Scaling & encoding
- Temporal feature engineering

---

### **3. Model Development**
**Model Choice:** Gradient Boosted Trees (XGBoost/LightGBM)

**Reasons:**
- Strong performance on tabular data
- Handles missing values
- Explainable via SHAP

**Hyperparameters:**
- Learning rate
- Max depth / number of leaves

---

### **4. Evaluation & Deployment**
**Metrics:**
- Precision@K
- Recall

**Concept Drift Monitoring:**
- Track feature distributions
- Track rolling performance metrics

**Deployment Challenge:**
- Secure, scalable integration with SIS/LMS

---

## 📌 Part 2: Case Study — Hospital Readmission Prediction

### **Problem Scope**
Predict whether a discharged patient will be readmitted within 30 days.

**Objectives:**
- Identify high-risk patients
- Provide interpretable risk factors
- Reduce readmission by 15%

**Stakeholders:**
- Clinicians, discharge planners, patients, administrators

---

### **Data Strategy**
**Data Sources:**
- EHR (labs, vitals, ICD codes, meds)
- Demographics & social factors

**Ethical Concerns:**
- Patient privacy (HIPAA)
- Fairness & bias in underserved groups

**Preprocessing Pipeline:**
- Secure ingestion, de-identification
- Cohort & label creation
- Time-window features
- Encoding & normalization
- Missingness indicators
- Fairness audit

---

### **Model Development**
**Model:** Gradient Boosted Trees (XGBoost/LightGBM)

**Confusion Matrix (Example):**
|                | Predicted + | Predicted - |
|----------------|-------------|-------------|
| Actual +       | 80 (TP)     | 30 (FN)     |
| Actual -       | 20 (FP)     | 370 (TN)    |

**Precision = 80%**
**Recall ≈ 72.7%**

---

### **Deployment**
**Steps:**
1. Pilot & clinician feedback
2. API + model serving via Docker/Kubernetes
3. Integrate with EMR via FHIR
4. UI dashboard
5. Shadow-mode testing
6. Security & access control
7. Monitoring + retraining pipeline
8. CI/CD + rollback

**Regulatory Compliance:**
- Data minimization
- Encryption
- RBAC
- BAAs
- Audit trails

---

### **Optimization**
**Solution to Overfitting:**
- Early stopping + L2 regularization

---

## 📌 Part 3: Critical Thinking

### **Ethics & Bias**
**Impact of Biased Data:**
- Misdiagnosis risk for underrepresented groups
- Unequal treatment recommendations
- Lower trust and worse patient outcomes

**Bias Mitigation Strategy:**
- Fairness audits + rebalancing (oversampling/weights)

---

### **Trade-offs**
**Interpretability vs Accuracy:**
- Simple models = interpretable but less accurate
- Complex models = more accurate but harder to trust

**Limited Compute Constraints:**
- Prefer lightweight models (LR, decision trees, small GBDT)

---

## 📌 Part 4: Reflection

### **Challenges:**
Data preprocessing was the hardest due to messy, incomplete, and sensitive healthcare data.

### **Improvements:**
- More clinical expert collaboration
- More time for fairness testing
- Larger datasets
- Advanced hyperparameter optimization

---

## 📌 AI Workflow Diagram

Use the prompt below in any diagram-generating tool:

```
Create a horizontal AI development workflow diagram with the following stages:

1. **Start**
2. **Problem Definition**
   - Define objectives
   - Identify stakeholders
3. **Data Strategy**
   - Identify data sources
   - Address privacy and ethical issues
4. **Data Preprocessing**
   - Cleaning
   - Handle missing values
   - Feature engineering
   - Train/validation/test split
5. **Model Development**
   - Model selection
   - Training
   - Hyperparameter tuning
   - Confusion matrix
6. **Model Evaluation**
   - Accuracy
   - Precision
   - Recall
   - Bias assessment
7. **Deployment**
   - Integration into hospital systems
   - Monitoring for concept drift
   - Regulatory compliance
8. **Continuous Improvement**
   - Error analysis
   - Retraining
   - Optimization
9. **End**

Use rounded rectangles, connectors, and subtle colors for each section.
```

---

## 📚 References
- CRISP-DM Framework Documentation
- Hospital AI Deployment Guidelines (2024)
- Google AI Fairness Research (2023)
- PLP Academy Lecture Notes

---

## 🔧 How to Use This Repo
- Clone the repository
- Review the documentation
- Use workflow prompts to recreate diagrams
- Adapt the pipelines for your own ML projects

---
