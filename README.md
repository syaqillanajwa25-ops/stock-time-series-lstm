# Stock Time Series Prediction using LSTM

A deep learning time-series forecasting project for predicting stock closing prices using Long Short-Term Memory (LSTM) neural networks.

The project explores stock price patterns for **Facebook (FB)** and **IBM**, applies proper time-series preprocessing, and compares multiple LSTM configurations to improve forecasting performance.

## Project Overview

The objective of this project is to predict the next closing price of a stock based on historical stock price observations.

Two stocks are analyzed:

- Facebook (FB)
- IBM

Because stock prices are sequential data, the dataset is processed chronologically without random shuffling to prevent future information from leaking into the training data.

## Time-Series Preprocessing

The forecasting pipeline includes:

- Chronological train-test splitting
- Close price extraction
- MinMax normalization
- Sliding-window sequence creation
- LSTM-compatible data reshaping
- Prediction inverse transformation

The project uses:

```text
Window Size = 5
Forecast Horizon = 1
```

This means the previous five observations are used to predict the next stock closing price.

## Preventing Data Leakage

The scaler is fitted only on the training data.

The same fitted scaler is then applied to validation and test data, preventing information from future observations from influencing model training.

## LSTM Model

Long Short-Term Memory networks are used because they are designed to learn patterns from sequential data.

The project develops and evaluates multiple LSTM configurations.

### Baseline LSTM

A baseline LSTM model is first trained to establish initial forecasting performance.

### Modified LSTM

The architecture and training configuration are then modified to improve prediction accuracy and generalization.

### Modified LSTM V2

A further improved LSTM configuration is evaluated as the final forecasting model.

## Model Evaluation

Forecasting performance is evaluated using:

- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- Mean Absolute Percentage Error (MAPE)

These metrics measure the difference between predicted stock prices and actual closing prices.

## Final Results

### Facebook (FB)

The final model achieved approximately:

```text
RMSE : 4.0572
MAE  : 2.7889
MAPE : 1.5117%
```

### IBM

The final model achieved approximately:

```text
RMSE : 2.6522
MAE  : 1.7092
MAPE : 1.3177%
```

The low MAPE values indicate that the final LSTM model was able to closely follow the overall stock price patterns in the test data.

## Project Workflow

```text
Historical Stock Data
        │
        ▼
Select Closing Price
        │
        ▼
Chronological Data Split
        │
        ▼
MinMax Scaling
        │
        ▼
Sliding Window Creation
        │
        ▼
LSTM Model
        │
        ▼
Model Improvement
        │
        ▼
Stock Price Prediction
        │
        ▼
Inverse Transformation
        │
        ▼
RMSE / MAE / MAPE Evaluation
```

## Project Structure

```text
stock-time-series-lstm/
│
├── 01_Stock_Time_Series_Prediction_LSTM.ipynb
├── project-report.pdf
└── README.md
```

## File Description

`01_Stock_Time_Series_Prediction_LSTM.ipynb`

Contains the complete time-series forecasting workflow, including:

- Data exploration
- Time-series preprocessing
- Data normalization
- Sliding-window sequence generation
- LSTM model development
- Model modification
- Stock price forecasting
- Prediction visualization
- Model evaluation

`project-report.pdf`

Contains the project documentation and analysis.

## Tech Stack

### Deep Learning

- TensorFlow
- Keras
- LSTM

### Data Processing

- Python
- Pandas
- NumPy
- Scikit-learn
- MinMaxScaler

### Visualization

- Matplotlib

### Development

- Jupyter Notebook
- Google Colab

## Key Features

- Stock price time-series forecasting
- LSTM neural networks
- Multiple stock datasets
- Chronological train-test splitting
- Data leakage prevention
- Sliding-window sequence creation
- Baseline and modified LSTM comparison
- RMSE, MAE, and MAPE evaluation
- Actual vs predicted price visualization

## Future Improvements

Possible improvements include:

- Use longer historical sequence windows
- Compare GRU and Bidirectional LSTM
- Incorporate additional stock indicators
- Add trading volume and technical indicators
- Explore Transformer-based forecasting models
- Perform more extensive hyperparameter tuning
- Develop an interactive stock forecasting dashboard
