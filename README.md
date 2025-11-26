# Portfolio Performance & Risk Analytics

A data-driven framework for investment portfolio analysis, quantifying downside risk and supporting strategic financial decision-making.

---

## 📊 Project Overview

This project analyzes a $1M diversified investment portfolio using statistical methods to answer critical business questions: **How much could we lose on a bad day?** and **Are our risk estimates reliable?**

The analysis combines historical data analysis, statistical modeling, and rigorous validation to provide actionable insights for investment decisions and capital allocation.

**Key Deliverables:**
- Quantified maximum daily loss at 99% confidence level
- Validated risk estimates using statistical testing
- Comparative analysis across three analytical approaches
- Data-driven recommendations for risk management

---

## 🎯 Business Context

**Objective**: Provide finance leadership with reliable estimates of potential portfolio losses to support:
- Capital budgeting and reserve planning
- Investment strategy decisions
- Performance benchmarking
- Stakeholder reporting

**Core Question**: *"What's the worst-case daily loss we should prepare for with 99% confidence?"*

---

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

---

## 🔍 Analytical Approach

### Phase 1: Data Analysis
- Collected 3 years of daily pricing data for 5-asset portfolio (Tech, Financial, Commodity, Index)
- Calculated daily returns and analyzed statistical properties
- Assessed correlations to understand diversification benefits
- Tested distribution assumptions using normality tests

### Phase 2: Risk Quantification
Applied three complementary methodologies:

**1. Historical Analysis**
- Used actual past performance (percentile-based)
- No assumptions about future distributions
- Most conservative estimate: captures real market behavior

**2. Statistical Model (Variance-Covariance)**
- Assumes normal distribution of returns
- Leverages mean and standard deviation
- Fast, efficient for ongoing monitoring

**3. Monte Carlo Simulation**
- Generated 10,000 potential scenarios
- Incorporates portfolio correlations
- Robust for complex portfolio structures

### Phase 3: Validation & Testing
- Tested model accuracy using 225-day holdout period
- Counted actual vs. expected threshold breaches
- Performed statistical hypothesis testing (Kupiec test)
- Validated reliability at 99% confidence level

---

## 📈 Key Findings

### Portfolio Specifications
- **Portfolio Value**: $1,000,000
- **Assets**: AAPL, MSFT, JPM, GLD, SPY (20% each)
- **Analysis Period**: 3 years (2022-2024)
- **Confidence Level**: 99%

### Risk Estimates

| Method | Daily Loss Estimate | % of Portfolio |
|--------|---------------------|----------------|
| Historical Analysis | $21,578 | 2.16% |
| Statistical Model | $20,674 | 2.07% |
| Monte Carlo | $20,716 | 2.07% |

**Range**: $904 (4% variance across methods)

### Validation Results
- ✅ **All models passed statistical validation** (p-value = 1.0000)
- **Actual exceedances**: 5 days out of 225 (2.22%)
- **Expected exceedances**: 2-3 days (1.00%)
- **Interpretation**: Models slightly underestimated risk but within acceptable range

---

## 💡 Business Insights & Recommendations

### 1. **Risk Quantification**
With 99% confidence, daily losses should not exceed **$21,578** (2.16% of portfolio value)

### 2. **Frequency Expectation**
Expect to breach this threshold ~2-3 times per year under normal market conditions

### 3. **Model Selection**
**Recommend**: Historical Analysis method ($21,578)
- Most conservative estimate
- No distributional assumptions
- Passed validation testing
- Better captures tail risk

### 4. **Capital Planning**
Set daily risk limit at **$22,000** with escalation protocols if breached

### 5. **Monitoring Framework**
- Track daily P&L against threshold
- Review models quarterly with updated data
- Flag consecutive breaches for investigation

---

## 🛠️ Technical Skills Demonstrated

- **Data Analysis**: Python (Pandas, NumPy) for financial data processing
- **Statistical Methods**: Hypothesis testing, distribution analysis
- **Financial Modeling**: Multiple VaR methodologies, Monte Carlo simulation
- **Data Visualization**: Matplotlib for executive-ready charts
- **Validation**: Backtesting framework, model accuracy assessment

---

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

## 📌 Use Cases

This analytical framework can be applied to:
- **Investment Portfolio Monitoring**: Daily risk tracking
- **Capital Allocation**: Setting position limits
- **Performance Reporting**: Communicating risk to stakeholders
- **Scenario Analysis**: Stress testing portfolio under different conditions
- **Benchmarking**: Comparing actual vs. expected performance

---

## 🎓 Key Takeaways

1. **Data-Driven Decision Making**: Used 3 years of data to quantify risk objectively
2. **Model Validation**: Didn't just calculate numbers—proved they're reliable through testing
3. **Practical Application**: Translated statistical analysis into actionable business recommendations
4. **Comprehensive Approach**: Combined multiple methods for robust conclusions
5. **Clear Communication**: Presented complex analytics in business-friendly format
