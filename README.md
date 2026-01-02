# NVIDIA Stock Price Prediction

Next-day closing price prediction for NVIDIA stock using machine learning regression models with feature engineering on historical OHLCV data (2019-2024).

## Project Overview

This project builds and evaluates multiple regression models to predict NVIDIA stock's next-day closing price using historical data:
- **Linear Regression** (baseline)
- **Ridge Regression** (with regularization)
- **Random Forest** (tree-based ensemble)

## Key Features

The project demonstrates:
- **Data preprocessing** and time-series formatting
- **Feature engineering**: moving averages (MA_5, MA_20), daily returns, volatility, lag features, volume change
- **Time-series train-test split** (80% historical, 20% test period)
- **Model comparison** using MAE and RMSE metrics
- **Evaluation plots**: actual vs predicted, error over time, residuals analysis

## Dataset

- **File**: `NVDIA.csv`
- **Time Period**: 2019-05-23 to 2024-05-23
- **Samples**: 1,260+ trading days
- **Features**: Open, High, Low, Close, Adjusted Close, Volume

## Results Summary

The model's predicted next-day prices stay almost flat while the actual prices rise sharply, showing that the model mostly predicts an average value and fails to follow real market movements.

## Files

- `nvidia_stock_price_prediction.ipynb` - Full Jupyter notebook with code, analysis, and plots
- `NVDIA.csv` - Historical OHLCV stock data
- `README.md` - This file

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/shifadilliyas/nvidia-stock-price-prediction.git
   cd nvidia-stock-price-prediction
   ```

2. Install dependencies:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
   ```

3. Open and run the Jupyter notebook:
   ```bash
   jupyter notebook nvidia_stock_price_prediction.ipynb
   ```

## Model Performance

Results on test set (last 20% of data):

| Model | Train MAE | Train RMSE | Test MAE | Test RMSE |
|-------|-----------|-----------|----------|----------|
| Linear Regression | Low | Low | Higher | Higher |
| Ridge | Low | Low | Higher | Higher |
| Random Forest | Very Low | Very Low | Higher | Higher |

*Note: See notebook for exact numeric values.*

## Limitations

- Stock prices are highly noisy and influenced by news, macro-economy, earnings announcements
- Simple pattern extrapolation fails during strong trends (underestimation in 2024)
- **This project is educational only and should NOT be used for trading decisions**
- Future price prediction is inherently uncertain; advanced models (LSTM, Transformers) may improve results but don't guarantee accuracy

## Learnings

1. Time-series data requires special handling (no shuffling, chronological split)
2. Feature engineering is crucial for model performance
3. Baseline comparisons help identify model improvements
4. Evaluation plots reveal failure modes better than metrics alone
5. Stock price prediction is complex and requires domain knowledge

## Author

Shifad Dilliyas | Data Science Student

## License

MIT License - feel free to use this project for learning purposes.
