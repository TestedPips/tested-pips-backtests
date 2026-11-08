# Video 5: MACD Crossover (Tested Pips)

Backtest of the MACD crossover on 5 forex pairs (EUR/USD, GBP/USD, USD/JPY, AUD/USD, USD/CAD) and 3 timeframes (15-minute, 1-hour, 4-hour), 12 Mar 2017 to 12 Oct 2026 (FOREX.com via TradingView Deep Backtesting).

**Result:** 27 of 30 tests lost money after costs (median −55.0%). All 10 tests on 15-minute lost (median −97.1%). Version A (200 EMA + zero line filters) lost less than Version B (any crossover) in all 15 matchups. Only USD/JPY 4-hour Version A (+16.7%, 144 trades) stayed positive without its 5 best trades, and almost all of its profit came from buys.

The same 5,186 AUD/USD 15-minute trades (Version B) made +462.5% with zero costs and lost 97.9% with costs.

## Rules tested
1. MACD (12, 26, 9) on the close
2. Buy when the MACD line crosses above the signal line; sell when it crosses below (on the closed candle)
3. Version A: buys only when price closes above the 200 EMA and the cross is below the zero line; sells only below the 200 EMA with the cross above zero. Version B: every crossover
4. Entry: market order at the open of the next candle
5. Stop 1 pip beyond the lowest low (buys) / highest high (sells) of the last 10 candles; target 1.5R
6. One position at a time

## Test setup
- $10,000 start, 1% risk per trade, position capped at 30:1 leverage
- Commission 0.0035% per side (about $7 per standard lot round trip) + 0.5 pip slippage on market and stop fills

## Files
| File | What it is |
| --- | --- |
| `TestedPips_MACD_Crossover.pine` | Pine Script v6 strategy (v1.0). Paste into a new TradingView strategy. |
| `TestedPips_Video5_MACDCrossover_Results_v1.0.csv` | All 30 results (pair, timeframe, version, net %, drawdown, win rate, trades, profit factor) |
| `TestedPips_Video5_MACDCrossover_Checks_v1.0.csv` | Check 1: all ten 15m tests at zero vs full costs, EUR/USD 15m A cost split. Check 2: the three winners by year, without their 5 best trades, longs vs shorts |
| `MACD_AUDUSD_15m_VersionB_zero_costs.xlsx` / `_full_costs.xlsx` | The same 5,186 trades with and without costs |
| `MACD_USDJPY_4H_VersionA_full_costs.xlsx` | Trade list, 144 trades |
| `MACD_USDCAD_1H_VersionA_full_costs.xlsx` | Trade list, 596 trades |
| `MACD_AUDUSD_4H_VersionA_full_costs.xlsx` | Trade list, 158 trades |

## Notes
- One rule set only: no trailing stops, opposite-cross exits or other targets tested.
- Costs do not include a separate spread.

Educational only. Not financial advice, not a trade signal. Past results do not predict future ones.
