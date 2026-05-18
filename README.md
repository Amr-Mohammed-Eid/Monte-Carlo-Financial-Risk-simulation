<div align="center">
  <h1>📈 Financial Risk Monte Carlo Simulation</h1>
  <p><strong>Advanced risk analysis and portfolio forecasting using Multi-Dimensional Geometric Brownian Motion (GBM)</strong></p>
</div>

<br />

## 📖 Overview

This project models and simulates the future expected prices of a stock portfolio consisting of **Apple (AAPL)**, **Microsoft (MSFT)**, and **Google (GOOGL)**. By leveraging historical market data and running robust Monte Carlo simulations, we estimate critical financial risk metrics that help in making informed investment decisions.

The core of this simulation relies on **Multi-Dimensional Geometric Brownian Motion (GBM)**, paired with **Cholesky Decomposition**, to accurately capture the correlation and covariance between different portfolio assets.

---

## 🧮 The Mathematical Model: Geometric Brownian Motion (GBM)

The Monte Carlo simulation is driven by the **Geometric Brownian Motion (GBM)** model. GBM is a continuous-time stochastic process in which the logarithm of the randomly varying quantity follows a Brownian motion (also called a Wiener process) with drift. 

### 1. Single Asset GBM
For a single asset, the stochastic differential equation (SDE) is defined as:

$$ dS_t = \mu S_t dt + \sigma S_t dW_t $$

Where:
- $S_t$ = Stock price at time $t$
- $\mu$ = Expected return (drift)
- $\sigma$ = Volatility (standard deviation of returns)
- $W_t$ = Standard Brownian motion (Wiener process)

### 2. Multi-Dimensional GBM (Portfolio Simulation)
Since our portfolio contains multiple correlated assets, we must model their paths jointly. We discretize the process using the exact solution to the SDE:

$$ S_i(t + \Delta t) = S_i(t) \exp\left[ \left( \mu_i - \frac{\sigma_i^2}{2} \right) \Delta t + \sigma_i \sqrt{\Delta t} Z_i \right] $$

Where $Z_i$ are correlated standard normal random variables. To generate these correlated variables $Z$, we apply **Cholesky Decomposition** to the covariance matrix of the assets' historical returns:

$$ \Sigma = L L^T $$

By multiplying independent standard normal random variables by the lower triangular matrix $L$, we introduce the correct historical correlation into our simulated price paths.

---

## 🎯 Key Risk Metrics

By generating thousands of potential future price paths, we construct a probability distribution of the portfolio's future value. From this distribution, we calculate:

- **Value at Risk (VaR):** The maximum expected loss over a specified time frame at a given confidence level (e.g., 95% or 99%).
- **Expected Shortfall (ES) / Conditional Value at Risk (CVaR):** The expected loss given that the VaR threshold has been breached. This provides a better understanding of tail risk.

---

## 🛠️ Technologies Used

- **Python 3.x**: Core programming language.
- **yfinance**: Automated extraction of historical market data from Yahoo Finance.
- **NumPy & Pandas**: Matrix operations, Cholesky decomposition, and data manipulation.
- **Matplotlib & Seaborn**: Comprehensive visualization of simulation "spaghetti" paths and final return distributions.
- **Jupyter Notebook**: Interactive environment for model development and execution.

---

## 📁 Project Structure

```text
├── financial_risk_simulation.ipynb   # Main Jupyter Notebook with mathematical foundations & visualizations
├── requirements.txt                  # Python dependencies
└── README.md                         # Project documentation
```

---

## 🚀 Setup and Execution

1. **Clone the repository** (if applicable) and navigate to the project directory:
   ```bash
   cd "Financial Risk Monte Carlo Sim"
   ```

2. **Install Dependencies:**
   Make sure you have Python installed, then run:
   ```bash
   pip install -r requirements.txt
   ```

3. **Launch the Simulation:**
   Start the Jupyter Notebook server to interact with the model:
   ```bash
   jupyter notebook financial_risk_simulation.ipynb
   ```

---

<div align="center">
  <p><i>Developed to demonstrate advanced financial modeling, stochastic processes, and risk management techniques.</i></p>
</div>
