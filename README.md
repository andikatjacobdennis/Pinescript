# Pine Script Trading Strategies

This repository contains various Pine Script strategies for TradingView. The strategies are implemented using Pine Script v5 and are designed for backtesting and live trading on the TradingView platform.

## Strategies

### Adaptive Reversal Strategy with Dynamic Stop Losses

This strategy aims to identify and trade reversals with dynamic stop loss levels. It includes configurable parameters for stop losses and trading hours, and adapts to market conditions by switching trades based on stop loss triggers.

#### Script Details

- **Strategy Name:** Adaptive Reversal Strategy with Dynamic Stop Losses
- **Version:** Pine Script v5
- **License:** Mozilla Public License 2.0 ([MPL 2.0](https://mozilla.org/MPL/2.0/))
- **Author:** andikatjacobdennis

#### Features

- **Dynamic Stop Losses:** Configurable stop loss values for long and short trades.
- **Trading Window:** Ability to set start and end times for trading.
- **Trade Switching:** Automatically switches trades between long and short positions based on stop loss triggers.

#### Parameters

- **Long Stop Loss (points):** The stop loss value for long trades (in points). Default is 1.
- **Short Stop Loss (points):** The stop loss value for short trades (in points). Default is 1.
- **Trade Start Hour:** The hour at which trading begins. Default is 9.
- **Trade Start Minute:** The minute at which trading begins. Default is 15.
- **Trade End Hour:** The hour at which trading ends. Default is 15.
- **Trade End Minute:** The minute at which trading ends. Default is 0.

#### How to Use

1. Copy the Pine Script code into the TradingView Pine Script editor.
2. Adjust the parameters as needed for your trading strategy.
3. Add the strategy to your TradingView chart and start backtesting or live trading.
