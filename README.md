# Predictive-Maintenance-for-NASA-Turbofan-Engines ✈️⚙️
## 📌 Project Overview

In the aviation industry, engine failure is not an option. Traditional maintenance strategies like Reactive (fix when broken) or Preventive (scheduled replacement) are either dangerous or costly.

This project implements a Predictive Maintenance (PdM) solution using Machine Learning to predict the Remaining Useful Life (RUL) of NASA turbofan engines. By analyzing sensor data, we can forecast exactly when an engine will fail, enabling "Zero Downtime" operations.

## 🛠️ Methodology & Approach

### 1. Data Cleaning & Preprocessing

  * Dead Sensor Removal: Identified and removed 7 sensors (e.g., T2, P2, epr, farB) that showed zero variance/constant values to reduce noise.
  * Data Integrity: Validated having no missing values (Nulls) and checked data types.
    
### 2. Feature Engineering

   * Piecewise Linear Degradation: Applied RUL Clipping (Threshold = 125 cycles). This assumes the engine operates normally for a period before degradation starts, preventing the model from learning noise during the healthy phase.
    
### 3. Model Selection

  Benchmarked multiple regression algorithms to find the best performance:

   * #### Linear Regression (Baseline)
   * #### Support Vector Regressor (SVR)
   * #### Random Forest Regressor
   * #### XGBoost Regressor (Best Performer) 🏆

## 🚀 Results

 The XGBoost model demonstrated superior ability to capture non-linear degradation trends compared to other models.
 
   * **Evaluation Metric:** Root Mean Squared Error (RMSE).
   * **Simulation:** The model successfully tracks the degradation path of unseen engines, clearly identifying the critical "Failure Zone" (last 30 cycles).

##🧰 Technologies Used

  * **Python**
  * **Data Manipulation: Pandas, NumPy**
  * **Visualization: Matplotlib, Seaborn**
  * **Machine Learning: Scikit-Learn, XGBoost**
