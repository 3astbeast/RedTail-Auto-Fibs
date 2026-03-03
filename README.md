<p align="center">
  <img src="https://avatars.githubusercontent.com/u/209633456?v=4" width="160" alt="RedTail Indicators Logo"/>
</p>

<h1 align="center">RedTail Auto Fibs</h1>

<p align="center">
  <b>Automatic multi-timeframe Fibonacci retracement levels for NinjaTrader 8.</b><br>
  Plots Daily, Weekly, and Monthly Fibonacci retracements from the previous period's range — no manual drawing required.
</p>

<p align="center">
  <a href="https://buymeacoffee.com/dmwyzlxstj">
    <img src="https://img.shields.io/badge/☕_Buy_Me_a_Coffee-FFDD00?style=flat-square&logo=buy-me-a-coffee&logoColor=black" alt="Buy Me a Coffee"/>
  </a>
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/3astbeast/RedTail-Auto-Fibs/refs/heads/main/Screenshot%202026-03-03%20125433.png" width="800" alt="RedTail AutoFibs Screenshot"/>
</p>
---

## Overview

RedTail Auto Fibs automatically tracks the high, low, open, and close of each daily, weekly, and monthly period, then plots Fibonacci retracement levels from the previous period's range onto the current chart. The fibs are direction-aware — if the previous period closed bullish, retracements are drawn from high to low; if bearish, from low to high. Each timeframe has its own color scheme and up to 10 fully customizable levels, making it easy to see where daily, weekly, and monthly fibs overlap.

---

## How It Works

The indicator tracks OHLC data for each period internally using Eastern Time session logic (session rolls at 6 PM ET). When a new period begins, the previous period's high/low/open/close become the anchor points for the Fibonacci levels. The direction of the retracement is determined by comparing the period's close to its open — bullish periods draw 0% at the high (retracement toward the low), and bearish periods draw 0% at the low (retracement toward the high).

Lines extend both backward (configurable lookback in days) and forward (configurable bars past the current bar) for easy visual reference.

---

## Three Timeframes

Each timeframe can be independently enabled or disabled with its own line style, width, and opacity.

**Daily Fibs** — Retracements from the previous day's range. Default style: solid lines, blue color family.

**Weekly Fibs** — Retracements from the previous week's range. Default style: dashed lines, orange color family.

**Monthly Fibs** — Retracements from the previous month's range. Default style: dash-dot lines, magenta color family.

---

## Per-Level Customization

Each timeframe has 10 independently configurable Fibonacci levels (30 total across all three timeframes). Every level has:

- **Enabled/Disabled toggle** — Turn individual levels on or off
- **Value** — The Fibonacci percentage (supports both standard retracements and extensions via negative values)
- **Color** — Independent color per level

**Default levels (per timeframe):**
- 0%, 23.6%, 38.2%, 50%, 61.8%, 78.6%, 100% (enabled)
- −27.2%, −61.8%, −100% (disabled by default — extension levels)

The extension levels use negative values to project beyond the range. Enable them to see where price might target if it breaks through the 0% or 100% level.

---

## Labels

Each Fibonacci line includes a text label showing the timeframe, percentage, and optionally the price value. For example: `Daily | 61.8% | 5432.50`. The label font size is configurable globally, and price display can be toggled on or off.

---

## Global Settings

- **Line Extend Bars Right** — How many bars past the current bar the lines extend (1–50). Default: 5.
- **Line Lookback Days** — How many days back the lines extend (1–30). Lower values reduce clutter and speed up loading. Default: 2.
- **Label Font Size** — Font size for all Fib labels (6–24). Default: 10.
- **Show Price on Label** — Toggle price values in labels on or off.

---

## Performance

The indicator uses a smart caching system — it only redraws Fibonacci levels when the underlying OHLC values actually change, avoiding redundant redraws on every bar update. Combined with the configurable lookback days, this keeps the indicator lightweight even on fast timeframes.

---

## Installation

1. Download the `.cs` file from this repository
2. Open NinjaTrader 8
3. Go to **Tools → Import → NinjaScript Add-On**
4. Select the downloaded file and click **OK**
5. The indicator will appear in your **Indicators** list — add it to any chart

---

## Part of the RedTail Indicators Suite

This indicator is part of the [RedTail Indicators](https://github.com/3astbeast/RedTailIndicators) collection — free NinjaTrader 8 tools built for futures traders who demand precision.

---

<p align="center">
  <a href="https://buymeacoffee.com/dmwyzlxstj">
    <img src="https://img.shields.io/badge/☕_Buy_Me_a_Coffee-Support_My_Work-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black" alt="Buy Me a Coffee"/>
  </a>
</p>
