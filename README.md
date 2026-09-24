# 🏡 House Price Prediction

A machine-learning project that predicts residential property prices from a real-world Indian housing dataset. The entire pipeline — data loading, cleaning, model training, evaluation, and an interactive prediction UI — lives in a single Jupyter Notebook.

---

## 📂 Dataset

| Detail | Info |
|--------|------|
| **Source** | [House Price Prediction Dataset – Kaggle](https://www.kaggle.com/datasets/zafarali27/house-price-prediction-dataset) |
| **File** | `house_prices.csv` |
| **Records** | ~2 000+ property listings |
| **Region** | Thane, Maharashtra, India |
| **Key columns** | Title, Amount (INR), Price/sqft, Location, Carpet Area, BHK, Status, Floor, Furnishing, Bathroom, Balcony, Ownership |

---

## 📝 Project Description

This project builds an end-to-end house price prediction system:

1. **Data collection & loading** — reads `house_prices.csv` directly into a Pandas DataFrame.
2. **Data cleaning** — parses messy string prices (`42 Lac`, `1.40 Cr`) into numeric rupee values, extracts area in sqft, BHK count, floor number, and label-encodes all categorical features.
3. **Exploratory Data Analysis** — six EDA charts (price distribution, BHK vs price, area vs price, furnishing vs price, correlation heat-map, floor vs price).
4. **Model training** — trains three models side-by-side: Linear Regression, Random Forest Regressor, and Gradient Boosting Regressor; evaluates each by MAE, RMSE, and R².
5. **Feature importance** — bar charts for tree-based models.
6. **Interactive frontend** — an `ipywidgets` GUI inside the same notebook where the user tweaks sliders/dropdowns and clicks **Predict Price** to get an instant estimate in Lakh/Crore INR.

---

## 🛠️ Technologies Used

| Layer | Library / Tool |
|-------|---------------|
| Language | Python 3.9+ |
| Data handling | `pandas`, `numpy` |
| Visualisation | `matplotlib`, `seaborn` |
| Machine learning | `scikit-learn` |
| Frontend (UI) | `ipywidgets` |
| Notebook runtime | `jupyter` / `notebook` |

---

## ⚙️ Setup & Run Instructions

### 1. Clone / download the project

```bash
git clone <your-repo-url>
cd daproject
```

### 2. (Recommended) Create a virtual environment

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Enable ipywidgets in Jupyter

```bash
jupyter nbextension enable --py widgetsnbextension
```

*(Only needed once; already handled automatically in JupyterLab 3+.)*

### 5. Launch the notebook

```bash
jupyter notebook house_price_prediction.ipynb
```

### 6. Run all cells

In Jupyter: **Kernel → Restart & Run All**

The interactive prediction UI appears at the bottom of the notebook after all cells execute.

---

## 🔑 Key Information

- **Target variable**: property price in Indian Rupees (INR), derived from the `Amount(in rupees)` column.
- **Best model**: typically **Gradient Boosting Regressor** or **Random Forest Regressor** (displayed automatically after training).
- **Saved artefacts**: `eda_charts.png`, `model_evaluation.png`, and feature-importance PNG files are written to the project folder after running.
- The dataset contains listings **only from Thane, Maharashtra**; predictions outside this distribution may be less accurate.
- Rows with missing price or area values are dropped during cleaning.

---

## 📁 Project Structure

```
daproject/
├── house_price_prediction.ipynb   ← Single notebook (backend + frontend)
├── house_prices.csv               ← Raw dataset
├── requirements.txt               ← Python dependencies
├── README.md                      ← This file
├── House_Price_Prediction_Documentation.docx  ← Full project documentation
├── eda_charts.png                 ← Generated after running notebook
├── model_evaluation.png           ← Generated after running notebook
└── feature_importance_*.png       ← Generated after running notebook
```

---

## 📄 License

For educational / research use. Dataset sourced from Kaggle under the terms of its original publisher.
