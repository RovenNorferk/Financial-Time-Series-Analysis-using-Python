# Financial Time Series Analysis Using Python

## Overview
This project focuses on analyzing financial time series data, specifically stock indices, to understand their returns and volatility. By employing various statistical modeling techniques, including ARMA, ARIMA, GARCH, and SARIMAX models, the analysis aims to identify patterns, make forecasts, and assess model performance.

## Key Steps in the Analysis

### 1. Data Loading and Preparation
- **Data Source**: Historical price data was retrieved for major stock indices, including the S&P 500, FTSE 100, Nikkei 225, and DAX, using the `yfinance` library.
- **Data Preparation**:
  - Percentage returns were calculated to represent the daily changes in price.
  - Data was split into training (80%) and testing (20%) sets, ensuring that the models were trained on historical data and validated on unseen data.

### 2. Statistical Tests and Visualizations
- **Stationarity Tests**: Conducted the Augmented Dickey-Fuller test to check for stationarity in the return series.
- **Autocorrelation Analysis**: Plotted the autocorrelation function (ACF) and partial autocorrelation function (PACF) to identify potential lags for ARMA models.
- **Residual Analysis**: Residuals from the fitted models were analyzed for patterns, ensuring that they resemble white noise.

### 3. Model Fitting
- **ARMA Models**: Different ARMA models (up to order 7) were fitted to the returns data. Likelihood ratio tests were performed to compare nested models and evaluate their significance.
- **ARIMA Models**: Used the `auto_arima` function from the `pmdarima` package to automatically determine the best-fitting ARIMA model, considering both non-seasonal and seasonal components. The best model identified was SARIMAX(2, 0, 2).
- **GARCH Models**: Explored GARCH models to analyze volatility. Various specifications were fitted, including GARCH(1,1), GARCH(1,2), and GARCH(2,1), with comparisons made based on AIC and BIC values.
- **VAR Models**: Implemented Vector Autoregression (VAR) to capture the interdependencies among multiple time series.

### 4. Model Evaluation
- **Goodness of Fit**: Evaluated models using AIC, BIC, and log-likelihood values, where lower values indicated better fit.
- **Significance of Coefficients**: Analyzed the statistical significance of the coefficients from the fitted models to assess their predictive capabilities.
- **Residual Diagnostics**: Conducted additional tests (Ljung-Box and Jarque-Bera) to check for autocorrelation and non-normality in residuals, leading to insights about model adequacy.

### 5. Volatility Forecasting
GARCH models were utilized to forecast future volatility, providing insights into market risk. The predicted volatility was plotted against actual returns for a visual assessment of model performance.

### 6. Results and Insights
- **Model Selection**: The SARIMAX model incorporating exogenous variables (like S&P 500 returns) significantly improved model fit, as indicated by lower AIC and BIC values.
- **Statistical Significance**: Many AR and MA coefficients were statistically significant, indicating that past return values influence future returns.
- **Non-Normal Residuals**: The Jarque-Bera test revealed non-normality in residuals, suggesting the need for further adjustments or alternative modeling approaches.

## Suggestions for Further Analysis
- **Model Comparison**: Implement criteria like cross-validation to select the best-performing model.
- **Residual Analysis**: Conduct thorough residual diagnostics to validate model assumptions.
- **Long-Term Forecasting**: Extend forecasting efforts beyond the test set to evaluate models' predictive power over time.
- **Hyperparameter Tuning**: Optimize ARIMA and GARCH models through hyperparameter tuning using automated libraries.
- **Inclusion of Economic Indicators**: Consider incorporating macroeconomic or sentiment indicators to enhance model explanations.
- **Robustness Checks**: Perform robustness checks to validate findings under different model specifications.
- **Machine Learning Approaches**: Explore machine learning models for potential comparisons with traditional time series methods.

## Conclusion
This analysis successfully applied various statistical models to assess financial time series data. The comprehensive evaluation of ARMA, ARIMA, GARCH, and SARIMAX models provided valuable insights into the dynamics of stock returns and volatility. The findings emphasize the importance of model selection, diagnostics, and validation in financial modeling.

## Technologies Used
- Python
- Libraries: `pandas`, `numpy`, `yfinance`, `statsmodels`, `pmdarima`, `arch`, `matplotlib`, `seaborn`
