Comprehensive tutorial for Pine Script on TradingView:

---

# Pine Script Tutorial

## 1. Introduction to Pine Script

### What is Pine Script?
Pine Script is a domain-specific language created by TradingView for writing custom technical analysis studies and trading strategies. It allows traders to build and test their own indicators and strategies directly on the TradingView platform. 

### Overview of Pine Script's Capabilities
Pine Script provides powerful tools to:
- Create custom indicators and strategies.
- Visualize data with custom plots.
- Backtest trading strategies with historical data.
- Generate alerts and notifications.

### Setting Up Your TradingView Account
To start using Pine Script:
1. **Sign Up**: Create an account on TradingView if you don't already have one.
2. **Log In**: Access your account using your credentials.
3. **Open the Pine Script Editor**: Click on the 'Pine Editor' tab at the bottom of your TradingView chart.

## 2. Getting Started with Pine Script

### Accessing the Pine Script Editor
1. **Navigate to TradingView**: Open TradingView and select any chart.
2. **Open Pine Editor**: Click on the 'Pine Editor' tab located at the bottom of the TradingView interface.

### Basic Syntax and Structure
Pine Script follows a straightforward syntax. Here’s a basic structure:
```pinescript
//@version=5
indicator("My Script", overlay=true)
plot(close)
```
- `//@version=5`: Specifies the version of Pine Script.
- `indicator("My Script", overlay=true)`: Defines the indicator name and whether it overlays on the main chart.
- `plot(close)`: Plots the closing price.

### Writing Your First Script: A Simple Moving Average
```pinescript
//@version=5
indicator("Simple Moving Average", overlay=true)
length = input(14, title="Length")
sma = ta.sma(close, length)
plot(sma, color=color.blue, title="SMA")
```
- `input(14, title="Length")`: Allows users to set the period for the SMA.
- `ta.sma(close, length)`: Calculates the Simple Moving Average.
- `plot(sma, color=color.blue, title="SMA")`: Plots the SMA on the chart.

## 3. Pine Script Basics

### Variables and Data Types
Pine Script supports various data types:
- **Integers**: Whole numbers.
- **Floats**: Decimal numbers.
- **Strings**: Text.
- **Booleans**: `true` or `false`.

Example:
```pinescript
length = input.int(14, title="Length")  // Integer
factor = input.float(1.5, title="Factor")  // Float
```

### Operators and Expressions
Operators include:
- **Arithmetic**: `+`, `-`, `*`, `/`
- **Relational**: `==`, `!=`, `>`, `<`
- **Logical**: `and`, `or`, `not`

Example:
```pinescript
value = close > sma ? high : low
```

### Functions and Procedures
Functions perform operations and return values.
Example:
```pinescript
fibonacciRetracement(x) =>
    // Function to calculate Fibonacci levels
    [0.382, 0.618] * x
```

## 4. Plotting and Visualizing Data

### Using `plot()`, `plotshape()`, and `plotarrow()`
- **`plot()`**: Draws lines or shapes on the chart.
- **`plotshape()`**: Plots shapes like circles or triangles.
- **`plotarrow()`**: Plots arrows to indicate trends or signals.

Example:
```pinescript
plot(close, color=color.blue)
plotshape(series=close > sma, location=location.belowbar, color=color.green, style=shape.labelup, text="Buy")
plotarrow(series=close - sma)
```

### Customizing Plots: Colors, Styles, and Widths
You can customize plots with attributes like `color`, `style`, and `linewidth`.
Example:
```pinescript
plot(sma, color=color.red, style=plot.style_linebr, linewidth=2)
```

### Adding Labels and Text
Use `label.new()` to add text labels to your chart.
Example:
```pinescript
if (close > sma)
    label.new(bar_index, high, "Above SMA", color=color.green, textcolor=color.white)
```

## 5. Working with Indicators

### Built-in Indicators: Overview and Usage
Pine Script provides numerous built-in indicators such as Moving Averages, RSI, MACD, etc. You can apply them directly or use their code to create custom variations.

### Creating Custom Indicators
Example of a custom RSI indicator:
```pinescript
//@version=5
indicator("Custom RSI", overlay=true)
length = input(14, title="Length")
rsi = ta.rsi(close, length)
plot(rsi, color=color.blue)
```

### Combining Multiple Indicators
Example:
```pinescript
//@version=5
indicator("Combined Indicators", overlay=true)
sma = ta.sma(close, 14)
rsi = ta.rsi(close, 14)
plot(sma, color=color.red)
plot(rsi, color=color.blue)
```

## 6. Strategy Development

### Introduction to Pine Script Strategies
Strategies allow you to define and test trading rules.

### Writing and Testing Basic Strategies
Example:
```pinescript
//@version=5
strategy("Basic Strategy", overlay=true)
sma = ta.sma(close, 14)
if (close > sma)
    strategy.entry("Buy", strategy.long)
else
    strategy.close("Buy")
```

### Using `strategy.entry()`, `strategy.exit()`, and `strategy.close()`
- **`strategy.entry()`**: Places a trade order.
- **`strategy.exit()`**: Closes an open trade.
- **`strategy.close()`**: Closes a position.

Example:
```pinescript
strategy.entry("Buy", strategy.long)
strategy.exit("Sell", from_entry="Buy", profit=10, loss=5)
```

## 7. Advanced Pine Script Features

### Working with Timeframes and Historical Data
You can access different timeframes and historical data using functions like `request.security()`.
Example:
```pinescript
security(syminfo.tickerid, "D", close)
```

### Creating Alerts and Notifications
Use `alertcondition()` to create alerts.
Example:
```pinescript
alertcondition(close > sma, title="Price Above SMA", message="Price has crossed above SMA")
```

### Handling Multiple Timeframe Analysis
Example:
```pinescript
sma_1h = request.security(syminfo.tickerid, "60", ta.sma(close, 14))
plot(sma_1h, color=color.red)
```

## 8. User Inputs and Customization

### Using `input()` Functions for User Customization
Create user inputs for customization.
Example:
```pinescript
length = input.int(14, title="Length")
```

### Creating Interactive Scripts with Input Fields
Add interactive elements using `input()` functions.
Example:
```pinescript
show_sma = input(true, title="Show SMA")
if show_sma
    plot(sma, color=color.blue)
```

### Building Custom Settings Panels
Example:
```pinescript
length = input.int(14, minval=1, title="SMA Length")
```
