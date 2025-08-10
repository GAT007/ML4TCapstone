# Machine Learning for Trading: Strategy Evaluation

This project, developed for the CS7646 course at Georgia Institute of Technology, implements and evaluates two distinct trading strategies: a manual strategy based on technical indicators and a Q-Learner strategy that uses reinforcement learning. The performance of these strategies is compared against a benchmark to assess their effectiveness.

The code for this project is available on request to adhere to integrity standards set by Gerogia Tech

## Description

The core of this project is the development and comparison of two trading approaches for the stock market.

1.  **Manual Strategy**: A rule-based trading strategy, which utilizes a combination of three technical indicators: Exponential Moving Average (EMA), Moving Average Convergence and Divergence (MACD), and Relative Strength Index (RSI). Decisions to go long or short are made based on the combined signals from these indicators.

2.  **Strategy Learner**: A strategy that employs a Q-Learner, a model-free reinforcement learning algorithm, to learn an optimal trading policy. The state is represented by discretized values of the same technical indicators (EMA, MACD, RSI), and the learner is rewarded based on the change in portfolio value.

The project includes two experiments to evaluate these strategies:

* **Experiment 1**: A direct comparison of the Manual Strategy and the Strategy Learner's performance on in-sample and out-of-sample data.

* **Experiment 2**: An analysis of how the market `impact` parameter affects the performance of the Q-Learner.

## Dependencies

The project is written in Python and requires the following libraries:

* pandas
* NumPy
* Matplotlib
* random
* datetime

  

## Files

* `ManualStrategy.py`: Implements the manual, rules-based trading strategy using EMA, MACD, and RSI indicators.
* `StrategyLearner.py`: Implements the Q-Learning based strategy learner. It uses a Q-Learner to train on historical data and make trading decisions.
* `QLearner.py`: Contains the implementation of the Q-Learner algorithm, including the logic for updating the Q-table and handling Dyna-Q.
* `indicators.py`: Provides functions to calculate the technical indicators used in the strategies, such as Bollinger Bands, MACD, RSI, and EMA.
* `marketsimcode.py`: A market simulator that takes a series of trades and computes the resulting portfolio value over time, accounting for commissions and market impact.
* `experiment1.py`: Code to run the first experiment, which compares the performance of the `ManualStrategy` and `StrategyLearner`.
* `experiment2.py`: Code to run the second experiment, which analyzes the effect of different market `impact` values on the `StrategyLearner`.
* `testproject.py`: The main script to run all experiments and generate comparison plots.

## How to Run

To run the project and execute the experiments, run the main test script from your terminal:

```bash
python testproject.py
```

This will run both experiments, generate performance statistics, and save the resulting plots to the `images/` directory.

## Future Work

While this project provides a solid foundation for comparing manual and machine learning-based trading strategies, several areas could be explored for future improvement:

* **Adaptive Indicator Weighting**: The manual strategy treats all indicators equally. Future work could involve implementing a machine learning approach to dynamically learn the optimal weights for each indicator based on changing market conditions.
* **Market Noise Resilience**: The current strategies could be sensitive to short-term market noise. Future iterations could explore techniques to improve resilience, such as incorporating more sophisticated filtering or confirmation signals.
* **Hyperparameter Optimization**: The Q-Learner's hyperparameters (alpha, gamma, rar, etc.) were chosen based on common practices. A more systematic approach, like grid search or Bayesian optimization, could be used to find the optimal set of hyperparameters for a given dataset.
* **Alternative Reinforcement Learning Models**: Explore more advanced reinforcement learning algorithms, such as Deep Q-Networks (DQN) or Actor-Critic models, which might be able to capture more complex market dynamics.
* **Expanded Feature Set**: Incorporate a wider range of technical indicators or even fundamental data (e.g., P/E ratios, sector news) into the state representation for the learner.
* **Portfolio Diversification**: The current strategies are tested on a single stock (JPM). Future work could expand the framework to manage a diversified portfolio of multiple assets, which would involve handling asset correlation and risk management.
