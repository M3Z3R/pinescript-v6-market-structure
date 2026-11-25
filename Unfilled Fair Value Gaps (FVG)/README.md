# Unfilled Fair Value Gaps (FVG) v6 — Pine Script v6

A clean, light, and reliable TradingView indicator written in **Pine Script v6** that identifies, tracks, dynamically trims, and alerts on unmitigated 3-candle Fair Value Gaps.

> **Zero Repainting:** All signals and gap creations are evaluated on confirmed bar closes (`barstate.isconfirmed`).

---

## Features

- **3-Candle FVG Detection**: Highlights bullish (`low[0] > high[2]`) and bearish (`high[0] < low[2]`) gaps. Filter tiny gaps using the ATR Minimum Gap Size multiplier.
- **Mitigation Modes**:
  - `Full Fill`: Keeps the zone open until price breaks past the far boundary.
  - `Partial Trim (50% / Wick)`: Dynamically shrinks the gap zone as price wicks into it.
- **Box Lifecycle Management**: Optionally keep mitigated gaps with reduced visual opacity or auto-delete them. Configurable cap for active zones (`Max Active FVGs = 20` default).
- **Visual Customization**: Individual color pickers for bullish/bearish boxes and an optional 50% equilibrium midline.
- **Alert Support**: Built-in `alertcondition()` hooks for new FVG formations and price entry events.

---

## Inputs & Parameters

| Parameter | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| `Min Gap Size (ATR Mult)` | Float | `0.5` | Minimum FVG threshold relative to `ta.atr(14)`. |
| `Mitigation Mode` | Dropdown | `Partial Trim` | Choose `Full Fill` or `Partial Trim`. |
| `Keep Mitigated Boxes` | Bool | `false` | Keep historical filled boxes on chart. |
| `Max Active FVGs` | Int | `20` | Cap maximum concurrent active boxes. |
| `Show 50% Midline` | Bool | `true` | Display internal equilibrium line inside zones. |

---

## How to Install

1. Copy the code inside `unfilled-fvg.pine`.
2. Open **TradingView** and click on the **Pine Editor** tab at the bottom of the screen.
3. Paste the code into the editor, click **Save**, and name your script.
4. Click **Add to Chart**.

## Visual
https://github.com/user-attachments/assets/d373d5d0-ee35-4de1-a473-976ed6870f80

---

## Custom Indicator Development

Need custom Pine Script v6 indicators, strategies, or backtesting tools?  
[**Order Custom Pine Script Development on Fiverr**](https://www.fiverr.com/s/Bb8z79W)
