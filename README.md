
# Quantitative Strategy Repository

Welcome to the Quantitative Strategy Repository! This repository contains various quantitative strategies and their implementations, with a particular focus on mean-variance optimization and long-short equity strategies. This repository is currently a work in progress, and I am continuously updating/editing it to improve clarity with deeper research and new strategies.

## Table of Contents

- [Projects](#projects)
  - [Mean-Variance Optimization and Backtesting](#mean-variance-optimization-and-backtesting)
  - [Long-Short Strategy Research](#long-short-strategy-research)
- [About Me](#about-me)
- [License](#license)
- [Disclaimer](#disclaimer)

## Projects

### [Mean-Variance Optimization and Backtesting](./Portfolio_Optimization.ipynb)
This project involves the implementation of mean-variance optimization, a foundational concept in modern portfolio theory. It includes backtesting to evaluate the performance of the optimized portfolios over historical data.

### [Long-Short Strategy Research](./Strategy_Factors_Formation.ipynb)
This project explores long-short equity strategies, including the formation and backtesting of over 10 different strategies across historical data. Key aspects of this research include:
- **Factor Combination**: Mixing different signals for strategy formation to enhance performance and robustness.
- **Machine Learning/Deep Learning Methodology**: Incorporating advanced machine learning and deep learning techniques to develop and improve long-short strategies.
- **Signal Robustness Analysis**: Analyzing the robustness of signals, which may affect portfolio turnover.
- **Visualization**: Providing visualizations to illustrate the performance and characteristics of the strategies.

**Note:** Individual files for each strategy will be uploaded in the future to enhance clarity and organization.

Future updates will include deeper research into individual strategies and the addition of new strategies.

### Illustration of Momentum Strategy

For this momentum strategy, I excluded stocks with a P/E ratio less than 5 to avoid valuation traps. The data used is sourced from CRSP and COMPUSTAT, spanning from 1970 to 2023. Financial data is annual and lagged by 6 months.

The momentum signal is generated using returns from the -12 to -2 month period, excluding the -1 month return to avoid the short-term reversal effect, as identified by Jegadeesh (1989).

#### Factor's Return (Momentum)
![Factor's Return (momentum)](/momentum_illustration_graphs/factor_return.png)
*Note: Grey areas represent recession periods.*

#### Factor's Holding Period Return
![Factor's Holding Period Return](/momentum_illustration_graphs/factor_hpr.png)
*The blue line represents the holding period return since 3 months prior, while the orange line represents the holding period return since 1 year prior.*

#### Performance of Each Portfolio ($1 Invested)
![Performance of Each Portfolio ($1 Invested)](/momentum_illustration_graphs/decile_performance.png)
*This graph demonstrates whether the decile portfolios diverge over different time periods. A robust strategy should exhibit significant divergence in the performance of each decile portfolio, indicating that the signal or feature used has consistent predictive power. Note that we are long on the top decile and short on the bottom decile. The momentum signal and strategy rebalancing are updated monthly.*

#### Transition Matrix of Rankings
![Transition Matrix of Rankings (1 Month)](/momentum_illustration_graphs/transition_matrix.png)
*These graphs illustrate the transition matrices for rankings 1 month, 3 months, and 6 months prior. A strong signal should display higher brightness along the diagonal, indicating stability in rankings and consequently lower turnover and transaction costs.*

#### Signal Robustness and Decay (Momentum)
![Signal Robustness (momentum)](/momentum_illustration_graphs/signal_robustness.png)
*The left graph shows the historical average persistence rate of each decile portfolio across calendar months to examine if the signal's strength varies by month. The high persistence rate for the top and bottom portfolios indicates lower turnover and transaction costs. The right graph plots the expected persistence rate based on the transition matrix, showing the probability of a stock remaining in the same decile ranking after a certain number of months.*

#### Historical Signal Persistence Rate (Momentum)
![Historical Signal Persistence Rate (momentum)](/momentum_illustration_graphs/persistance_rate.png)
*This graph depicts the historical persistence rates for the top and bottom deciles to assess whether the signal's strength varies with economic conditions. For momentum, the persistence rate tends to drop during economic downturns, highlighting potential vulnerabilities.*

## About Me
[Provide details about yourself, your background, and your interest in quantitative finance.]

## License
[Provide the licensing information for the repository.]

## Disclaimer
[Include any disclaimers regarding the use of the information and strategies in this repository.]
