# Decision Memo — JOBY Pilot Allocation

**To:** Investment committee
**From:** [TO COMPLETE: author name]
**Memo date:** [TO COMPLETE: date you finalize this memo]
**Decision:** Pilot or reject a capped JOBY position

> Every number, date, condition, and sentence marked *(output)* below is copied exactly
> from [../outputs/baseline/decision.md](../outputs/baseline/decision.md), produced by
> `py joby_proforma_2026.py --revenue-pct 100`. If the output changes, this memo must be
> updated to match.

## Decision *(output)*

**Decision line:** Reject a JOBY pilot allocation, because the model fails the mandate: Cumulative 2026-30 new shares at or below 25.0% of FY2025 shares (actual 40.0%).

**Reversal condition:** This decision reverses to a pilot of at most 1% if a rerun shows 2030 FCFE before funding above $0.0M and cumulative new shares at or below 25.0% of FY2025 shares; with every other input at base, the model first passes both at --revenue-pct 162.1.

## Dates *(output)*

- **Model as-of date:** FY2025 balance sheet at December 31, 2025 (Joby 2025 10-K, filed February 26, 2026)
- **Market quote shown for comparison only (not used in the decision):** $6.22 on September 24, 2026 (intraday quote; replace with the close if submitting later)

## Decision numbers *(output; USD millions except shares (millions) and percentages)*

| Decision number | Value |
|---|---:|
| 2030 operating profit | $375.1M |
| 2030 FCFE before funding | $121.2M |
| Cumulative 2026-30 equity raised | $2,275.8M |
| 2030 shares outstanding | 1,281.0M |
| New shares 2026-30, % of FY2025 shares (915.1M) | 40.0% |

## Mandate conditions and check *(output)*

| Condition | Actual | Result |
|---|---:|---|
| 2030 FCFE before funding above $0.0M | $121.2M | PASS |
| Cumulative 2026-30 new shares at or below 25.0% of FY2025 shares | 40.0% | FAIL |

**Mandate verdict:** REJECT

The mandate allows a pilot of at most 1% of the portfolio only when both conditions pass.

## Assumptions *(output)*

- **2026-30 revenue path:** 75.0M / 300.0M / 800.0M / 1800.0M / 3500.0M (--revenue-pct 100)
- Gross margin 2026-30: 35% / 40% / 45% / 50% / 55%
- R&D 2026-30: 650M / 700M / 775M / 850M / 900M
- SG&A 2026-30: 190M / 240M / 325M / 425M / 525M
- Capex 2026-30: 90M / 125M / 180M / 240M / 300M
- Depreciation: 22.86% of opening PP&E each year
- Cash tax: 21% of positive operating income only
- Cash floor $300M, funded by new equity at $6.22/share
- Per-share value is not used: the terminal-value figure is illustrative only (see full report)

## Why *(author explanation)*

The base case becomes cash-generative by 2030 (FCFE before funding $121.2M), so the cash
condition passes. But reaching 2030 requires $2,275.8M of new equity to hold the $300M cash
floor, which at $6.22 per share adds 40.0% to the FY2025 share count — above the 25.0%
dilution limit. The rejection is driven by dilution, not by the 2030 operating result.

## Stress test

See [changed-input-record.md](changed-input-record.md) for the locked prediction and the
changed-input result.

## Limitations

Revenue, margin, cost, and capex paths are author judgment, not company guidance. The model
uses a single equity issue price and no debt. [TO COMPLETE: any further limitations you
want the committee to weigh]
