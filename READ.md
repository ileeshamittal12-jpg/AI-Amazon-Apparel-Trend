# Seasonal Sales Analysis & Forecasting — Amazon Apparel

**Project**: AI for Market Trend Analysis — Seasonal sales and cancellation analysis for Amazon apparel  
**Student**: Isha  
**Purpose**: Explore seasonal buying patterns, analyze cancellations, and forecast monthly revenue for the next 12 months using AI and machine learning techniques.

---

## 📂 Contents
This repository contains:

- **Notebooks**: Reproducible code for EDA, preprocessing, modeling, and evaluation  
- **Scripts**: Helper scripts to run the full pipeline  
- **Deliverables**: Slide deck, final report, demo script, and demo-ready notebook  
- **Data**: Placeholder for `amazon_apparel_data.csv`  

---

## 🚀 Quick Start (Google Colab)
1. Open `notebooks/00_run_all_in_colab.ipynb` in Google Colab.  
2. Upload `data/amazon_apparel_data.csv` to the Colab session, or mount Google Drive and set `DATA_PATH`.  
3. Run cells from top to bottom (installs dependencies, runs EDA → preprocessing → modeling → evaluation).  
4. Use `notebooks/demo_script.ipynb` to generate demo plots and outputs for the 3-minute video.

---

## 📊 Dataset
Expected CSV columns (update in `config/column_map.json` if different):

- `order_id`, `order_date` (YYYY-MM-DD)  
- `product_id`, `product_category`, `material` (e.g., wool, cotton)  
- `sales_amount` (numeric), `quantity`  
- `state`, `status` (Cancelled/Shipped), `customer_id`  

---

## 🗂 Project Structure

project-root/
├─ README.md
├─ requirements.txt
├─ data/
│ └─ amazon_apparel_data.csv
├─ notebooks/
│ ├─ 00_run_all_in_colab.ipynb
│ ├─ 01_eda.ipynb
│ ├─ 02_preprocessing_features.ipynb
│ ├─ 03_models.ipynb
│ ├─ 04_evaluation_and_analysis.ipynb
│ └─ demo_script.ipynb
├─ src/
│ ├─ data_loader.py
│ ├─ features.py
│ ├─ models.py
│ └─ evaluate.py
├─ reports/
│ ├─ final_report.pdf
│ └─ results_summary.csv
├─ slides/
│ └─ 10_slide_deck.pptx
├─ demo/
│ └─ demo_script.txt
└─ config/
└─ column_map.json

---

## 📓 Notebooks Summary

- **00_run_all_in_colab.ipynb** — installs libraries, sets paths, runs a full pipeline to regenerate outputs  
- **01_eda.ipynb** — exploratory data analysis: missing data, seasonality, material-season interaction, cancellations  
- **02_preprocessing_features.ipynb** — cleaning, feature engineering (lags, rolling means, seasonal dummies)  
- **03_models.ipynb** — model training (LightGBM, XGBoost, SARIMA/Prophet, LSTM example)  
- **04_evaluation_and_analysis.ipynb** — metrics, residuals, feature importance, insights  
- **demo_script.ipynb** — condensed version for 3-minute demo recording  

---

## 📌 Requirements

Example `requirements.txt`:

pandas
numpy
matplotlib
seaborn
scikit-learn
lightgbm
xgboost
tensorflow
statsmodels
prophet
yellowbrick
shap
joblib
jupyter


> Note: Colab already has many packages installed. `00_run_all_in_colab.ipynb` handles installs conditionally.

---

## ⚙ How to Reproduce

1. Place the dataset in `data/amazon_apparel_data.csv`.  
2. Open `notebooks/00_run_all_in_colab.ipynb` in Google Colab.  
3. Run top-to-bottom.  
4. Outputs (plots, `results_summary.csv`, saved model artifacts) are available in `/content/drive/MyDrive/project-output/` if using Drive, or in session files.

---

## 📝 Primary Tasks Implemented

1. **EDA**: Monthly/seasonal sales trends, material-season interaction, cancellation heatmaps  
2. **Feature Engineering**: Time features, lags, rolling means, material×season interactions, state-level aggregations  
3. **Models**:  
   - Regression (monthly revenue): LightGBM (primary), XGBoost, Ridge baseline  
   - Time-series: SARIMA / Prophet  
   - Sequence model: LSTM (demo example)  
   - Cancellation classifier: LightGBM or LogisticRegression  
4. **Validation**: Time-series split (rolling window); metrics RMSE, MAE, MAPE (regression); precision/recall/F1 (classification)  
5. **Explainability**: SHAP summary plots, feature importance  

---

## 🎯 Deliverables Included

- Notebooks (runnable)  
- `slides/10_slide_deck.pptx`  
- `reports/final_report.pdf`  
- `demo/demo_script.txt`  
- `models/` (saved best model artifacts)  

---

## 🎬 Demo Recording Checklist (3 minutes)

1. One-liner objective (10s)  
2. Show seasonal sales plot + cancellation heatmap (40s)  
3. Mention best model and metrics (30s)  
4. Show 12-month forecast + action (40s)  
5. Closing & link to repo (10s)  

---

## ⚠ Notes, Assumptions & Tips

- Use time-based train/validation split (no random shuffle)  
- If < 2 years of data, prefer tree models and simpler time-series baselines  
- Example hyperparameter grids included in `03_models.ipynb` — tune manually or use Optuna  

---

## 📬 Contact / Support

For any questions or issues running the project, you can reach out to the student (Isha).  
