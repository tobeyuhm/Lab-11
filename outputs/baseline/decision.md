# JOBY Decision Result — Baseline (--revenue-pct 100)

- **Command:** `py joby_proforma_2026.py --revenue-pct 100`
- **Model as-of date:** FY2025 balance sheet at December 31, 2025 (Joby 2025 10-K, filed February 26, 2026)
- **Market quote shown for comparison only (not used in the decision):** $6.22 on September 24, 2026 (intraday quote; replace with the close if submitting later)
- **Units:** USD millions except shares (millions) and percentages

## Input

- **--revenue-pct:** 100% of the base 2026-30 revenue path
- **2026-30 revenue path:** 75.0M / 300.0M / 800.0M / 1800.0M / 3500.0M

## Decision numbers

| Decision number | Value |
|---|---:|
| 2030 operating profit | $375.1M |
| 2030 FCFE before funding | $121.2M |
| Cumulative 2026-30 equity raised | $2,275.8M |
| 2030 shares outstanding | 1,281.0M |
| New shares 2026-30, % of FY2025 shares (915.1M) | 40.0% |

## Mandate check

| Condition | Actual | Result |
|---|---:|---|
| 2030 FCFE before funding above $0.0M | $121.2M | PASS |
| Cumulative 2026-30 new shares at or below 25.0% of FY2025 shares | 40.0% | FAIL |

**Mandate verdict:** REJECT

## Assumptions held at base

- Gross margin 2026-30: 35% / 40% / 45% / 50% / 55%
- R&D 2026-30: 650M / 700M / 775M / 850M / 900M
- SG&A 2026-30: 190M / 240M / 325M / 425M / 525M
- Capex 2026-30: 90M / 125M / 180M / 240M / 300M
- Depreciation: 22.86% of opening PP&E each year
- Cash tax: 21% of positive operating income only
- Cash floor $300M, funded by new equity at $6.22/share
- Per-share value is not used: the terminal-value figure is illustrative only (see full report)

## Decision

**Decision line:** Reject a JOBY pilot allocation, because the model fails the mandate: Cumulative 2026-30 new shares at or below 25.0% of FY2025 shares (actual 40.0%).

**Reversal condition:** This decision reverses to a pilot of at most 1% if a rerun shows 2030 FCFE before funding above $0.0M and cumulative new shares at or below 25.0% of FY2025 shares; with every other input at base, the model first passes both at --revenue-pct 162.1.
