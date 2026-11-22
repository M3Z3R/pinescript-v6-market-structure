# 2-Candle Alternating Break of Structure (BOS) — Pine Script v6

A clean, robust Pine Script v6 indicator for TradingView that detects confirmed structural shifts using 2-candle swing formations and an alternating state filter.

## Overview

The **2-Candle Alternating Break of Structure** indicator tracks micro-structural shifts without cluttering your chart. By maintaining an internal trend-state machine, the script eliminates duplicate consecutive signals in the same direction—a Bullish BOS will only trigger after a Bearish BOS has set the market state to Downtrend.

## Features

- **2-Candle Swing Detection:**
  - **Swing High:** Bullish candle followed immediately by a bearish candle.
  - **Swing Low:** Bearish candle followed immediately by a bullish candle.
- **Alternating State Machine:** Filters out duplicate directional signals to ensure only valid structural state transitions are plotted.
- **Body Close vs. Wick Mode:** Customizable execution mode—choose between conservative body closes (`close`) or aggressive intrabar wick breaks (`high`/`low`).
- **Built-In Alerts:** Includes native `alertcondition()` hooks for both Bullish and Bearish BOS triggers, populated with standard dynamic placeholders (`{{ticker}}`, `{{interval}}`).

## Settings

| Option | Default | Description |
|---|---|---|
| `Allow Wick Break` | `False` | Set to `False` to require candle body closes beyond structural levels. Set to `True` for intrabar wick breakouts. |

## Installation

1. Copy the contents of `bos-indicator.pine`.
2. Open TradingView, launch the **Pine Editor** panel at the bottom.
3. Clear the default text, paste the code, and click **Save**.
4. Click **Add to Chart**.

---

### Need Custom Pine Script Development?

Get custom indicators, strategies, or alerts built for TradingView.  
[Order a Custom Pine Script on Fiverr](https://www.fiverr.com/s/Bb8z79W)
