# 🌍 Climate Intelligence System
### Emission Forecasting, Risk Zoning, Anomaly Detection & Public Sentiment Analysis

---

## 📌 Project Overview

Climate change analysis is often limited to static visualizations and basic statistical summaries.  
This project goes beyond descriptive analysis and builds a **Climate Intelligence System** that transforms raw climate data into **actionable intelligence**.

The system integrates:
- Spatial emission analysis
- Climate risk zoning using machine learning
- Time-series forecasting of CO₂ emissions
- Anomaly detection for emission spikes
- Public sentiment analysis related to climate change

---

## 🎯 Project Objectives

| ID | Objective |
|----|-----------|
| O1 | Analyze spatial and temporal CO₂ emission patterns |
| O2 | Classify locations into climate risk zones |
| O3 | Forecast future emissions using time-series models |
| O4 | Detect abnormal emission events |
| O5 | Analyze public sentiment trends on climate change |

---

## 🧠 Key Features

- 📊 Advanced Exploratory Data Analysis (EDA)
- 🧭 Risk-based spatial clustering (Low / Medium / High)
- ⏱️ Seasonal time-series forecasting (SARIMA)
- 🚨 Emission anomaly detection (Isolation Forest)
- 🗣️ NLP-based sentiment analysis (VADER)
- 🗺️ Interactive maps using **Folium** (no geopandas dependency)

---

## 📊 Dataset Description

This project uses three datasets designed to simulate real-world climate monitoring and analysis scenarios.

---

### 🔹 Training Dataset (`train.csv`)

The training dataset contains historical emission data and atmospheric indicators used for model training, risk zoning, and anomaly detection.

| Column Name | Description |
|------------|------------|
| latitude | Latitude of the observation |
| longitude | Longitude of the observation |
| year | Year of observation (2019–2021) |
| week_no | Week number (0–52) |
| SO2_density | Sulphur dioxide concentration |
| NO2_density | Nitrogen dioxide concentration |
| CO_density | Carbon monoxide concentration |
| aerosol_index | Aerosol measurement index |
| emission | CO₂ emission value (target variable) |

---

### 🔹 Test Dataset (`test.csv`)

The test dataset represents future unseen data and is used for emission forecasting and scenario simulation.

| Column Name | Description |
|------------|------------|
| latitude | Latitude of the observation |
| longitude | Longitude of the observation |
| year | Year of observation (2022) |
| week_no | Week number |
| SO2_density | Sulphur dioxide concentration |
| NO2_density | Nitrogen dioxide concentration |
| CO_density | Carbon monoxide concentration |
| aerosol_index | Aerosol measurement index |

> ⚠️ The test dataset does not contain emission values, replicating real-world prediction conditions.

---

### 🔹 Sentiment Dataset (`nasa_comments.csv`)

This dataset contains public comments related to climate change, used for sentiment analysis.

| Column Name | Description |
|------------|------------|
| Text | Public comment on climate change |
| Date | Timestamp of the comment |

---

## 🔬 Methodology

The project follows a structured data science pipeline to transform raw data into actionable climate intelligence.

---

### 1️⃣ Data Preprocessing

- Removal of high-missing-value columns
- Median-based imputation for numerical features
- Log transformation applied to emission values to handle skewness
- Data consistency checks across spatial and temporal dimensions

---

### 2️⃣ Feature Engineering

- Spatial aggregation using rounded latitude and longitude
- Computation of location-wise emission statistics:
  - Mean emission
  - Emission variability
  - Maximum emission
  - Temporal emission trend
- Creation of derived features for clustering and forecasting

---

### 3️⃣ Climate Risk Zoning

- Unsupervised learning using **KMeans clustering**
- Locations classified into three risk categories:
  - 🟢 Low Risk
  - 🟠 Medium Risk
  - 🔴 High Risk
- Risk zones visualized using interactive **Folium maps**
- No dependency on heavy GIS libraries (e.g., geopandas)

---

### 4️⃣ Time-Series Forecasting

- Weekly emission trends modeled using **Seasonal ARIMA (SARIMA)**
- Seasonal patterns captured using a 52-week cycle
- Forecasts generated with confidence intervals
- Used to support proactive climate planning

---

### 5️⃣ Anomaly Detection

- Emission anomalies detected using **Isolation Forest**
- Identification of abnormal emission spikes
- Helps highlight potential environmental or industrial irregularities

---

### 6️⃣ Public Sentiment Analysis

- Text preprocessing and sentiment scoring using **VADER**
- Aggregation of sentiment scores by year
- Comparison of public concern trends with emission behavior

---

## 🛠️ Technologies Used

| Category | Tools / Libraries |
|--------|------------------|
| Programming Language | Python 3.x |
| Development Environment | VS Code |
| Notebook Environment | Jupyter Notebook |
| Data Processing | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn, Folium |
| Machine Learning | Scikit-learn |
| Time Series Analysis | Statsmodels |
| Natural Language Processing | NLTK (VADER) |

---

## 📈 Results & Insights

- Clear spatial separation of **climate risk zones**
- Strong seasonal patterns observed in emission trends
- Successful identification of anomalous emission events
- Public sentiment shows a gradual increase in climate concern
- Forecasting models provide meaningful future emission projections

---

## ⚠️ Limitations

- Dataset is geographically constrained
- No real-time data ingestion
- Forecasting models rely on historical trends only
- Sentiment analysis limited to polarity-based interpretation

---

## 🔮 Future Enhancements

- Integration with real satellite-based climate datasets
- Deep learning models (LSTM) for improved forecasting
- Interactive dashboards using Streamlit or Flask
- Multi-region or global-scale analysis
- Policy impact and emission reduction simulations

---

## 📜 Ethical Considerations

- No personally identifiable information is used
- Sentiment data is anonymized
- Analysis is purely academic and non-political
- Results are presented without bias or manipulation

---

## 🧾 Conclusion

This project demonstrates how climate datasets can be transformed into an intelligent analytical system rather than static reports.  
By integrating spatial analysis, machine learning, time-series forecasting, anomaly detection, and sentiment analysis, the system provides a comprehensive framework for climate monitoring and decision support.

The project emphasizes **robust methodology, interpretability, and real-world applicability**, making it suitable for academic evaluation as well as portfolio presentation.
