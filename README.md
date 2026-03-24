# nyc-taxi-trip-duration-ml
# NYC Taxi Trip Duration Prediction – Machine Learning Project

## 1. Project Overview
This project aims to predict the duration of taxi trips in New York City using machine learning.  
The project demonstrates a full machine learning pipeline, including data preprocessing, feature engineering, model training, and evaluation.

The final model used is an XGBoost Regressor trained on engineered spatial and temporal features.

---

## 2. Problem Statement
Accurately predicting taxi trip duration is important for ride-hailing services, route planning, and customer experience.  
However, travel time depends on many factors such as distance, time of day, traffic patterns, and location.

The objective of this project is to build a machine learning model that can estimate trip duration based on pickup and dropoff information and time-related features.

---

## 3. Dataset
Dataset: NYC Taxi Trip Duration (Kaggle)  
The dataset contains:
- Pickup and dropoff coordinates
- Pickup datetime
- Passenger count
- Trip duration (target variable)

Due to file size limitations, the full dataset is not included in this repository.  
You can download it from Kaggle and place it in the `data/` folder.

---

## 4. Feature Engineering
The following features were created from the raw data:

### Temporal Features
- Pickup hour
- Pickup weekday
- Month
- Weekend indicator
- Rush hour indicator

### Distance Features
- Haversine distance
- Manhattan distance
- Bearing (direction)

### Location Features
- Airport pickup/dropoff indicator

### Interaction Features
- Distance × Rush hour
- Distance × Weekend

These features help the model capture spatial and temporal patterns that affect trip duration.

---

## 5. Model
Model used: **XGBoost Regressor**

XGBoost is a gradient boosting algorithm based on an ensemble of decision trees.  
Each tree learns from the errors of the previous trees, and the final prediction is the sum of all trees.

**Input:** Engineered feature vector  
**Output:** Predicted trip duration

The target variable was log-transformed during training to improve model stability.

---

## 6. Evaluation Metrics
The model was evaluated using the following metrics:
- RMSE (Root Mean Squared Error)
- MAE (Mean Absolute Error)
- Error Percentiles

### Results:
- MAE ≈ 1.4 minutes
- RMSE ≈ 28 seconds

This means the model’s prediction is off by about 1.4 minutes on average.

---

## 7. Project Structure
nyc-taxi-trip-duration-ml/
│
├── data/
├── notebooks/
├── src/
├── models/
├── report/
├── presentation/
├── README.md
└── requirements.txt

---

## 8. How to Run the Project

### Install dependencies
```bash
pip install -r requirements.txt
