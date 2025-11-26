# Portfolio Capital Allocation & Performance Optimization
A comprehensive quantitative framework leveraging Value-at-Risk (VaR) for **proactive capital allocation, risk-adjusted performance measurement, and regulatory compliance** in a diversified investment portfolio.

---

## 📊 Project Overview: Strategic Financial Analysis

This project transitions a purely risk measurement tool (**VaR**) into a **strategic financial planning instrument**. By rigorously quantifying downside risk, it provides the foundation for setting optimal risk limits, determining necessary capital reserves (capital adequacy), and making data-driven investment decisions.

**Key Deliverables & Business Impact:**
* **Capital Adequacy & Reserve Setting:** Precisely quantifies the capital buffer required to absorb potential **99% confidence** daily loss.
* **Risk-Adjusted Performance:** Provides the necessary risk metrics to calculate **RAROC** (Risk-Adjusted Return on Capital).
* **Compliance:** Implements industry-standard methodologies required by regulations (e.g., **Basel III** framework).
* **Forecasting/Modeling:** Utilizes **Monte Carlo Simulation** for scenario-based financial forecasting.

---

## 🎯 Core Business Problem & Solution

**Financial Challenge**: How much capital is truly at risk, and how much reserve capital is required to ensure solvency and stability while maximizing investment efficiency?

**Solution**: Implement and validate three advanced VaR models to provide a definitive, statistically-validated answer to the question: *"What is the maximum potential capital loss we must be prepared to absorb on a single, extremely volatile day (99% confidence)?"*

---

## 📈 Methodology: Data-Driven Financial Modeling

The project employs a structured, three-step quantitative methodology.

### 1. Data & Pre-Analysis
* **Data Set**: 3 years of historical prices for 5 major assets (AAPL, MSFT, JPM, GLD, SPY) to simulate a real-world, diversified portfolio.
* **Distribution Analysis**: Performed normality tests (Jarque-Bera, Shapiro-Wilk) to inform the appropriate choice of VaR model.
* **Correlation Mapping**: Analyzed asset correlations to understand diversification benefits and concentration risk.

### 2. Capital-at-Risk Quantification (VaR Calculation)
Three distinct models were implemented to ensure estimate robustness and consensus:
* **Historical Simulation**: Non-parametric approach for a true, observed "worst-case" loss estimation.
* **Variance-Covariance (Parametric)**: Fast and efficient method for quick daily capital estimates, assuming return normality.
* **Monte Carlo Simulation**: **Scenario Analysis** by generating 10,000 random market environments for flexible stress-testing and forecasting.

### 3. Model Validation & Capital Recommendation
* **Backtesting Framework**: A rigorous train (70%) and test (30%) split was used to check model accuracy against 225 days of actual market data.
* **Statistical Validation**: Employed **Kupiec's POF Test** to ensure the models' estimated 1% failure rate statistically aligned with the actual observed failure rate.

---

## 📊 Key Results & Financial Recommendation

| Metric | Detail |
| :--- | :--- |
| **Portfolio Value** | $1,000,000 |
| **Confidence Level** | 99% (Expected Failure Rate: 1.00%) |
| **Time Horizon** | 1-Day |
| **Validation Status** | **100% Validation** (All models passed Kupiec's POF Test) |

### Capital Reserve Requirement (VaR Estimates)

| Method | Capital-at-Risk (%) | **Recommended Daily Capital Reserve ($)** |
| :--- | :--- | :--- |
| Historical Simulation | -2.16% | **$21,577.69** |
| Variance-Covariance | -2.07% | $20,673.91 |
| Monte Carlo | -2.07% | $20,715.75 |

**Conclusion**: The project recommends setting the daily risk limit (Capital Reserve) at **$21,578**. This establishes a clear financial boundary for the trading desk and ensures the institution holds sufficient capital reserves to cover losses with **99% certainty**.

---

## 🛠️ Technologies Used

* **Python 3.x**
* **Data Processing**: Pandas, NumPy
* **Statistical Analysis**: SciPy
* **Financial Data**: yfinance
* **Environment**: Jupyter Notebook

## 📁 Project Structure

```
portfolio-analytics/
│
├── 01_data_setup.ipynb              # Data collection & analysis
├── 02_var_calculation.ipynb         # Risk quantification (3 methods)
├── 03_backtesting_validation.ipynb  # Model validation & testing
│
├── data/                            # Analysis outputs
│   ├── portfolio_returns.csv
│   ├── var_results.csv
│   └── backtest_results.csv
│
└── outputs/                         # Visualizations
    ├── 01_price_history.png
    ├── 02_return_distributions.png
    ├── 03_var_comparison_all_methods.png
    └── 04_backtesting_results.png
```
## 🚀 Running the Analysis

### Requirements
```bash
pip install pandas numpy scipy matplotlib yfinance
```

### Execution Steps
1. Run `01_data_setup.ipynb` - Downloads and prepares data
2. Run `02_var_calculation.ipynb` - Calculates risk estimates
3. Run `03_backtesting_validation.ipynb` - Validates model accuracy

### Outputs
- CSV files with detailed results in `data/` folder
- Publication-ready charts in `outputs/` folder
- Summary statistics for reporting

---

