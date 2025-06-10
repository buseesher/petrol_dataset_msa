# 🛢️ Predicting Petrochemical Output using Machine Learning

Description:

This project focuses on time-series data cleaning, feature engineering, and machine learning regression to predict petrochemical plant output using historical operational data.

[Colab Notebook Link](https://colab.research.google.com/drive/16j7txzTN0hKVSs4cpL4eijnp14w-U2qC)

## 📁 Dataset

Data is read from `/content/train_test.xlsx` and prepared for ML tasks.

A separate dataset for future prediction is loaded from `/content/prediction.csv`.

## 📊 Key Steps in the Pipeline

🧹 1. Data Cleaning & Transformation

* Missing and duplicate values handled.

*Time-based indexing and sorting.

*Outlier filtering and rolling averages (24-hour means).

*Manual removal of identified faulty data intervals.

 📈 2. Feature Engineering
 
* Aggregated daily averages: `mean_Y1`, `mean_Y2`, ...,`mean_U2` 

* Final dataset exported as:
* `/content/drive/MyDrive/Datathon/yarisma_veriseti/ml_dataset.csv`

🤖 3. Machine Learning Model

*Target: D column (petrochemical output value)

*Model used: Support Vector Regression (SVR)

*Scaled input features with StandardScaler

*Metrics computed:

    *MSE (Mean Squared Error)

    *MAE (Mean Absolute Error)

    *RMSE (Root Mean Squared Error)

    *MAPE (Mean Absolute Percentage Error)

Example Output:

```bash
train mse = 1.42  & train mae = 0.97 & train rmse = 1.19 & train mape = 0.019
test mse = 1.38  & test mae = 0.95 & test rmse = 1.17 & test mape = 0.021
Test accuracy (R²): 87.6%
  ```

📉 4. Prediction on New Data

*Incoming hourly data is aggregated into 24-hour means.

*Predictions generated using the trained SVR model.

*Output is stored in a new DataFrame for visualization or further processing.

## 📦 Libraries Used

`pandas`, `numpy`, `matplotlib`, `seaborn`, `plotly`

`scikit-learn`: SVR, train/test split, preprocessing, metrics, etc.

## 📌 Notebooks & Files

📓 [Training & Modeling Notebook](https://colab.research.google.com/drive/16j7txzTN0hKVSs4cpL4eijnp14w-U2qC)

📂 train_test.xlsx: historical dataset

📂 prediction.csv: prediction input data

📄 Final cleaned training data: `ml_dataset.csv`

## ⚠️ Notes

This project is part of an educational assignment under the MSA Datathon scope.

All data preprocessing and model tuning decisions are manually designed for explainability.

