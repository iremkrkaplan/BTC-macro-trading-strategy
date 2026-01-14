# BTC Macro Trading Strategy - Event-Driven Analysis

A sophisticated algorithmic trading strategy for BTC/USDT that leverages macroeconomic event data to capitalize on market volatility surrounding major U.S. economic indicators.

## Project Overview

This project implements an event-driven trading system that combines macroeconomic event timing with technical analysis indicators to generate trading signals for Bitcoin. The strategy is designed to enter and exit positions based on the expected impact of economic data releases, using a dual-indicator confirmation system for signal validation.

## Key Features

- **Event-Driven Timing Strategy**: Adaptive entry/exit timing based on event impact classification
- **Multi-Indicator Confirmation**: Combines momentum (RSI) and trend (Supertrend) indicators for robust signal generation
- **Comprehensive Backtesting Framework**: Full historical performance analysis with detailed metrics
- **Macroeconomic Event Integration**: Tracks CPI, Fed Rate, Nonfarm Payrolls, Unemployment, and Jobless Claims
- **Performance Analytics**: Advanced trade statistics including win rate, ROI, and risk metrics

## Strategy Architecture

### Entry & Exit Timing

The strategy employs an **Event-Type Based Approach** that adapts timing based on the expected market impact:

- **High-Impact Events** (CPI, Fed Rate, Nonfarm Payrolls, Unemployment)
  - Entry: 2 days before event release
  - Exit: 2 days after event release

- **Medium-Impact Events** (Jobless Claims)
  - Entry: 1 day before event release
  - Exit: 1 day after event release

### Signal Generation

**Multiple Indicator Confirmation** approach ensures high-quality trade entries:

**Trading Rules:**
- **RSI < 44**: Relative Strength Index must indicate oversold conditions
- **Close Price > Supertrend**: Price must be above the Supertrend line, confirming bullish trend

Both conditions must be satisfied simultaneously to generate a BUY signal, ensuring confirmation from both momentum and trend perspectives.

### Parameter Optimization

The RSI threshold was optimized from the standard oversold level (< 30) to < 44 to meet the minimum trade requirement while maintaining the strategy's core logic. This adjustment increases sensitivity to buying opportunities while preserving the dual-confirmation framework.

## Getting Started

### Prerequisites

- Python 3.7+
- Jupyter Notebook
- Binance API credentials (optional, for live data)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/btc-macro-trading-strategy.git
cd btc-macro-trading-strategy
```

2. Install dependencies:
```bash
pip install pandas python-binance ta jupyter
```

3. Configure API keys (if using live data):
   - Open the notebook
   - Update the `api_key` and `api_secret` variables in the first cell

4. Run the Jupyter notebook:
```bash
jupyter notebook İremKarakaplan_BTC_Trading_Quiz.ipynb
```

## Performance Results

The strategy has been backtested with the following performance metrics:

- **Total Trades Executed**: 12
- **Win Rate**: 41.67%
- **Total Return**: 6.99% ROI
- **Starting Capital**: $10,000 USDT
- **Final Balance**: $10,699.33 USDT
- **Average P/L per Trade**: $58.28 USDT
- **Best Trade**: $1,153.38 USDT profit
- **Worst Trade**: -$538.88 USDT loss

### Advanced Metrics

- Average entry timing: 1.67 days before event
- Average exit timing: 1.67 days after event
- Most profitable indicator combination: RSI + Supertrend

## Project Structure

```
btc-macro-trading-strategy/
├── İremKarakaplan_BTC_Trading_Quiz.ipynb  # Main trading strategy notebook
├── macro_economics_data.txt                # Macroeconomic event data
├── README.md                              # Project documentation
└── .gitignore                             # Git ignore rules
```

## Dependencies

- **pandas** (>=1.5.0): Data manipulation and analysis
- **python-binance** (>=1.0.19): Binance API integration for market data
- **ta** (>=0.11.0): Technical analysis indicators library
- **jupyter** (>=1.0.0): Interactive notebook environment

## Methodology

### Event Classification

The strategy monitors five key macroeconomic indicators:

1. **CPI (Consumer Price Index)**: Monthly inflation data
2. **Fed Rate**: Federal Reserve interest rate decisions
3. **Nonfarm Payrolls**: Monthly employment report
4. **Unemployment Rate**: Monthly unemployment statistics
5. **Jobless Claims**: Weekly unemployment claims

### Technical Indicators

- **RSI (Relative Strength Index)**: Momentum oscillator identifying overbought/oversold conditions
- **Supertrend**: Trend-following indicator based on ATR (Average True Range)

### Risk Management

- Position sizing based on available capital
- Stop-loss and take-profit levels determined by event timing
- Maximum position exposure limits

## Disclaimer

This project is for educational and research purposes only. Past performance does not guarantee future results. Cryptocurrency trading involves substantial risk of loss. Always conduct thorough testing and risk assessment before deploying any trading strategy with real capital.

## License

This project is provided as-is for educational purposes.

## Author

İrem Karakaplan

## Acknowledgments

- Binance API for market data access
- Technical analysis library contributors
- Macroeconomic data sources
