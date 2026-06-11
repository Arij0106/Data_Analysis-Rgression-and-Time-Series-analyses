# Level-2-Data_Analysis_codveda-tachnologies
This repository contains an end-to-end data analytics and predictive pipeline focused on financial market intelligence. The project combines multivariate regression algorithms with statistical time-series decomposition frameworks to model, evaluate, and extract behavioral insights from historical equity metrics.

##  Project Overview

The core objective of this project is to perform double-layered analytical validation on equity metrics:
1. **Regression Analysis:** Implementing linear models to map the mathematical relationship between standard trading liquidity bounds (`Open`, `High`, `Low`, `Volume`) and the final equity valuation baseline (`Close`).
2. **Time Series Decomposition:** Isolation of systemic trends, cyclical seasonality, and stochastic noise (residuals) inside historical data tracking.

### Data Profile
* **Source Tracking:** Global multi-ticker historical stock price tracking logs.
* **Core Variables Evaluated:** `Symbol`, `Date`, `Open`, `High`, `Low`, `Close`, `Volume`.
* **Primary Target Filter:** Apple Inc. (`AAPL`) for isolated temporal trend structures.

---

##  Pipeline Phases & Implementation

### Task 1: Predictive Modeling (Regression Analysis)
* **Data Cleansing:** Erased multi-column structural null anomalies natively via row-wise list deletions (`dropna()`).
* **Evaluation Framework:** Execution of a decoupled 80/20 data split pattern to isolate validation sets against standard overfitting traps.
* **Algorithm Deployment:** Ordinary Least Squares (OLS) multivariate `LinearRegression`.

#### Model Performance Results:
* **Mean Squared Error (MSE):** `0.5160` (Extremely tight variance boundaries out-of-sample).
* **R-squared ($R^2$):** `1.0000` (Exceptional explanatory fitness reflecting near-absolute convergence with historical variance).

#### Vector Weight Coefficients:
* **Intercept:** `-0.0079`
* **Open:** `-0.538093`
* **High:** `+0.787251`
* **Low:** `+0.750968`
* **Volume:** `-0.000000` (Negligible linear slope impact on pricing target endpoints).

---

### Task 2: Temporal Mapping (Time Series Analysis)
Focused on tracking historical trends, volatility structures, and localized market cyclic movements over strict business-day horizons (`'B'`).

Utilisez le code avec précaution.[ Raw Time Data ] ──► [ Resampled Business Days ('B') ] ──► [ Forward Fill ('ffill') ]│▼[ Seasonal Decompose Model ]
* **Methodology:** Additive Seasonal Decomposition structural splits over a set 5-day trading week lifecycle baseline (`period=5`).
* **Visual Output Matrix:** Generates a stacked 4-panel visual dashboard breakdown mapping:
  1. **Observed (Actuals):** Unfiltered data path tracking.
  2. **Trend:** Smooth rolling trajectories filtering short-term noise.
  3. **Seasonal:** Symmetrical 5-day cycle patterns.
  4. **Residuals:** Random stochastic white noise variations.

---

##  Tech Stack & Architecture

* **Runtime Support:** Jupyter Notebook environment ecosystem (fully optimized for Google Colab/NBViewer).
* **Data Structures & Operations:** `pandas`
* **Mathematical Operations:** `scikit-learn` (LinearRegression, metrics frameworks).
* **Statistical Mathematics:** `statsmodels` (tsa.seasonal framework tools).
* **Visualization Engine:** `matplotlib` (using the modern clean `seaborn-v0_8-whitegrid` styling configuration layout).

---

##  Quick Start & Dataset Link Integration

To immediately load data assets natively straight from your remote notebook canvas without making any manual system environment imports, execute the following block:

```python
import pandas as pd

# Remote repository raw streaming connection endpoint link setup
url = "https://raw.githubusercontent.com/Arij0106/Data_Analysis-Rgression-and-Time-Series-analyses/refs/heads/main/stockprices.csv"
df = pd.read_csv(url)

# Print structural metrics summary
print(df.head(11))
```

---
