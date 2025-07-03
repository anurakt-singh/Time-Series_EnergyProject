# PJME Energy Use Prediction with XGBoost

This project uses XGBoost to predict PJME (PJM East) energy usage based on historical data.

## Setup

### Dependencies

* Python 3.x
* Required packages:

  * pandas
  * numpy
  * matplotlib
  * seaborn
  * xgboost
  * scikit-learn

### Installation

1. Clone the repository:

   ```bash
   git clone <repository-url>
   ```
2. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

### Data

* Dataset: `AEP_hourly.csv`
* Location: `/content/` directory
* Columns:

  * `Datetime`: Timestamp of the energy record
  * `PJME_MW`: Energy use in Megawatts

## Usage

### 1. Data Exploration

* Plot overall energy usage
* Split data into training and testing sets (cut-off: Jan 1, 2015)
* Visualize a specific week of data

### 2. Feature Engineering

* Create time-based features:

  * Hour
  * Day of the week
  * Quarter
  * Month
  * Year
  * Day of year
  * Day of month
  * Week of year
* Visualize distribution of energy usage by hour and month

### 3. Model Creation

* Model: XGBoost Regressor
* Parameters:

  * `base_score=0.5`
  * `booster='gbtree'`
  * `n_estimators=1000`
  * `learning_rate=0.01`
  * `max_depth=3`
  * `early_stopping_rounds=50`
  * `objective='reg:linear'`

### 4. Model Training and Evaluation

* Train the model using the defined features
* Validate using test data
* Evaluate performance using RMSE (Root Mean Squared Error)

### 5. Results

* Plot feature importance
* Compare actual vs. predicted values (full data and selected week)
* Calculate RMSE score
* Identify top 10 days with the highest average prediction error

## Output Example

```
RMSE Score on Test set: <value>
Top 10 error dates:
<date>: <average error>
...
```

## Future Improvements

* Tune hyperparameters using cross-validation
* Add more external data like weather for better predictions
* Deploy model for real-time forecasting

---

