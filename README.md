# Microsoft Stock Simulation Using Euler Discretisation and Monte Carlo Methods

This project analyzes Microsoft (MSFT) stock performance from 2000 to 2017 and uses historical data to model future price dynamics. The workflow includes calculating log returns, volatility, and simulating future stock prices using Monte Carlo methods combined with Euler–Maruyama discretisation. The project concludes by computing the expected payoff at maturity based on the simulated terminal prices in order to get the fair value of the call option.

## Project Overview

- Loaded and processed historical MSFT stock data using a CSV file
- Computed daily log returns 
- Estimated volatility from historical returns
- Simulated future stock paths using Monte Carlo simulation
- Implemented Euler discretisation for stochastic modeling under Geometry Brownian Motion (GBM)
- Visualized the first 10 of the 10,000 generated simulated paths on a graph
- Calculated the expected terminal payoff
- Discounted the expected terminal payoff to get the call option price C of today

## Technologies and Libraries

- Python 3
- NumPy for numerical computation
- Pandas for data handling and time-series operations
- Matplotlib for data visualization
- Jupyter Notebook for experimentation and documentation

## Methodology

- Daily log returns are computed as: log_returns = 1 + data.pct_change()

- Volatility (stdev) are estimated using the mean and standard deviation of historical log returns.

- Future price paths are generated via stochastic simulation.

- The discrete-time approximation of the stochastic differential equation under GBM is: $\mathrm{d}S_t = \mathrm{d}S_{t-1} . \exp((r - 0.5  \sigma^2)  \delta\_t + \sigma \sqrt{\mathrm{d}t}  Z_t)$ 

- The expected terminal payoff is obtained by averaging the payoff across all simulated price paths.

- The call option price is obtained by discounting the expected terminal payoff

## Conclusion

We noticed that the call option price obtained through Euler discretization under GBM was approximately similar to the one obtained using the Black-Scholes formula
