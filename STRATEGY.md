# RS Momentum Strategy – Locked Parameters (v1)

**Status:** Locked for initial development and testing  
**Date locked:** 2026-11-17  
**Lane:** Weekly Relative Strength / Momentum

---

## 1. Universe

- Liquid names from tracked lists: HSI constituents, major STI names, liquid US names.
- Minimum 20-day average dollar volume filter (practical floor for realistic fills).
- Exclude names with recent major corporate actions or extreme distress.

## 2. Primary Signal

- **10-day Relative Strength**  
  `RS = Stock total return (10 trading days) − Linked Index total return (10 trading days)`
- Rank descending (highest RS = strongest).

## 3. Confirmation Filters (ALL required)

- 5-day trend still positive (or not sharply negative) — use existing 5D trend flag.
- Current volume > 20-day average volume.
- Soft filter (optional but recommended): sector not in bottom quartile of relative strength.

## 4. Portfolio Construction

- Select the **top 8** names that pass all filters.
- **Equal weight**.
- Maximum **3 names** from any single sector.
- Rebalance every **5 trading days** (weekly cadence).
- If fewer than 8 names pass filters → hold fewer (do not force full investment).

## 5. Exit Rules

- Exit on rebalance if name falls out of the **top 12**.
- Hard time stop: maximum holding period of **6 weeks**.
- Immediate exit / no new entries if macro regime turns decisively **risk-off**.
- Optional later: volatility-based trailing stop (e.g. 2× ATR).

## 6. Macro Overlay (Core Futures)

- New long entries **only** when regime is risk-on or neutral.
- No new entries (consider reducing exposure) when regime is clearly risk-off.
- Regime derived from existing Core Futures tags (NQ/ES, rates, USD, commodities).

## 7. Position Sizing & Risk Limits

- Equal weight across selected names.
- Target portfolio daily volatility ~1.0–1.5% (adjust later if needed).
- Maximum single-name weight: **15%**.
- Drawdown rules:
  - After 8–10% drawdown from peak → reduce size by 50%.
  - After 12–15% drawdown → stop new entries.
- Cash buffer allowed.

## 8. Costs (for first backtests)

- Realistic all-in round-trip cost: 10–20 bps for liquid names (higher for smaller names).
- Use adjusted prices.
- Check survivorship bias where possible.

## 9. Success Criteria for v1

- Positive excess return **after costs**.
- Acceptable maximum drawdown relative to return.
- Reasonable turnover.
- Performance not entirely concentrated in one regime or one calendar year.

---

## Implementation Notes

- The shortlist produced by the dashboard is a **research ranked list**, not an automatic trade signal.
- Always apply the full rule set (filters + regime + risk limits) before considering any position.
- Freeze these parameters for the first walk-forward test. Only change after out-of-sample evaluation.

---

*This document is the single source of truth for v1 parameters.*
