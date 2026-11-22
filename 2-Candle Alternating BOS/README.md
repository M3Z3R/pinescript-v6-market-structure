2-Candle Alternating Break of Structure (BOS) — Pine Script v6
A high-performance Pine Script v6 technical indicator designed for TradingView. It detects confirmed structural market shifts using precise 2-candle swing formations while employing an alternating state machine to prevent redundant back-to-back signals in the same direction.
Overview
The 2-Candle Alternating Break of Structure indicator tracks micro-structural shifts across any chart timeframe. Standard BOS indicators often spam charts with repeated signals during prolonged expansion phases. This script addresses that noise by maintaining an active trend-state machine—guaranteeing that a new Bullish BOS can only trigger after a bearish structural reversal has occurred, and vice versa.
Key Features
2-Candle Swing Detection: Accurately identifies structural pivot points.
Swing High: Defined as a bullish candle immediately followed by a bearish candle.
Swing Low: Defined as a bearish candle immediately followed by a bullish candle.
Alternating State Machine: Enforces trend-state logic (Uptrend vs. Downtrend). Prevents duplicate continuation signals, ensuring clean and actionable chart analysis.
Body Close vs. Wick Mode: Toggle between strict validation requiring candle-body closes (close) beyond key levels or instant intrabar wick breaches (high / low).
Built-In Dynamic Alerts: Pre-configured alertcondition() integration using TradingView's native placeholders ({{ticker}}, {{interval}}) for seamless automation via webhooks or mobile notifications.
Indicator Settings
Setting
Type
Default
Description
Allow Wick Break
Boolean
False
When set to False, requires candle close beyond swing levels for confirmation. When True, triggers immediately on intrabar high/low wick extensions.

Installation Guide (TradingView)
Copy the Code: Copy the full Pine Script v6 source code from bos-indicator.pine.
Open Pine Editor: On TradingView, open your target chart and click the Pine Editor tab at the bottom console.
Paste & Save: Erase any default code in the editor, paste the copied script, and click Save.
Add to Chart: Click the Add to Chart button in the Pine Editor toolbar.


Raw GitHub README.md Code
Copy and paste the markdown block below directly into your repository's README.md file:

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
[Order a Custom Pine Script on Fiverr](YOUR_FIVERR_GIG_LINK_HERE)

