
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

The following graph displays the algorithm's decisions regarding portfolio weights over time.
![mvo](/mvo_illustration_graphs/weights_across_time.png)

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

#### Strategy Statistics
![Strategy Statistics](/momentum_illustration_graphs/strategy_statistics.png)
*Description: The left-hand side table exhibits the statistics of this strategy. The mean return (monthly) of this strategy is 1.03%. It also shows that even a simple momentum strategy has an annualized Sharpe ratio of 0.8. The t-statistic of 5.88 indicates that this strategy has returns statistically significant from 0.*

*On the right-hand side, it showcases the statistics for each decile portfolio. Q10 is the portfolio of stocks with the top 10% momentum, rebalanced monthly, and Q1 is the portfolio of stocks with the bottom 10% momentum, rebalanced monthly. As the decile increases, the mean return consistently increases from 0.6% (monthly) for the bottom decile to 1.6% (monthly) for the top decile. Note: 'count' refers to the sample size, 635 months of U.S. stock data.*

*The long/short strategy here involves longing the top decile and shorting the bottom decile.*

#### Performance During Recession and Non-Recession Periods
![Performance During Recession and Non-Recession Periods](/momentum_illustration_graphs/performance_periods.png)
*Description: This table examines the strategy's performance during the recession and non-recession periods. The first column shows the specific date range, 'count' is the sample size (months) during that period, and all statistics are calculated using monthly data. For example, from 1971-01 to 1973-10, the momentum strategy had a mean monthly return of 2.29% and an annualized Sharpe ratio of 1.46. The statistics starting from 'α' show the results of regressing the strategy's return on market excess return, indicating alpha, the p-value of alpha, market beta, the p-value of market beta, and the R-squared of the regression.*

*Higher alpha indicates a better strategy and a lower p-value signifies the statistical significance of the alpha. Market beta refers to the strategy's sensitivity to market movements. For instance, from 1971-01 to 1973-10, if the market dropped by 1%, the strategy's average return would be 0.76%. The max drawdown represents the maximum cumulative loss during that period (9.98% for this instance).*

*This method allows us to examine how the strategy performs across different periods.*




#### Factor's Return (Momentum)
![Factor's Return (momentum)](/momentum_illustration_graphs/factor_return.png)
*Note: Grey areas represent recession periods.*

#### Factor's Holding Period Return
![Factor's Holding Period Return](/momentum_illustration_graphs/factor_hpr.png)
*The blue line represents the holding period return since 3 months prior, while the orange line represents the holding period return since 1 year prior.*

#### Performance of Each Portfolio ($1 Invested)
![Performance of Each Portfolio ($1 Invested)](/momentum_illustration_graphs/decile_performance.png)
*This graph demonstrates whether the decile portfolios diverge over different periods. A robust strategy should exhibit significant divergence in the performance of each decile portfolio, indicating that the signal or feature used has consistent predictive power. Note that we are long on the top decile and short on the bottom decile. The momentum signal and strategy rebalancing are updated monthly.*

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
I am a Master's student in Quantitative Finance with dual bachelor's degrees in Science and Business Administration. My academic focus includes artificial intelligence, statistics, and finance. Most of the projects in this repository are related to the application of machine learning and deep learning in Quantitative Finance, although some are dedicated to exploring the methodologies themselves. Visit my [personal website](https://justinyuchi.github.io/justinyuchihsu.github.io/) for more about my work and interests.


## License
This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Disclaimer
Disclaimer
The information provided in this repository is for educational and informational purposes only. It is not intended to be investment advice, and you should not rely on it as such. The strategies and analyses presented are based on historical data and hypothetical performance, which have inherent limitations. Past performance is not indicative of future results.

For the full disclaimer, please refer to the [DISCLAIMER.md](./DISCLAIMER.md) file.
