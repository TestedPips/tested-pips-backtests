# Video 3: London Breakout (Tested Pips)

Backtest of the London Breakout on 5 forex pairs, 5-minute data, 12 Mar 2017 to 12 Oct 2026 (FOREX.com via TradingView Deep Backtesting).

**Result:** 27 of 30 tests lost money after costs. The only profitable tests were on USD/JPY; the best (Version A, hold to 16:00) made +28.3%, but its profit depends on its 10 best trades and came almost entirely from 2022–2026.

## Rules tested
1. Asian range: high and low from 00:00 to 07:00 London time
2. At 07:00: buy stop 1 pip above the high, sell stop 1 pip below the low (one cancels the other)
3. Orders live 07:00–10:00 London only
4. Stop: Version A = 1 pip beyond the opposite side of the range; Version B = range midpoint
5. Target: 1R, 2R, or none (hold to 16:00 London)
6. One trade per day; anything open at 16:00 London is closed

## Test setup
- $10,000 start, 1% risk per trade, position capped at 30:1 leverage
- Commission 0.0035% per side (about $7 per standard lot round trip) + 0.5 pip slippage on stop/market fills

## Files
| File | What it is |
| --- | --- |
| `TestedPips_London_Breakout.pine` | Pine Script v6 strategy (v1.2). Paste into a new TradingView strategy. |
| `TestedPips_Video3_LondonBreakout_Results_v1.1.csv` | All 30 results (pair, version, target, net %, drawdown, win rate, trades, profit factor) |
| `TestedPips_Video3_LondonBreakout_RobustnessTests_v1.2.csv` | USD/JPY checks: zero costs, commission only, full costs, skipping NFP/CPI days |
| `TestedPips_Video3_US_News_Days_NFP_CPI.csv` | NFP and CPI release dates used by the skip-news switch (BLS release schedules) |
| `LB_v1.1_A_USDJPY_1600close_full_costs.xlsx` | Full trade list for the best test (1,745 trades) |

## Notes
- Before late 2019 the 5-minute data is missing some candles. If the 06:55 candle is missing, orders are placed on the first candle after 07:00 (v1.1 fix).
- Costs do not include a separate spread.

Educational only. Not financial advice, not a trade signal. Past results do not predict future ones.
