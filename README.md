# 📈 Social Media Ad Performance Analysis & Conversion Prediction

[![Python](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/)
[![Power BI](https://img.shields.io/badge/PowerBI-Dashboard-yellow.svg)](https://app.powerbi.com/view?r=YOUR-DASHBOARD-LINK)
[![Machine Learning](https://img.shields.io/badge/ML-CatBoost%20%7C%20XGBoost-green.svg)]()
[![EDA](https://img.shields.io/badge/Data-EDA-orange.svg)]()
[![Status](https://img.shields.io/badge/Status-Completed-success.svg)]()
[![GitHub](https://img.shields.io/badge/Repo-GitHub-black.svg)]([https://github.com/YOUR-USERNAME/YOUR-REPO](https://github.com/Rishabh1108ch))
[![Notebook](https://img.shields.io/badge/View-Notebook-blueviolet.svg)](https://github.com/YOUR-USERNAME/YOUR-REPO/blob/main/Analysis.ipynb)
[![LinkedIn](https://img.shields.io/badge/Connect-LinkedIn-blue.svg)](https://www.linkedin.com/in/rishabh-chandrakar)


---

## 🧠 Overview
This project analyzes a large-scale **social media advertising dataset** to uncover insights into ad performance and predict **user conversion events** (Click, Purchase, Share, Comment, Like).  
It combines **Exploratory Data Analysis (EDA)** with **Predictive Machine Learning** to optimize ad targeting, audience segmentation, and budget allocation.

## 🖼️ Power BI Dashboard Preview

![Power BI Dashboard - Social Media Ads Performance](https://github.com/Rishabh1108ch/Social_media_Ads_Performance_Gradient-Boosting_Analysis/blob/main/Ads_performance_analysis_PowerBI.png))


---

## 🎯 Objective
Explore and analyze a comprehensive dataset (400,000+ ad events, 10,000 users) to:
- Identify high-converting demographics and ad formats  
- Evaluate platform performance (Facebook vs Instagram)  
- Build a predictive model to forecast user conversion likelihood  

---

## 🗂️ Datasets Used
| Dataset | Description | Records |
|----------|--------------|----------|
| `users.csv` | User demographic information | 10,000 |
| `ads.csv` | Ad metadata (type, platform, target_gender) | 200 |
| `ad_events.csv` | Log of all ad interactions (click, like, share, purchase) | 400,000 |
| `campaigns.csv` | Campaign details (budget, start/end dates) | 50 |

---

## ⚙️ Process & Methodology

### 1️⃣ Data Loading and Inspection
- Loaded all datasets with **Pandas** and verified structure using `.info()` and `.head()`.  
- Checked dataset integrity and ensured consistent keys across tables (`user_id`, `ad_id`, `campaign_id`).

### 2️⃣ Data Preprocessing & Cleaning
- Converted time columns (`timestamp`, `start_date`, `end_date`) into `datetime` format.  
- Verified **zero missing values** in essential columns.  
- Normalized categorical data for merging.

### 3️⃣ Data Merging
- Merged all four datasets via **left joins** → `merged_df` with **403,967 records**.  
- Unified structure connecting user demographics, ad specifics, and event data.

### 4️⃣ Exploratory Data Analysis (EDA)
- **Event distribution:**  
  - Impressions ≈ 85% (≈339,812)  
  - Clicks ≈ 10% (≈40,079)  
  - High-value events (Purchase, Share, Comment, Like): 20,109  

- **Platform insights:**  
  - Facebook: 127 ads  
  - Instagram: 73 ads  
  - Stories → most common ad type (64 ads)

- **User demographics:**  
  - Age range: 16–65 (mean ≈ 27.7 years)

- **Campaign budgets:**  
  - Range: $7,918 – $98,905  
  - Mean ≈ $50,718

---

## 🧩 Feature Engineering
Created new features for improved model performance:
- **Temporal:** `hour`, `day_of_month`, `month`, `day_of_week`, `is_weekend`  
- **Campaign-relative:** `days_since_campaign_start`, `days_until_campaign_end`  
- **Target variable:** `is_conversion` → `1` for {Click, Purchase, Share, Comment, Like}, else `0`

Key insights:
- Age groups **35–44** and **45–54** showed higher conversion rates.  
- **Video** and **Carousel** ads produced stronger engagement.  
- Platform-level conversion metrics visualized in Power BI.

---

## 🤖 Predictive Modeling: Conversion Forecasting

**Goal:** Predict whether a user event leads to a conversion (`is_conversion = 1`).

### 🔹 Baseline Model — Logistic Regression
- Features: `user_age`, `user_gender`, `target_gender`, `day_of_week`, `ad_platform`
- **Accuracy:** 84.93%

### 🔹 Advanced Models — Gradient Boosting Comparison
| Model | AUC-ROC | Accuracy | Precision | Recall | F1-score |
|--------|---------:|----------:|-----------:|--------:|----------:|
| **CatBoost Classifier** | **0.864** | **0.932** | 0.518 | 0.669 | 0.583 |
| XGBoost Classifier | 0.852 | 0.931 | 0.511 | 0.635 | 0.566 |
| Gradient Boosting | 0.849 | 0.930 | 0.509 | 0.618 | 0.558 |

**✅ Best Model:** CatBoost Classifier — best AUC-ROC (0.864) and accuracy (93.2%)  
**Metric used:** AUC-ROC for model discrimination performance.

---

## 📊 Power BI Dashboard Highlights
*(Screenshots / Links Placeholder)*  
- Conversion rate by **platform** and **ad type**  
- Top-performing **audience age groups**  
- Budget vs. conversion efficiency visual  
- Daily event trend and interaction heatmap  

---

## 💡 Key Takeaways
- Demonstrated **end-to-end Data Science workflow**: from wrangling to modeling.  
- Achieved **93.2% accuracy** in predicting user conversions.  
- Generated actionable insights to guide **marketing strategy** and **ROAS optimization**.  
- Visualized conversion trends and campaign KPIs with **Power BI**.  

---

## 🧰 Tech Stack
**Languages & Tools:** Python (Pandas, NumPy, Scikit-learn, CatBoost, XGBoost)  
**Visualization:** Matplotlib, Seaborn, Power BI  
**Data Handling:** Jupyter Notebook, CSV Datasets, GitHub  
**Version Control:** Git & GitHub  

---

## 🚀 Future Improvements
- Add **SHAP/Feature Importance** visuals for interpretability.  
- Integrate **time-based validation** for temporal robustness.  
- Implement **real-time API or batch scoring pipeline** for campaign updates.  
- Add **revenue-based cost-sensitive evaluation** (ROAS-focused metrics).

---

## 🔑 About
**Author:** Rishabh Chandrakar  
**Focus:** Data Analytics & Supply Chain/Marketing Analytics  
**Connect:** [LinkedIn](https://www.linkedin.com/in/rishabh-chandrakar) | [GitHub](https://github.com/Rishabh1108ch)


---

> *This project demonstrates how data-driven marketing analytics and machine learning can transform ad campaign decision-making through actionable insights and predictive intelligence.*
