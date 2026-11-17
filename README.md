# RS Momentum Dashboard

**Weekly Relative Strength / Momentum Strategy – v1 (Locked Parameters)**

Clean, research-oriented dashboard and rule set for short-horizon relative-strength momentum.

Live site (GitHub Pages): [https://mylesblanc.github.io/rs-momentum-dashboard/](https://mylesblanc.github.io/rs-momentum-dashboard/)

---

## Strategy Overview

This implements the **weekly RS / momentum** lane from the strategy family map.

- Rank liquid names by 10-day relative strength vs their linked index
- Apply trend + volume confirmation filters
- Hold a small, equal-weighted portfolio of the strongest names
- Rebalance weekly
- Overlay macro regime filter from core futures

The shortlist is a **research ranked list**, not an automatic buy signal.

---

## Locked Parameters (v1)

See [STRATEGY.md](STRATEGY.md) for the full formal rule sheet.

### Quick Reference

| Parameter              | Value                          |
|------------------------|--------------------------------|
| Universe               | Liquid HSI / STI / US names    |
| Primary Signal         | 10-day Relative Strength       |
| Confirmation           | 5D trend positive + Vol > 20D avg |
| Holdings               | Top 8                          |
| Max per sector         | 3                              |
| Rebalance              | Every 5 trading days           |
| Exit (rank)            | Fall out of top 12             |
| Time stop              | 6 weeks max                    |
| Macro filter           | No new longs in risk-off       |
| Weighting              | Equal weight                   |
| Risk                   | Drawdown rules + position caps |

---

## Repository Structure

- `index.html` – Interactive dashboard (static mock + rules)
- `STRATEGY.md` – Formal locked rule set
- `README.md` – This file

---

## Next Steps

1. Connect real data feeds (Yahoo / Polygon / your existing pipeline)
2. Implement the ranking engine
3. Add backtest module
4. Paper trade with the locked rules

---

*Past performance is not indicative of future results. This is a research tool, not financial advice.*
