# Weather in Australia: Rain Prediction & Data Visualization

This repository contains a machine learning and data visualization semestral project for the **Data Visualization (BI-VIZ)** course at the Czech Technical University in Prague (CTU FIT).

The project explores historical meteorological data across Australia to perform in-depth exploratory data analysis (EDA), geospatial visualization, and build predictive machine learning models to answer the fundamental question: **Will it rain tomorrow?**

---

## 🌦️ Problem Description

Weather forecasting is a classic yet complex real-world challenge. In this project, the problem is framed as a supervised binary classification task: based on single-day atmospheric observations (temperatures, atmospheric pressure, humidity, wind speeds, sunshine, cloud cover, and rainfall), predict whether it will rain on the following day (`RainTomorrow`: Yes / No).

A core challenge of this dataset is the natural class imbalance: approximately **78% of days are rain-free**, which heavily influences evaluation metrics and model behavior.

---

## 📊 Datasets & Sources

1. **Australian Weather Dataset (`weatherAUS.csv`)**
   - Source: [Kaggle - Weather Dataset Rattle Package](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package)
   - Origin: Australian Bureau of Meteorology ([BOM](http://www.bom.gov.au/))

2. **Australian City Coordinates (`au.csv`)**
   - Source: [Kaggle - World Cities Australia](https://www.kaggle.com/datasets/maryamalizadeh/worldcities-australia) (supplemented with Google Earth).
   - Used to augment meteorological stations with exact latitude and longitude for geospatial mapping.

---

## 🛠️ Data Preprocessing & Feature Engineering

- **Geocoding Enrichment**: Joined latitude and longitude coordinates based on station `Location`.
- **High-Dimensionality Drop**: Removed high-cardinality categorical wind direction variables (`WindGustDir`, `WindDir9am`, `WindDir3pm`).
- **Diurnal Feature Engineering**: Added linear difference features capturing daily intra-day dynamic changes:
  - Temperature difference: $\Delta \text{Temp} = \text{Temp3pm} - \text{Temp9am}$
  - Humidity difference: $\Delta \text{Humidity} = \text{Humidity3pm} - \text{Humidity9am}$
  - Pressure difference: $\Delta \text{Pressure} = \text{Pressure3pm} - \text{Pressure9am}$
  - Wind speed difference: $\Delta \text{WindSpeed} = \text{WindSpeed3pm} - \text{WindSpeed9am}$

---

## 🤖 Machine Learning Models & Experiments

- The dataset was split into **Training (70%)**, **Validation (15%)**, and **Test (15%)** sets.
- Used ML models:
  1. **Decision Tree Classifier**
  2. **Logistic Regression (with Class Balancing)**
---

## 💻 Installation & Requirements

To run the notebooks locally, ensure you have Python 3.8+ and install the necessary dependencies:

```bash
pip install pandas numpy matplotlib seaborn plotly scikit-learn
```
