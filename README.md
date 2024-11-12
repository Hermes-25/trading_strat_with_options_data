# trading_strat_with_options_data
# NIFTY BANK Options Trading Strategy

## Overview

This project is developed as part of the **Trading Strategy Challenge with Options Data**. The objective is to create an options trading strategy specifically focused on the NIFTY BANK index by utilizing historical **options price and volume data**. This strategy aims to optimize trading decisions by **extracting insights from options markets** and effectively implementing machine learning models for price prediction.

## Objectives

The key objectives of this project include:

1. **Data Acquisition and Preprocessing**: Loading, cleaning, and preprocessing historical options data for the NIFTY BANK index.
2. **Strategy Development**: Designing a robust trading strategy using mathematical and statistical models to generate buy/sell signals.
3. **Risk Management**: Implementing measures such as position sizing and stop-losses to limit market exposure and manage risk.
4. **Backtesting**: Evaluating the strategy's performance on historical data.
5. **Documentation**: Presenting the strategy's logic, rationale, and performance through charts, graphs, and detailed explanations.

## Installation

To run this project, make sure you have Python installed along with the required libraries:

```
pip install pandas numpy matplotlib scikit-learn py_vollib QuantLib xgboost tensorflow
```

## Data
The data used in this project consists of:

- Options Data: Detailed options price and volume data for various strike prices and expiration dates of the NIFTY BANK index.
- Index Data: Price-volume data for the NIFTY BANK index itself.

## Preprocessing Steps
  Handling missing data, splits, and adjustments.
  Converting columns to appropriate data types (e.g., dates, floats).
  Feature engineering to create indicators like Put-to-Call Ratio (PCR), implied volatility, option Greeks, and percentage change.
  Features
  Option Pricing: The Black-Scholes model is implemented to calculate theoretical option prices and implied volatility.
  Option Greeks: Key option Greeks like Delta, Gamma, Theta, Vega, and Rho are calculated to capture sensitivities.
  Additional Metrics: Derived metrics like exponential moving averages, PCR, and movement indicators enhance the model's predictive accuracy.

## Machine Learning Models
Multiple machine learning models are used to predict future price movements. This ensemble approach leverages each model's strengths, increasing overall predictive accuracy:

  Support Vector Machine (SVM): Classifies options based on past movements and feature values.
  Naive Bayes: A probabilistic classifier based on Bayes’ theorem.
  Random Forest: Constructs multiple decision trees for high accuracy and resistance to overfitting.
  XGBoost: Efficient gradient boosting algorithm, excellent for handling structured data.
  AdaBoost: Boosting algorithm that combines weak classifiers for stronger predictions.
  Logistic Regression: Estimates the probability of future price movements.
  Decision Tree: Simple, interpretable model for classification.
  K-Nearest Neighbors (KNN): Classifies based on the majority class of nearby points.

## Trading Strategy
- Logic and Signal Generation
    The strategy is based on ensemble predictions from the machine learning models, combined with signals derived from PCR and implied volatility indicators.

  Trade conditions are set up as follows:
    
    Buy Signal: Triggered when models forecast a rise in prices, supported by favorable PCR values and other indicators.
    Sell Signal: Triggered when models indicate a price drop, along with unfavorable PCR conditions.

- Strategy Execution
  The strategy buys or sells BANK NIFTY based on predictions, executing trades according to the generated signals, using rolling-window predictions to emulate real-time trading.

- Risk Management
  Effective risk management is critical in this strategy:
  
    Position Sizing: Limits exposure per trade to manage risk.
    Stop-Loss Orders: Automatically exits positions when losses exceed a predetermined threshold.
    Time-Based Stops: Limits the duration of exposure to prevent overexposure.
- Backtesting and Evaluation
  The strategy is backtested on historical data to simulate actual trading conditions. Key evaluation metrics include:
    
    Total Returns: Measures the absolute profitability of the strategy.
    Sharpe Ratio: Evaluates risk-adjusted returns, helping assess the strategy's robustness.
    Prediction Accuracy: The percentage of correct signals, indicating model effectiveness.
    Backtesting results are compared with a buy-and-hold approach to evaluate relative performance.

- Results
  The strategy's performance metrics, including cumulative returns, Sharpe ratio, and accuracy, are visualized through plots and charts. Key highlights:
  
  Portfolio Growth: Shows the portfolio's growth compared to a buy-and-hold strategy.
  Return Comparison: Demonstrates outperformance (or otherwise) relative to a baseline investment.
  Risk Profile: Illustrated by Sharpe ratio and maximum drawdowns, providing insight into the strategy's risk-adjusted effectiveness.

## Contributing
  Contributions to this project are welcome! If you’d like to improve the models, optimize the code, or add new features, please follow these steps:

## Fork the repository.
  Create a new branch (git checkout -b feature-branch).
  Make your changes and commit (git commit -am 'Add feature').
  Push to the branch (git push origin feature-branch).
  Create a new pull request.
  Please ensure your contributions follow best practices and add value to the project.

