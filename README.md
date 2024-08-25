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

# Sideways Strategy with Thick Band

This Pine Script strategy, named "Sideways Strategy with Thick Band," is designed to identify potential trading opportunities during sideways market conditions using Bollinger Bands and the Relative Strength Index (RSI). The strategy aims to capitalize on price movements within a defined range and provides visual indicators on the TradingView chart.

## Features

- **Bollinger Bands**: Utilizes Bollinger Bands to define the trading range.
- **RSI**: Uses the Relative Strength Index to confirm overbought or oversold conditions.
- **Visual Indicators**: Plots Bollinger Bands and highlights the chart background when conditions for trading are met.
- **Trade Execution**: Executes long and short trades based on predefined conditions and manages positions with exit rules.

## Inputs

- **Bollinger Bands Length (`bb_length`)**: The number of periods used to calculate the Bollinger Bands' moving average. Default is `20`.
- **Bollinger Bands Multiplier (`bb_mult`)**: The multiplier used to determine the width of the Bollinger Bands. Default is `2.0`.
- **RSI Length (`rsi_length`)**: The number of periods used to calculate the RSI. Default is `14`.
- **RSI Overbought Level (`rsi_overbought`)**: The RSI value above which the market is considered overbought. Default is `70`.
- **RSI Oversold Level (`rsi_oversold`)**: The RSI value below which the market is considered oversold. Default is `30`.

## Strategy Logic

### Entry Conditions

- **Long Entry**: Initiated when the closing price is at or below the lower Bollinger Band and the RSI is below the oversold level.
- **Short Entry**: Initiated when the closing price is at or above the upper Bollinger Band and the RSI is above the overbought level.

### Exit Conditions

- **Long Exit**: Executed when the closing price is at or above the Bollinger Bands' basis or the RSI rises above 50.
- **Short Exit**: Executed when the closing price is at or below the Bollinger Bands' basis or the RSI falls below 50.

### Position Tracking

- **Long Active**: Indicates if a long position is currently active.
- **Short Active**: Indicates if a short position is currently active.

## Visualization

- **Bollinger Bands**:
  - **Upper Bollinger Band**: Plotted in red.
  - **Lower Bollinger Band**: Plotted in green.
  - **Basis**: Plotted in blue.
- **Background Color**: The background is shaded blue when the price is within the Bollinger Bands range and an order is active.

## Usage

1. Copy the Pine Script code into the TradingView Pine Script editor.
2. Add the strategy to your chart.
3. Adjust the input parameters as needed to fit your trading preferences.
4. Monitor the chart for potential trading signals and execute trades accordingly.
