# Rossmann Store Sales Forecasting

A machine learning and time-series forecasting project to predict daily sales for Rossmann drug stores using historical sales data. The project includes data preprocessing, feature engineering, exploratory data analysis (EDA), multiple forecasting models, model evaluation, visualization, and MLflow experiment tracking.

---

## Project Objectives

- Predict daily sales for Rossmann stores.
- Compare the performance of multiple machine learning models.
- Perform feature engineering for time-series forecasting.
- Analyze sales trends through visualizations.
- Track experiments and register the best model using MLflow.

---

## Dataset

The project uses the **Rossmann Store Sales** dataset from Kaggle.

Dataset Files:

- `train.csv`
- `test.csv`
- `store.csv`
- `sample_submission.csv`

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- CatBoost
- Prophet
- MLflow

---

## Project Workflow

### 1. Data Loading

- Import datasets
- Merge train/test data with store information

---

### 2. Data Preprocessing

#### Missing Value Handling

Filled missing values in:

- CompetitionOpenSinceMonth
- CompetitionOpenSinceYear
- Promo2SinceWeek
- Promo2SinceYear
- PromoInterval
- CompetitionDistance (using median)

#### Duplicate Check

- Verified duplicate records

#### Data Type Conversion

- Converted `Date` to datetime format

#### Outlier Detection

Outliers were identified using the **Interquartile Range (IQR)** method on the **Sales** column.

---

### 3. Feature Engineering

#### Date Features

Extracted:

- Year
- Month
- Day
- Week
- Weekday

#### Lag Features

Created previous sales features:

- Lag_1
- Lag_7
- Lag_14
- Lag_30
- Lag_60
- Lag_90

#### Rolling Features

Created rolling averages:

- Rolling_Average_7
- Rolling_Average_14
- Rolling_Average_30
- Rolling_Average_60
- Rolling_Average_90

---

### 4. Exploratory Data Analysis (EDA)

The following analyses were performed:

- Daily Sales Trend
- Monthly Sales Trend
- Sales by Weekday
- Sales by Month
- Store-wise Sales
- Correlation Heatmap
- Sales Distribution
- Boxplot for Outlier Detection
- Rolling Mean Trend

---

## Machine Learning Models

### 1. Linear Regression

- One-Hot Encoding
- Standardization
- Model Training
- Evaluation

---

### 2. Decision Tree Regressor

- One-Hot Encoding
- Model Training
- Feature Importance

---

### 3. CatBoost Regressor

- Native categorical feature handling
- Hyperparameter tuning
- Feature Importance
- SHAP Analysis

---

### 4. Prophet

Additional regressors used:

- Promo
- Open
- SchoolHoliday
- StateHoliday
- CompetitionDistance
- Promo2
- DayOfWeek

Additional seasonalities:

- Weekly
- Monthly
- Quarterly
- Yearly

---

## Model Evaluation

Models were evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

---

## Visualizations

Generated visualizations include:

- Actual vs Predicted
- Residual Plot
- Feature Importance
- SHAP Summary Plot
- SHAP Dependence Plot
- Forecast vs Actual
- Rolling Forecast
- Error Distribution
- Monthly Prediction Accuracy

---

## MLflow Integration

MLflow was used to track experiments.

Each run stores:

### Parameters

- Model Name
- Hyperparameters

### Metrics

- MAE
- RMSE
- R² Score
- Training Time

### Artifacts

- Feature Importance Plot
- Residual Plot
- Forecast Plot
- Rolling Forecast Plot
- SHAP Summary Plot

### Model Registry

The best-performing model is registered in the MLflow Model Registry.

---

## Project Structure

```
Rossmann/
│
├── dataset/
│   ├── train.csv
│   ├── test.csv
│   ├── store.csv
│   └── sample_submission.csv
│
├── notebook.ipynb
│
├── cb_feature_importance.png
├── cb_residual.png
├── dt_feature_importance.png
├── prophet_forecast.png
├── rolling_forecast.png
├── shap_summary.png
│
├── mlruns/
│
├── README.md
├── requirements.txt
│
└── .gitignore
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/your-username/rossmann-store-sales-forecasting.git
cd rossmann-store-sales-forecasting
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Running the Project

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open the notebook and execute all cells sequentially.

---

## Running MLflow

Launch the MLflow UI:

```bash
mlflow ui
```

Open in your browser:

```
http://127.0.0.1:5000
```

The dashboard allows you to:

- Compare model performance
- View evaluation metrics
- Inspect hyperparameters
- Download trained models
- View experiment artifacts

---

## Results

The performance of all models was compared using MAE, RMSE, and R² Score.

Among the evaluated models, **CatBoost Regressor** achieved the best forecasting performance and was selected as the final model.

---

## Future Enhancements

- TimeSeriesSplit cross-validation
- Bayesian hyperparameter optimization
- Additional holiday and seasonal features
- Deep learning models (LSTM, GRU)
- Model deployment using Flask/FastAPI
- Interactive dashboard using Streamlit

---

## Author

**Kshitij Mishra**

---

## License

This project is intended for educational and academic purposes.
