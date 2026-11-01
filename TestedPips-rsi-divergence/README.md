# Video 4: RSI Divergence (Tested Pips)

Backtest of RSI divergence on 5 forex pairs (EUR/USD, GBP/USD, USD/JPY, AUD/USD, USD/CAD) and 3 timeframes (15-minute, 1-hour, 4-hour), 12 Mar 2017 to 12 Oct 2026 (FOREX.com via TradingView Deep Backtesting).

**Result:** 25 of 30 tests lost money after costs (median −32.1%). All 10 tests on 15-minute and all 10 on 1-hour lost. On 4-hour, 5 of 10 made money; 2 of them (AUD/USD Version A, EUR/USD Version B) stayed profitable without their 5 best trades, but on small samples (64 and 166 trades).

The same 873 EUR/USD 15-minute trades made +43.4% with zero costs and lost 59.5% with costs.

## Rules tested
1. RSI(14) on the close
2. Swing low = lowest low of the 5 candles on each side (confirmed 5 candles later, no lookahead). Swing high = the mirror
3. Bullish divergence: lower price swing low + higher RSI low at the same two swings. Bearish = the mirror. Swings 5 to 60 candles apart
4. Version A: first swing's RSI below 30 (buys) or above 70 (sells). Version B: any divergence
5. Entry: market order at the open of the next candle
6. Stop 1 pip beyond the second swing, target 2R, one position at a time

## Test setup
- $10,000 start, 1% risk per trade, position capped at 30:1 leverage
- Commission 0.0035% per side (about $7 per standard lot round trip) + 0.5 pip slippage on market and stop fills

## Files
| File | What it is |
| --- | --- |
| `TestedPips_RSI_Divergence.pine` | Pine Script v6 strategy (v1.0). Paste into a new TradingView strategy. |
| `TestedPips_Video4_RSIDivergence_Results_v1.0.csv` | All 30 results (pair, timeframe, version, net %, drawdown, win rate, trades, profit factor) |
| `TestedPips_Video4_RSIDivergence_Checks_v1.0.csv` | Check 1: EUR/USD 15m at three cost levels. Check 2: the five 4-hour winners by year, without their 5 best trades, longs vs shorts |
| `RSI_EURUSD_15m_VersionA_full_costs.xlsx` | Trade list, 873 trades, full costs |
| `RSI_EURUSD_15m_VersionA_zero_costs.xlsx` | Same test with zero costs |
| `RSI_AUDUSD_4H_VersionA_full_costs.xlsx` | Trade list, 64 trades |
| `RSI_EURUSD_4H_VersionB_full_costs.xlsx` | Trade list, 166 trades |
| `RSI_EURUSD_4H_VersionA_full_costs.xlsx` | Trade list, 82 trades |
| `RSI_USDJPY_4H_VersionA_full_costs.xlsx` | Trade list, 79 trades |
| `RSI_USDJPY_4H_VersionB_full_costs.xlsx` | Trade list, 154 closed trades (+1 open at the end of the data) |

## Notes
- One rule set only: no confirmation candle, trendline break or trend filter tested.
- EUR/USD 15-minute has far fewer trades in 2017–2019 than later years, so some early bars are probably missing.
- Costs do not include a separate spread.

Educational only. Not financial advice, not a trade signal. Past results do not predict future ones.
