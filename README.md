# 📊 AI-Powered Customer Churn Prediction & Cost-Aware Retention System

An end-to-end **Machine Learning + FastAPI + Streamlit + Power BI** solution for predicting customer churn, analyzing churn patterns, and generating cost-aware customer retention strategies.

The project combines **predictive analytics, business intelligence, REST APIs, and an interactive web application** into a single customer-retention workflow.

---

## 🚀 Live Demo

### 🌐 Streamlit Application

[Open Live Streamlit App](https://churn-api-c2apv35prmnxygyjxqf4jn.streamlit.app/?utm_source=chatgpt.com)

The application supports:

* 👤 Individual customer churn prediction
* 📂 Batch prediction using CSV files
* 📈 Churn probability and risk classification
* 🎯 Retention strategy recommendations
* 💰 Cost-aware discount recommendations
* 📥 Downloadable prediction results

---

# 📊 Power BI Dashboard

This repository also contains a **Power BI dashboard** for interactive business analysis of customer churn.

### Power BI File

```text
Churn_dashbord.pbix
```

The dashboard provides a business-oriented view of customer churn and helps identify patterns across different customer segments.

### 📈 Dashboard Analysis

The Power BI dashboard analyzes:

* **Overall Customer Churn**
* **Churn Rate**
* **Customer Demographics**
* **Tenure Distribution**
* **Contract Type**
* **Internet Service**
* **Monthly Charges**
* **Total Charges**
* **Paperless Billing**
* **Customer Segments**
* **Churn-related patterns and trends**

### 🎯 Business Use

The dashboard helps decision-makers answer questions such as:

* Which customer segments have the highest churn?
* How does churn vary by contract type?
* Which internet-service customers are more likely to churn?
* Does customer tenure influence churn?
* Which customer groups require greater retention attention?
* How are monthly charges associated with churn?

The Power BI dashboard complements the ML system by providing **historical and segment-level business insights**, while the prediction application provides **customer-level churn predictions and retention recommendations**.

---

# 🧠 Project Architecture

```text
                    Customer Data
                         │
            ┌────────────┴────────────┐
            │                         │
            ▼                         ▼
     Machine Learning            Power BI
     Churn Prediction            Dashboard
            │                         │
            ▼                         ▼
    Churn Probability          Business Analytics
            │
            ▼
     Risk Segmentation
            │
            ▼
   Retention Strategy Engine
            │
       ┌────┴────┐
       ▼         ▼
   Service    Targeted
 Intervention Discount
       │         │
       └────┬────┘
            ▼
    Business Decision
```

---

# 🎯 Problem Statement

Customer churn directly impacts recurring revenue and customer lifetime value.

A traditional churn prediction system only answers:

> **Which customers are likely to churn?**

This project goes one step further by answering:

> **Which customers are likely to churn, and what should the business do next?**

The system combines:

**Prediction → Risk Segmentation → Retention Action → Cost-Aware Intervention**

---

# 🤖 Machine Learning Model

The project uses **Logistic Regression** to predict customer churn probability.

### ML Workflow

```text
Raw Customer Data
        ↓
Data Cleaning
        ↓
Exploratory Data Analysis
        ↓
Feature Engineering
        ↓
Categorical Encoding
        ↓
Feature Scaling
        ↓
Train/Test Split
        ↓
Logistic Regression
        ↓
Model Evaluation
        ↓
Model Serialization
```

The trained model and scaler are stored as serialized files and used by the prediction API.

---

# 🎯 Churn Risk Segmentation

Customers are categorized based on predicted churn probability.

| Churn Probability | Risk Level   |
| ----------------- | ------------ |
| `< 30%`           | 🟢 Low       |
| `30% – <55%`      | 🟡 Medium    |
| `55% – <65%`      | 🟠 Elevated  |
| `65% – <80%`      | 🔴 High      |
| `≥ 80%`           | 🚨 Very High |

This allows retention teams to prioritize customers according to their predicted risk.

---

# 💰 Cost-Aware Retention Strategy

Instead of automatically giving discounts to every high-risk customer, the system uses a **tiered retention approach**.

```text
Low Risk
   ↓
No Financial Incentive

Medium Risk
   ↓
Engagement / Service Intervention

Elevated Risk
   ↓
Contract / Service Intervention

High Risk
   ↓
Targeted Discount + Retention Action

Very High Risk
   ↓
Priority Retention Intervention
```

The objective is to **avoid unnecessary discounts and reserve financial incentives for higher-risk customers where they are more justified**.

---

# 🖥️ Streamlit Application

The Streamlit application provides two prediction modes.

## 👤 Manual Prediction

Users can enter customer information including:

* Gender
* Senior Citizen
* Partner
* Dependents
* Tenure
* Internet Service
* Online Security
* Tech Support
* Contract
* Paperless Billing
* Monthly Charges

The application calculates estimated total charges and sends the customer data to the prediction API.

---

## 📂 Batch CSV Prediction

Users can upload multiple customer records through a CSV file.

The system generates prediction results for each customer, including:

* Churn prediction
* Churn probability
* Risk level
* Retention strategy
* Recommended action
* Recommended discount

The results can be downloaded as a CSV file.

---

# ⚡ FastAPI REST API

The trained ML model is exposed through a **FastAPI REST API**.

### Endpoint

```text
POST /predict
```

### Example Request

```json
{
  "tenure": 2,
  "Contract": 0,
  "InternetService": 2,
  "OnlineSecurity": 0,
  "TechSupport": 0,
  "MonthlyCharges": 95,
  "TotalCharges": 190,
  "PaperlessBilling": 1,
  "gender": 1,
  "SeniorCitizen": 1,
  "Partner": 0,
  "Dependents": 0
}
```

### Example Response

```json
{
  "prediction": 1,
  "churn_probability": 0.68
}
```

The Streamlit frontend consumes this API and converts the prediction into a business-oriented retention recommendation.

---

# 🔄 End-to-End Workflow

```text
Customer Data
      ↓
ML Churn Prediction
      ↓
Churn Probability
      ↓
Risk Classification
      ↓
Retention Strategy
      ↓
Cost-Aware Intervention
      ↓
Business Action
```

At the same time:

```text
Customer Data
      ↓
Power BI
      ↓
Interactive Churn Analysis
      ↓
Business Insights
```

This gives the project both:

**Predictive Intelligence + Business Intelligence**

---

# 🛠️ Tech Stack

### Machine Learning

* Python
* Pandas
* NumPy
* Scikit-learn
* Logistic Regression

### Backend

* FastAPI
* Uvicorn
* REST API

### Frontend

* Streamlit

### Business Intelligence

* Microsoft Power BI

### Deployment

* Streamlit Cloud
* Render

### Development

* Jupyter Notebook
* Git
* GitHub

---

# 📁 Project Structure

```text
Churn-Analysis/
│
├── app.py
├── api.py
│
├── Churn_model.pkl
├── Scaler.pkl
│
├── Churn_data_analysis_n_model.ipynb
├── Churn_dashbord.pbix
│
├── requirements.txt
├── runtime.txt
├── .gitignore
│
└── README.md
```

---

# ⚙️ Local Setup

### Clone Repository

```bash
git clone https://github.com/Abhay936/churn-analysis-powerbi-api-streamlit-app.git
cd churn-analysis-powerbi-api-streamlit-app
```

### Create Virtual Environment

```bash
python -m venv venv
```

### Activate Environment — Windows

```bash
venv\Scripts\activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run Streamlit

```bash
streamlit run app.py
```

---

# 📊 Project Components

| Component                  | Purpose                                      |
| -------------------------- | -------------------------------------------- |
| **Machine Learning Model** | Predict customer churn                       |
| **FastAPI**                | Serve ML predictions through REST API        |
| **Streamlit**              | Interactive prediction interface             |
| **CSV Batch Prediction**   | Predict churn for multiple customers         |
| **Retention Engine**       | Convert churn probability into actions       |
| **Power BI Dashboard**     | Analyze churn patterns and customer segments |
| **Cloud Deployment**       | Make the application accessible online       |

---

# 💼 Business Impact

The project is designed to move from:

```text
Prediction
```

to:

```text
Prediction
      ↓
Understanding
      ↓
Decision
      ↓
Action
```

Instead of treating churn prediction as an isolated ML problem, the system connects **machine learning predictions with business intelligence and customer retention decisions**.

---

# 🔮 Future Improvements

* Customer Lifetime Value prediction
* SHAP-based explainable AI
* Uplift modeling
* Retention ROI calculation
* A/B testing of retention offers
* Customer-level intervention effectiveness
* Model monitoring and drift detection
* Database integration
* Automated retention campaigns

---

# 👨‍💻 Author

**Abhay**

[GitHub Profile — Abhay936](https://github.com/Abhay936?utm_source=chatgpt.com)

---

## ⭐ Project Highlight

> **Predict churn → understand risk → recommend action → control retention cost.**

An end-to-end project combining **Machine Learning, FastAPI, Streamlit, Power BI, cloud deployment, and business-oriented customer retention analytics.**
