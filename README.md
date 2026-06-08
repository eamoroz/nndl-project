# Demand Forecasting for FMCG Products Using a CNN-Transformer Model
Team 6: Militsyna Polina, Moroz Ekaterina, Soboleva Tatyana

## Project Overview

This project develops a deep learning model for demand forecasting in e-commerce using FMCG sales data from Wildberries.

The objective is to predict product demand **7 days ahead**, supporting inventory planning, replenishment decisions, and logistics management.

A hybrid **CNN-Transformer** architecture is used to capture both short-term demand fluctuations and longer temporal dependencies in historical sales data.

---

## Dataset

The dataset contains daily product-level observations, including:

* Sales volume
* Product prices
* Product characteristics
* Customer feedback indicators
* Historical demand information

The data used for training and evaluation is provided via link 

https://drive.google.com/file/d/1JL_IZ6xZ9F8JTDplsZNJ5uJspXdEQS-H/view?usp=sharing 

An access request is required

---

## Forecasting Setup

* Forecast horizon: **7 days**
* Input sequence length: **30 days**
* Global forecasting model trained across multiple products

Feature engineering includes:

* Lag features
* Rolling statistics
* Calendar features
* Product-related attributes

---

## Baseline Models

The proposed model is compared against two benchmark approaches:

1. **Lag 7** – assumes future demand equals demand observed one week earlier.
2. **Rolling Mean 7** – uses the average demand from the previous 7 days.

---

## Results

| Model           |  RMSE |
| --------------- | ----: |
| CNN-Transformer | 45.15 |
| Rolling Mean 7  | 48.85 |
| Lag 7           | 57.06 |

The CNN-Transformer achieved the lowest RMSE and outperformed both benchmark models.

RMSE is used as the primary evaluation metric because large forecasting errors have the greatest business impact through stockouts, overstocking, and additional logistics costs.

---

## Reproducibility

The notebook contains all preprocessing, feature engineering, model training, and evaluation steps required to reproduce the reported results.

Random seeds are fixed to ensure reproducibility of the experiments.
