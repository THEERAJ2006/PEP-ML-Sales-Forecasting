# Project 1 – Sales Forecasting Using Time Series

This project builds a time series forecasting model to predict future retail sales using historical monthly sales data. The objective is to understand the underlying trend and seasonality in sales and to forecast the next 12 months using a SARIMA time series model.

**Highlights:**
- Synthetic monthly sales data from 2018–2022 (60 data points).
- Upward trend plus clear yearly seasonality in sales.
- SARIMA \((1,1,1)(1,1,1,12)\) model trained and evaluated on 80%/20% time-based split.
- Evaluation metrics: MAE ≈ 80.8, RMSE ≈ 95.9 on the test period.
- 12‑month ahead forecast to support planning and decision making.

## Dataset

- Synthetic monthly sales data from Jan 2018 to Dec 2022 (60 months).
- Columns:
  - `date` – Month-end date (2018-01-31 … 2022-12-31)
  - `sales` – Total sales units/value for that month
- The series shows:
  - Upward trend from ~1100 to ~1900 units.
  - Clear yearly seasonality (some months consistently higher).

  ## Methodology

1. **Data Preparation**
   - Converted `date` to datetime.
   - Sorted by date and set `date` as the time index.
   - Fixed monthly frequency using `asfreq('M')`.

2. **Exploratory Data Analysis**
   - Line plot of monthly sales over time to inspect trend.
   - Boxplot of sales by month (1–12) to visualize seasonal pattern.

3. **Train–Test Split**
   - Chronological split: 80% train, 20% test (first 48 months train, last 12 months test).

4. **Model**
   - Time series model: SARIMA \((1,1,1)(1,1,1,12)\).
   - Trained on the training period only.
   - Forecasted sales for the test period and compared with actuals.

5. **Evaluation Metrics**
   - Mean Absolute Error (MAE): 80.78
   - Root Mean Squared Error (RMSE): 95.85

## Results

- The model captures both upward trend and yearly seasonality.
- Test-period performance:
  - **MAE ≈ 80.8**
  - **RMSE ≈ 95.9**
- Given average monthly sales around ~1500 units, these errors are reasonably small.

Key plots saved:
- `sales_over_time.png` – Monthly sales trend.
- `seasonality_boxplot.png` – Sales distribution by month.
- `forecast_test.png` – Train vs Test vs Forecast with confidence intervals.
- `forecast_next_12_months.png` – History plus 12‑month future forecast.


## Conclusion

- Monthly sales show a clear **upward trend** over the 5‑year period.
- There is strong **seasonality**, with certain months regularly showing higher sales.
- The SARIMA \((1,1,1)(1,1,1,12)\) model achieves MAE ≈ 80.8 and RMSE ≈ 95.9, indicating good forecast accuracy for this synthetic retail series.
- The 12‑month forecast continues the growth trend and repeats the seasonal pattern, which can be used for inventory and budgeting decisions.
- This project demonstrates a complete time series workflow: data preparation, EDA, model building, evaluation, and future forecasting.

## How to Run

1. **Clone or Download the Project**
   - Open a folder named `PEP-ML-Sales-Forecasting` on your system.
   - Place `sales_forecasting.ipynb` and this `README.md` inside it.

2. **Create and Activate Virtual Environment**

python -m venv .venv
..venv\Scripts\Activate.ps1 # PowerShell on Windows


3. **Install Dependencies**

python -m pip install --upgrade pip
python -m pip install pandas numpy matplotlib seaborn statsmodels scikit-learn


4. **Open Notebook**

- Open VS Code → File → Open Folder → select `PEP-ML-Sales-Forecasting`.
- Open `sales_forecasting.ipynb`.
- Select the `.venv` Python as the notebook kernel.

5. **Run the Project**

- Run all cells in order:
  - Data creation.
  - Time series preparation.
  - EDA plots.
  - Train/test split.
  - SARIMA model training.
  - Evaluation (MAE, RMSE).
  - 12‑month future forecast.

