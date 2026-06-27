# RedBus Passenger Seat Count Prediction

## Overview

This project was developed as part of the **RedBus Data Hackathon**, where the objective was to predict the **final passenger seat count** for bus routes using historical booking and transaction data.

The solution leverages feature engineering and a **LightGBM Regressor** to estimate passenger demand across different routes and travel dates, enabling more accurate demand forecasting and operational planning.

---

## Problem Statement

The objective is to predict the **final passenger seat count** for each bus route before departure using historical booking trends and transaction data.

Accurate passenger demand prediction helps in:

* Better fleet allocation
* Improved demand forecasting
* Dynamic pricing strategies
* Efficient operational planning

---

## Dataset

The hackathon provided two datasets:

### **1. `train.csv`**

Contains the target variable used for model training.

| Column            | Description                |
| ----------------- | -------------------------- |
| `doj`             | Date of Journey            |
| `srcid`           | Source City ID             |
| `destid`          | Destination City ID        |
| `final_seatcount` | Final Passenger Seat Count |

### **2. `transactions.csv`**

Contains historical booking and transaction information for each route.

Key attributes include:

* Source & Destination IDs
* Source & Destination Regions
* Source & Destination Tier Information
* Cumulative Search Count
* Cumulative Seat Count
* Booking Date
* Journey Date

---

## Data Preprocessing

The following preprocessing steps were performed:

* Converted date columns into `datetime` format
* Calculated **Days Before Departure (DBD)**
* Cleaned inconsistent date formats
* Merged transaction data with the training dataset
* Removed duplicate records
* Handled missing values
* Generated route identifiers

---

## Feature Engineering

Several additional features were created to improve prediction accuracy.

### **Temporal Features**

* Day of Week
* Month
* Weekend Indicator

### **Historical Features**

* Cumulative Search Count
* Cumulative Seat Count

### **Holiday Features**

Indian public holidays (2023–2025) were collected and merged with the dataset to generate a **Holiday Indicator**, allowing the model to capture seasonal variations in travel demand.

---

## Machine Learning Model

The final model used for prediction was: **LightGBM Regressor**

---

## Model Evaluation

| Metric                             | Score      |
| ---------------------------------- | ---------- |
| **Mean Absolute Error (MAE)**      | **268.54** |
| **Root Mean Squared Error (RMSE)** | **394.10** |

The model effectively captured passenger demand patterns by combining historical booking statistics with temporal and holiday-based features.

---

## Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Scikit-learn**
* **LightGBM**
* **BeautifulSoup**
* **Matplotlib**

---


## Future Improvements

* Integrate weather information into the prediction pipeline
* Incorporate festival intensity and regional event data
* Perform hyperparameter optimization using Optuna or Grid Search
* Compare performance with CatBoost and XGBoost
* Deploy the model as a web application for real-time seat demand prediction

---

## Achievement

* **Developed as part of the RedBus Data Hackathon**
* **Achieved Nationwide Rank 301**
* Built an end-to-end machine learning pipeline including data preprocessing, feature engineering, model training, evaluation, and submission generation.
