# 🧠 Comprehensive Trading Indicator for TradingView
### All-in-One Chart Toolkit (Pine Script v6) | MA Group + Vegas + ZigZag + RSI Divergence + MTF S/R + Range Boxes + Alerts

> A **comprehensive all-in-one TradingView chart indicator**.  
> It combines common trend, structure, momentum, and support/resistance tools into one script, including **MA group / Vegas tunnel / ZigZag + Fibonacci / RSI divergence / multi-timeframe support & resistance / range box detection / ATR references / info table / multi-module alerts**, helping you reduce indicator switching and improve chart workflow efficiency.

---

## ✨ Features

### 🔹 1) 📊 MA Group (up to 4 lines)
- Supports up to 4 independently switchable moving averages
- Each MA is configurable with:
  - Type: `SMA / EMA / SMMA (RMA) / WMA / VWMA`
  - Source
  - Length
  - Color
- Includes MA bullish / bearish alignment detection

---

### 🔹 2) 🌈 Vegas Line Group (up to 5 lines)
- Built-in multi-line Vegas-style moving averages (with common default lengths)
- Each Vegas line supports:
  - MA type
  - Source
  - Length
  - Color
- Includes **Vegas bullish / bearish alignment detection**
- Useful for trend structure and higher-timeframe directional context

---

### 🔹 3) 🔺 ZigZag + Fibonacci Retracement/Extension (Optional)
- Built-in ZigZag swing detection
- Optional ZigZag line display
- Optional Fibonacci ratio lines + labels
- Configurable common ratios:
  - `0.236 / 0.382 / 0.500 / 0.618 / 0.786`
- Label location options (Left / Right)

---

### 🔹 4) 🔍 RSI Divergence Signals (Regular Divergence)
- Pivot-based regular RSI divergence detection
- Supports:
  - **Bullish Divergence**
  - **Bearish Divergence**
- Configurable:
  - RSI period
  - Pivot lookback left/right
  - Divergence range limits (min/max)
  - Plot bullish / bearish signals
- Displays chart labels for divergence signals

---

### 🔹 5) 🧱 Multi-Timeframe Support / Resistance Zones (MTF S/R)
- Pivot-based support/resistance zone detection
- Supports multi-timeframe sources (current TF / daily / weekly, etc.)
- Configurable:
  - Pivot length
  - Strength requirement
  - Zone width
  - Invalidation mode (`Wick` / `Close`)
  - Show invalidated zones
  - Show breakouts / retests
  - Zone extension behavior (`All / Only Valid / None`)
- Can merge nearby zones and annotate timeframe context

---

### 🔹 6) 📦 Range Box Detection
- Detects consolidation / range structures and draws range boxes
- Configurable:
  - Minimum range length
  - Range width factor
  - ATR length
- Box status coloring:
  - Unbroken
  - Broken upward
  - Broken downward
- Optional range top / bottom extension lines

---

### 🔹 7) 📏 ATR Reference Range (Data Window)
- Built-in ATR high/low references (current bar high/low ± ATR multiplier)
- Useful for:
  - Volatility estimation
  - Risk control references
  - Target/stop distance context

---

### 🔹 8) 🧾 Info Table (RSI + Trend)
- Simple info table shown in the top-right corner
- Currently includes:
  - RSI value
  - Trend direction (based on smoothed EMA200 trend filter)

---

### 🔹 9) 🔔 Multi-Module Alerts
Enable/disable alerts by module:

- RSI divergence alerts (bullish / bearish)
- Support/resistance breakout / retest alerts
- MA alignment alerts
- Vegas alignment alerts

> Uses `alert()` calls, suitable for TradingView alerts via **Any alert() function call**.

---

## 🖼️ Preview (Recommended Screenshots)
<img width="1702" height="903" alt="image" src="https://github.com/user-attachments/assets/4b32fea3-d5d2-488e-b816-d946cce8fc5d" />
<img width="1134" height="1472" alt="image" src="https://github.com/user-attachments/assets/8446a550-398c-4491-82e5-a2010f1cdf83" />
<img width="1127" height="1522" alt="image" src="https://github.com/user-attachments/assets/71f4d3fd-4c42-48a2-a981-0a0a4d44f67a" />
🚀 Installation (TradingView)

Open TradingView

Go to Pine Editor

Create a new script and clear the default code

Copy the script from this repository (e.g. 综合交易指标.pine)

Click Add to chart

Adjust inputs based on your market, timeframe, and trading workflow

🧩 Inputs (Grouped Overview)

This script has many inputs. Below is a grouped overview of the core settings (you can refine this further based on your release version).

1) 📊 Main Chart Indicators (MA Group + Vegas + ZigZag)
MA Group

Enable MA Group

MA #1 ~ MA #4 (type / source / length / color)

MA types: SMA / EMA / SMMA (RMA) / WMA / VWMA

Vegas Group

Enable Vegas Group

Vegas #1 ~ #5 (type / source / length / color)

MA types: SMA / EMA / SMMA (RMA) / WMA / VWMA

ZigZag / Fibonacci

Enable ZigZag

ZigZag Period

Show Zig Zag

Show Fibonacci Ratios

Fib text color / line color

ZigZag colors (up / down)

Label Location (Left / Right)

Fib ratio toggles (0.236 / 0.382 / 0.5 / 0.618 / 0.786)

2) 🔔 Alert Settings

Enable Divergence Alerts

Enable S/R Break/Retest Alerts

Enable MA Alignment Alerts

Enable Vegas Alignment Alerts

3) 📈 RSI / RSI Divergence Settings
RSI Basics

RSI Length

RSI Source

Overbought

Oversold

Midline

RSI Divergence

Enable Divergence Signals

RSI Period

Pivot Lookback Left / Right

Lookback Range Min / Max

Plot Bullish / Plot Bearish

4) 🧱 Support / Resistance

S/R Pivot Length

Strength Requirement

Invalidation Mode (Wick / Close)

Show Invalidated

Zone Width

Show Breaks

Show Retests

Expand Zones (All / Only Valid / None)

5) 🕒 Timeframes (MTF)

Current timeframe (toggle)

Daily timeframe (toggle)

Weekly timeframe (toggle)

Useful for combining multi-timeframe support/resistance context.

6) 📦 Range Box

Show Boxes

Minimum Range Length

Range Width

ATR Length

Colors (broken upward / broken downward / unbroken)

Show Range Lines

7) 📏 ATR Settings

ATR Period

ATR Multiplier

8) 🎨 Color Settings

Support zone color

Resistance zone color

Bullish / bearish color

Break color

Text color

🧠 How It Works
✅ MA / Vegas Alignment Detection

The script checks the ordering of enabled MA lines (or Vegas lines) to determine:

Bullish alignment: shorter-period lines above longer lines, with price above the lead line

Bearish alignment: shorter-period lines below longer lines, with price below the lead line

State transition detection (previous vs current bar) is used to trigger one-time alerts.

✅ RSI Regular Divergence Detection (Pivot-based)

Uses RSI pivots and price pivots to detect regular divergences:

Bullish Divergence

Price forms a Lower Low

RSI forms a Higher Low

Bearish Divergence

Price forms a Higher High

RSI forms a Lower High

Lookback range constraints are applied to improve signal matching quality.

✅ Multi-Timeframe Support / Resistance (MTF S/R)

Generates support/resistance zones from pivot highs/lows

Can fetch higher-timeframe S/R data via request.security()

Attempts to merge nearby zones and annotate timeframe information

Tracks invalidation, breakouts, and retests (optional display/alerts)

✅ Range Box Detection

Identifies consolidation ranges using length/width and ATR-based constraints

Draws boxes and colors them by breakout state

Optional range-top / range-bottom extension lines for follow-up observation

✅ Trend Info Panel

Top-right table shows RSI and trend direction

Trend direction is derived from EMA200 and a smoothed EMA200 filter

🔔 Alerts

This script supports the following module-level alerts (toggleable in inputs):

1) RSI Divergence Alerts

Bullish divergence (confirmed)

Bearish divergence (confirmed)

2) Support / Resistance Alerts

Breakout (confirmed)

Retest (confirmed)

3) MA Alignment Alerts

MA group bullish alignment formed

MA group bearish alignment formed

4) Vegas Alignment Alerts

Vegas bullish alignment formed

Vegas bearish alignment formed

✅ TradingView setup
Create an Alert for this indicator and use Any alert() function call.

📌 Notes

This indicator is for learning, research, and chart assistance only

Not financial advice

Since multiple modules can be enabled simultaneously, the chart may become visually dense; disable modules you don’t need for your workflow

Divergence / S&R / box / alignment signals should not be used in isolation

Consider combining with:

Market structure (trend vs range)

Volume

Multi-timeframe confluence

Risk management
⭐ Support

If this project helps you, consider giving it a Star ⭐
Issues and PRs are welcome!


