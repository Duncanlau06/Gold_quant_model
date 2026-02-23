# Gold Quantitative Model

This project uses advanced machine learning techniques, specifically **XGBoost** and **Random Forest Classifiers**, to model and predict the price of Gold (GLD) based on macroeconomic data and technical indicators.

## Features & Methodology

The model analyzes gold prices by synthesizing various market drivers and employing robust statistical techniques:

### 1. Data Inputs & Feature Engineering
- **Diverse Data Sources**: Integrates historical price data from **Yahoo Finance** (GLD, USD Index, Treasury Yields, Volatility VIX/MOVE) and macroeconomic indicators from **FRED** (Fed Balance Sheet, CPI, Non-Farm Payrolls, GDP).
- **Signal Generation**: Creates specialized features such as **Real Yields** (Yield adjusted for inflation), **Liquidity Impulse** (Fed balance sheet log-returns), and **Market Stress** metrics.

### 2. Advanced Quant Pipeline
- **Multicollinearity Reduction**: Employs **Hierarchical Clustering** to group highly correlated features, ensuring the model's inputs are efficient and non-redundant.
- **Feature Selection**: Uses **Permutation Importance Analysis** to identify and rank the most predictive drivers, isolating robust signals from market noise.
- **Model Selection**: Combines the power of **Random Forest** for baseline importance and **XGBoost Classifier** for high-precision predictive modeling, specifically tuned to handle class imbalance in financial regimes.

### 3. Backtesting & Comparison
- **Strategy Comparison**: Evaluates model performance against a traditional **Buy and Hold** benchmark.
- **Dynamic Thresholding**: Implements a calibrated signal threshold to optimize the trade-off between precision and recall in a "Buy vs. No-Buy" classification setting.

---

## Project Structure

- `assets.ipynb`: The main research environment containing the full pipeline from clustering to backtesting.
- `.env`: Stores sensitive API keys (FRED).
- `.gitignore`: Prevents sensitive and temporary files from being tracked by Git.

---

## Setup & Installation

### 1. Configure API Keys
This project requires a FRED API key to pull macroeconomic data.

1.  Get a free key from [FRED](https://fred.stlouisof.org/docs/api/api_key.html).
2.  Create a `.env` file in the root directory.
3.  Add your key:
    ```text
    FRED_API_KEY=your_actual_api_key_here
    ```

### 2. Install Dependencies
Install the required Python libraries via pip:

```bash
pip install yfinance pandas pandas_datareader fredapi numpy matplotlib scikit-learn xgboost scipy python-dotenv
```

### 3. Running the Project
Open `assets.ipynb` and run the cells sequentially. The first cell contains a helper to ensure environment variables and dependencies are loaded correctly.
