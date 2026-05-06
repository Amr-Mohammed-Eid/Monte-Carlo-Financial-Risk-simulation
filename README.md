# Financial Risk Monte Carlo Simulation

This project models and simulates the Future expected prices of a stock portfolio consisting of Apple (AAPL), Microsoft (MSFT), and Google (GOOGL). By running Monte Carlo simulations based on Multi-Dimensional Geometric Brownian Motion (GBM), we estimate critical financial risk metrics:
- **Value at Risk (VaR)**
- **Expected Shortfall (ES) / Conditional Value at Risk (CVaR)**

## Project Structure

- `financial_risk_simulation.ipynb`: The main Jupyter Notebook combining the conceptual problem definition, Multi-Dimensional GBM mathematical foundations, model development, implementation, and visualized results (including a comprehensive tabular summary).
- `requirements.txt`: List of required Python dependencies.

## Setup and Execution

1. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Run the Notebook:**
   ```bash
   jupyter notebook financial_risk_simulation.ipynb
   ```

## Model Highlights
- Employs **yfinance** to pull historical market data.
- Employs **Cholesky Decomposition** to capture the covariance between different portfolio assets.
- Displays comprehensive plotting using **matplotlib** and **seaborn** for visualizing simulation spaghettis paths and final return distributions.
