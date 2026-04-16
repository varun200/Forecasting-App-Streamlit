# 📈 Sales Forecasting Automation App

A multi-model sales forecasting web application built with **Python** and **Streamlit**, designed to automate the end-to-end forecasting workflow for product-territory sales data.
---

## 🚀 Demo

> Upload your sales data → Select forecast models → View results, charts, and summaries — all in one app.

---

## 📌 Background

Manually generating sales forecasts across multiple products and territories was time-consuming and error-prone. This app was built to automate that process, handling data validation, model selection, parameter tuning, and output generation in a guided, multi-step workflow.

---

## ⚙️ Features

- **Guided 3-step workflow:** Data Upload → Model Parameters → Results
- **Multi-model forecasting:** Run and compare up to 6 models simultaneously
  - Linear Regression
  - Exponential Smoothing (Holt-Winters)
  - SARIMA
  - Prophet (Meta)
  - Gaussian Process
  - Upper/Lower Confidence Bounds
- **Automatic data validation:**
  - Missing value and zero detection
  - Date consistency checks
  - Z-score outlier detection with optional normalization
- **Calendarization support:** Adjusts forecasts for seasonal business calendar effects
- **Interactive visualizations:** Product × Territory forecast charts using Plotly
- **Downloadable template:** Dynamically generates input Excel templates based on user-specified products and territories
- **Summary reporting:** Most Recent 13-Week vs. Prior 13-Week sales comparison with growth % by forecast method

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python | Core logic |
| Streamlit | Web application framework |
| Prophet | Trend + seasonality forecasting |
| statsmodels (SARIMA, Holt-Winters) | Time series modeling |
| scikit-learn | Linear regression, Gaussian Process |
| Plotly | Interactive charts |
| pandas / NumPy | Data processing |
| openpyxl | Excel output generation |

---

## 📂 Project Structure

```
Forecasting-App-Streamlit/
│
├── 1_🏠_Home.py               # Step 1: Data upload, validation, outlier detection
├── pages/
│   ├── 2_⚙️_Model Parameters.py  # Step 2: Date range + model + parameter selection
│   └── 3_📊_Results.py           # Step 3: Forecast output, charts, summary table
├── Calendarisation.xlsx       # Business calendar for seasonal adjustment
├── requirements.txt           # Dependencies
└── README.md
```

---

## 📊 How It Works

### Step 1 — Data Upload
- User downloads a dynamically generated Excel template (configurable by number of products and territories)
- Uploads historical weekly/monthly sales data
- App validates: missing values, date consistency, statistical outliers (Z-score > 3)

### Step 2 — Model Parameters
- User selects baseline and forecast date ranges
- Selects one or more forecast models
- Configures model-specific parameters (trend type, seasonality, SARIMA order, confidence interval)

### Step 3 — Results
- Forecasts are de-calendarized, modeled, then re-calendarized for business accuracy
- Interactive Plotly charts by product and territory
- Pivot table output with weekly or quarterly aggregation
- 13-week summary comparison with growth % across all forecast methods

---

## 🔧 Installation & Setup

```bash
# Clone the repository
git clone https://github.com/varun200/Forecasting-App-Streamlit.git
cd Forecasting-App-Streamlit

# Install dependencies
pip install -r requirements.txt

# Run the app
streamlit run 1_🏠_Home.py
```

---

## 📁 Input Data Format

The app generates a downloadable Excel template. Each date column represents a week (or month), and the values are sales figures for that product-territory combination in that period.

| Product | Territory | MM/DD/YYYY | MM/DD/YYYY | ... |
|---------|-----------|------------|------------|-----|
| ProductA | t1 | 1200 | 1350 | ... |
| ProductA | t2 | 980 | 1100 | ... |
| ProductB | t1 | 450 | 500 | ... |

> **Note:** Values represent sales units for each product-territory pair per time period. The app supports both weekly and monthly data frequencies.

---

## 📈 Sample Use Case

> A pharma sales team needs weekly forecasts for 3 products across 10 territories for the next quarter. Instead of manually running models in Excel, an analyst uploads the historical data, selects SARIMA + Prophet, sets the forecast window, and downloads results in under 15 minutes.

---

## 🙋 Author

**Varun Ramadugu**  
MS Business Analytics, Northeastern University  
[LinkedIn](https://linkedin.com/in/varun-ramadugu) | [GitHub](https://github.com/varun200)
