# JOBY Decision Result — Changed input (--revenue-pct 85)

- **Command:** `py joby_proforma_2026.py --revenue-pct 85`
- **Model as-of date:** FY2025 balance sheet at December 31, 2025 (Joby 2025 10-K, filed February 26, 2026)
- **Market quote shown for comparison only (not used in the decision):** $6.22 on September 24, 2026 (intraday quote; replace with the close if submitting later)
- **Units:** USD millions except shares (millions) and percentages

## Input

- **--revenue-pct:** 85% of the base 2026-30 revenue path
- **2026-30 revenue path:** 63.8M / 255.0M / 680.0M / 1530.0M / 2975.0M

## Decision numbers

| Decision number | Value |
|---|---:|
| 2030 operating profit | $86.3M |
| 2030 FCFE before funding | $-106.9M |
| Cumulative 2026-30 equity raised | $2,593.7M |
| 2030 shares outstanding | 1,332.1M |
| New shares 2026-30, % of FY2025 shares (915.1M) | 45.6% |

## Mandate check

| Condition | Actual | Result |
|---|---:|---|
| 2030 FCFE before funding above $0.0M | $-106.9M | FAIL |
| Cumulative 2026-30 new shares at or below 25.0% of FY2025 shares | 45.6% | FAIL |

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

**Decision line:** Reject a JOBY pilot allocation, because the model fails the mandate: 2030 FCFE before funding above $0.0M (actual $-106.9M); Cumulative 2026-30 new shares at or below 25.0% of FY2025 shares (actual 45.6%).

**Reversal condition:** This decision reverses to a pilot of at most 1% if a rerun shows 2030 FCFE before funding above $0.0M and cumulative new shares at or below 25.0% of FY2025 shares; with every other input at base, the model first passes both at --revenue-pct 162.1.
