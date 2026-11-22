# TradingView Pine Script™ v6 — Market Structure & Liquidity Tools

Clean, non-repainting **Pine Script v6** (`//@version=6`) indicators built for price-action and Smart Money Concepts (SMC) traders.

---

## Included Indicators

### 1. 2-Candle Alternating Break of Structure (`2-Candle Alternating BOS.pine`)
Detects confirmed structural shifts using 2-candle swing formations with an alternating trend-state machine to prevent redundant back-to-back signals in the same direction.

* **2-Candle Swing Detection:** Identifies swing highs (bullish candle followed by bearish candle) and swing lows (bearish candle followed by bullish candle).
* **Alternating State Machine:** Tracks the active structural state (`Uptrend` / `Downtrend`) so a new Bullish BOS only triggers after a bearish shift (and vice versa).
* **Body Close vs. Wick Mode:** Toggle between strict candle-body closes (`close`) or instant intrabar wick breaks (`high`/`low`).
* **Dynamic Built-In Alerts:** Ready-to-use `alertcondition()` hooks for Bullish and Bearish BOS events using `{{ticker}}` and `{{interval}}`.

| Setting | Default | Description |
| :--- | :--- | :--- |
| `Allow Wick Break` | `false` | Set to `false` to require candle-body closes beyond swing levels, or `true` for intrabar wick breakouts. |

---

### 2. Unfilled Fair Value Gaps (`Unfilled Fair Value Gaps (FVG).pine`)
Automatically detects, extends, dynamically trims, and alerts on unmitigated 3-candle Fair Value Gaps (evaluated strictly on confirmed bar closes for zero repainting).

* **3-Candle FVG Detection & ATR Filter:** Identifies bullish (`low[0] > high[2]`) and bearish (`high[0] < low[2]`) imbalances, filtering out noise via an ATR-based minimum gap multiplier (`ta.atr(14)`).
* **Flexible Mitigation Modes:**
  * `Full Fill`: Keeps the zone open until price breaks past the far boundary of the gap.
  * `Partial Trim (50% / Wick)`: Dynamically shrinks the gap zone in real time as price wicks into it.
* **Box Lifecycle Management:** Option to automatically delete filled boxes or keep historical mitigated zones with dimmed opacity, capped by `Max Active FVGs` (default `20`).
* **Custom Visuals & Midline:** Independent color pickers for bullish/bearish zones plus an optional 50% equilibrium midline.
* **Built-In Alerts:** Includes `alertcondition()` hooks for new FVG formations and price entry events.

| Setting | Default | Description |
| :--- | :--- | :--- |
| `Min Gap Size (ATR Mult)` | `0.2` / `0.5` | Minimum gap height relative to `ta.atr(14)` required to plot a zone. |
| `Mitigation Mode` | `Full Fill` / `Partial Trim` | Choose between full-fill invalidation or dynamic wick trimming. |
| `Keep Mitigated Boxes` | `false` | Retain historical filled boxes on the chart with reduced opacity. |
| `Max Active FVGs` | `20` | Maximum concurrent active gap boxes tracked on the chart. |
| `Show 50% Midline` | `true` | Display a 50% equilibrium midline inside active FVG zones. |

---

## How to Install on TradingView

1. Open either `2-Candle Alternating BOS.pine` or `Unfilled Fair Value Gaps (FVG).pine` in this repository and copy the full source code.
2. Open **TradingView** and click the **Pine Editor** tab at the bottom of your chart.
3. Clear any default template code, paste the script, and click **Save**.
4. Click **Add to Chart** to apply the indicator.

---

## Need a Custom Indicator, Strategy, or Webhook Bridge?

I build custom **Pine Script v6** indicators, backtestable strategies, legacy v4/v5 upgrades, and automated JSON webhook alerts (MetaTrader 5 / 3Commas / custom bots).

👉 **[Order a custom script or message me on Fiverr](https://www.fiverr.com/s/0DEZYpL)**
