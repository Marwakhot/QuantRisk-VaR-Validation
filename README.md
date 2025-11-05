# Value-at-Risk (VaR) Portfolio Risk Management System

A comprehensive implementation and validation of Value-at-Risk methodology for quantitative portfolio risk assessment.

---

## 📊 Project Overview

This project implements three industry-standard VaR methodologies to quantify the maximum potential loss for a diversified investment portfolio. The analysis includes rigorous statistical validation through backtesting and hypothesis testing to ensure model reliability.

**Key Features:**
- Three VaR calculation methods (Historical Simulation, Variance-Covariance, Monte Carlo)
- Statistical validation using Kupiec's Proportion of Failures (POF) test
- Comprehensive backtesting framework with train-test split
- Distribution analysis and normality testing
- Professional visualization and reporting

---

## 🎯 Business Problem

Financial institutions need to quantify potential losses to:
- Set appropriate risk limits
- Allocate capital reserves
- Comply with regulatory requirements (Basel III)
- Make informed investment decisions

**Question Answered**: *"What is the maximum amount we expect to lose on a bad day (with 99% confidence)?"*

---

## 📁 Project Structure

```
var-project/
│
├── 01_data_setup.ipynb              # Step 1: Data collection & preprocessing
├── 02_var_calculation.ipynb         # Step 2: VaR calculation (3 methods)
├── 03_backtesting_validation.ipynb  # Step 3: Model validation
│
├── data/                            # Generated data files
│   ├── cleaned_returns.csv
│   ├── cleaned_prices.csv
│   ├── var_results.csv
│   ├── portfolio_returns.csv
│   └── backtest_results.csv
│
├── outputs/                         # Visualization outputs
│   ├── 01_price_history.png
│   ├── 02_return_distributions.png
│   ├── 03_var_comparison_all_methods.png
│   └── 04_backtesting_results.png
│
└── README.md
```

---

## 🛠️ Technologies Used

- **Python 3.x**
- **Data Processing**: Pandas, NumPy
- **Statistical Analysis**: SciPy
- **Visualization**: Matplotlib
- **Financial Data**: yfinance
- **Environment**: Jupyter Notebook

---

## 📈 Methodology

### Step 1: Data Setup
- Downloaded 3 years of historical price data for 5 assets (AAPL, MSFT, JPM, GLD, SPY)
- Calculated daily returns
- Performed distribution analysis (histograms, Q-Q plots)
- Conducted normality tests (Jarque-Bera, Shapiro-Wilk)
- Analyzed correlations between assets

### Step 2: VaR Calculation
Implemented three VaR methodologies:

**1. Historical Simulation**
- Non-parametric approach using actual historical returns
- Finds 1st percentile of return distribution
- No distributional assumptions required

**2. Variance-Covariance (Parametric)**
- Assumes normal distribution of returns
- Formula: VaR = μ + σ × Z_α
- Fast and theoretically elegant

**3. Monte Carlo Simulation**
- Generates 10,000 random scenarios
- Uses historical mean and covariance
- Flexible for complex portfolios

### Step 3: Backtesting & Validation
- Split data: 70% training, 30% testing (225 days)
- Counted exceedances (days when actual loss > VaR)
- Performed Kupiec's POF test for statistical validation
- Compared expected vs actual failure rates

---

## 📊 Key Results

### Portfolio Configuration
- **Portfolio Value**: $1,000,000
- **Assets**: AAPL, MSFT, JPM, GLD, SPY (equal-weighted)
- **Confidence Level**: 99%
- **Time Horizon**: 1 day

### VaR Estimates (99% Confidence)
| Method | VaR (%) | VaR ($) |
|--------|---------|---------|
| Historical Simulation | -2.16% | $21,577.69 |
| Variance-Covariance | -2.07% | $20,673.91 |
| Monte Carlo | -2.07% | $20,715.75 |

### Validation Results
- **All three models passed** Kupiec's POF test (p-value = 1.0000)
- **Actual failure rate**: 2.22% vs Expected: 1.00%
- **Recommended Model**: Historical Simulation (most conservative)
- **Daily Risk Limit**: $21,577.69

---

## 💡 Key Insights

1. **Model Consensus**: All three methods produced similar estimates (range: $903.78), indicating robust risk measurement

2. **Statistical Validity**: 100% validation rate across all models demonstrates reliable VaR estimates

3. **Practical Application**: With 99% confidence, daily losses should not exceed $21,578 (approximately 2.16% of portfolio value)

4. **Expected Frequency**: VaR breach expected ~2-3 times per year (1% of ~252 trading days)

---

## 🚀 How to Run

### Prerequisites
```bash
pip install pandas numpy scipy matplotlib yfinance
```

### Execution
Run notebooks in sequence:

1. **Step 1 - Data Setup**
   ```bash
   jupyter notebook 01_data_setup.ipynb
   ```
   - Downloads historical data
   - Generates: `cleaned_returns.csv`, `cleaned_prices.csv`

2. **Step 2 - VaR Calculation**
   ```bash
   jupyter notebook 02_var_calculation.ipynb
   ```
   - Calculates VaR using three methods
   - Generates: `var_results.csv`, `portfolio_returns.csv`

3. **Step 3 - Backtesting**
   ```bash
   jupyter notebook 03_backtesting_validation.ipynb
   ```
   - Validates models
   - Generates: `backtest_results.csv`, visualizations
---

## 📄 License

This project is for educational purposes. Data sourced from Yahoo Finance via yfinance library.

---


---

**⭐ If you found this project helpful, please consider giving it a star!**
