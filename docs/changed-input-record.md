# Locked Changed-Input Record — Lab 20

> **This prediction must be committed and pushed BEFORE the changed-input run.**
> Do not run `py joby_proforma_2026.py --revenue-pct 85` until Part A is committed. The commit
> hash in Part A is the proof that the prediction came first. Parts B–D are filled in only
> after that commit.

---

## Part A — Locked pre-run prediction

| Field | Entry |
|---|---|
| Input name | `--revenue-pct` (2026–30 revenue path as a percent of the base path) |
| Old value and units | 100 percent of base path = $75.0M / $300.0M / $800.0M / $1,800.0M / $3,500.0M (USD millions, 2026–30) |
| New value and units | 85 percent of base path = $63.75M / $255.0M / $680.0M / $1,530.0M / $2,975.0M (USD millions, 2026–30) |
| Everything else | Held at base (margins, R&D, SG&A, capex, tax, $300M cash floor, $6.22 issue price) |
| Command to run after commit | `py joby_proforma_2026.py --revenue-pct 85` |
| Output location after run | `outputs/revenue_pct_85/decision.md` |

### Predicted direction of each decision number

Approximate sizes are hand calculations from the model's mechanics (see *Reasoning*), not
model output.

| Decision number | Baseline (output) | Predicted direction | Predicted approximate value |
|---|---:|---|---:|
| 2030 operating profit | $375.1M | Down | ≈ $86.4M (−$288.8M) |
| 2030 FCFE before funding | $121.2M | Down, turning negative | ≈ −$106.9M (−$228.1M) |
| Cumulative 2026-30 equity raised | $2,275.8M | Up | ≈ $2,593.6M (+$317.8M) |
| 2030 shares outstanding | 1,281.0M | Up | ≈ 1,332.1M |
| New shares 2026-30, % of FY2025 shares | 40.0% | Up | ≈ 45.6% |

### Predicted effect on the decision

- **FCFE condition:** predicted to change from PASS to **FAIL**.
- **Dilution condition:** predicted to stay **FAIL**, and by a wider margin.
- **Verdict:** predicted to stay **REJECT**. The decision is predicted **not** to change, but
  it would now fail on both conditions instead of one.
- **Reversal threshold:** predicted to stay `--revenue-pct 162.1`, because it is an absolute
  level of the same input and does not depend on the starting value.

### Reasoning

1. Revenue falls 15% each year; the margin is unchanged, so gross profit falls by
   15% × revenue × margin. In 2030 that is $525.0M × 55% = $288.75M.
2. Depreciation depends only on PP&E and capex, which do not change, so 2030 operating
   profit falls by the same $288.75M: $375.1M → about $86.4M. It stays positive, so tax is
   still paid.
3. The 21% tax cushions the drop: net income and FCFE before funding fall by
   $288.75M × 79% ≈ $228.1M, so $121.2M → about −$106.9M.
4. The lower gross profit in 2026–29 (about $3.9M, $18.0M, $54.0M, $135.0M) adds to the equity
   raises needed to hold the $300M floor. A negative 2030 FCFE adds a 2030 raise of about
   $106.9M. That is about $317.8M more equity at $6.22, or about 51.1M more shares.

### Lock

| Field | Entry |
|---|---|
| Prediction prepared by | [TO COMPLETE: author name]. Drafted with AI assistance (Claude, 2026-11-17) from the model code; the author must check it before committing. |
| Prediction commit hash | `55dcb5c544f36bc1dd1014087c461f3397f66076` |
| Prediction commit link | https://github.com/tobeyuhm/Lab-11/commit/55dcb5c544f36bc1dd1014087c461f3397f66076 |
| Commit date and time | 2026-11-17 14:09:53 −0500; pushed to `origin/lab20-evidence-package` before the changed-input run |

*Part A above this table is unchanged since that commit. Compare with `git diff 55dcb5c -- docs/changed-input-record.md`.*

---

## Part B — Baseline output

Source: [../outputs/baseline/decision.md](../outputs/baseline/decision.md), from
`py joby_proforma_2026.py --revenue-pct 100`.

| Decision number | Value |
|---|---:|
| 2030 operating profit | $375.1M |
| 2030 FCFE before funding | $121.2M |
| Cumulative 2026-30 equity raised | $2,275.8M |
| 2030 shares outstanding | 1,281.0M |
| New shares 2026-30, % of FY2025 shares (915.1M) | 40.0% |

**Mandate verdict:** REJECT (FCFE condition PASS; dilution condition FAIL)

---

## Part C — Changed-input output

Run on 2026-11-17, after the Part A commit was pushed.

Source: [../outputs/revenue_pct_85/decision.md](../outputs/revenue_pct_85/decision.md)
(full report: [../outputs/revenue_pct_85/full_report.txt](../outputs/revenue_pct_85/full_report.txt)), from
`py joby_proforma_2026.py --revenue-pct 85`.

| Decision number | Value |
|---|---:|
| 2030 operating profit | $86.3M |
| 2030 FCFE before funding | $-106.9M |
| Cumulative 2026-30 equity raised | $2,593.7M |
| 2030 shares outstanding | 1,332.1M |
| New shares 2026-30, % of FY2025 shares (915.1M) | 45.6% |

**Mandate verdict:** REJECT (FCFE condition FAIL; dilution condition FAIL)

**Decision line:** Reject a JOBY pilot allocation, because the model fails the mandate: 2030 FCFE before funding above $0.0M (actual $-106.9M); Cumulative 2026-30 new shares at or below 25.0% of FY2025 shares (actual 45.6%).

**Reversal condition:** This decision reverses to a pilot of at most 1% if a rerun shows 2030 FCFE before funding above $0.0M and cumulative new shares at or below 25.0% of FY2025 shares; with every other input at base, the model first passes both at --revenue-pct 162.1.

---

## Part D — What happened

*Drafted with AI assistance (Claude, 2026-11-17) by comparing the Part A prediction with the
Part C output. The author should review it and rewrite it in their own words if required.*

| Decision number | Baseline | Predicted | Actual | Direction matched? |
|---|---:|---:|---:|---|
| 2030 operating profit | $375.1M | ≈ $86.4M, down | $86.3M | Yes |
| 2030 FCFE before funding | $121.2M | ≈ −$106.9M, down, turning negative | $-106.9M | Yes |
| Cumulative 2026-30 equity raised | $2,275.8M | ≈ $2,593.6M, up | $2,593.7M | Yes |
| 2030 shares outstanding | 1,281.0M | ≈ 1,332.1M, up | 1,332.1M | Yes |
| New shares, % of FY2025 shares | 40.0% | ≈ 45.6%, up | 45.6% | Yes |

| Question | Entry |
|---|---|
| What happened | Cutting the revenue path by 15% lowered 2030 operating profit by $288.8M and turned 2030 FCFE before funding negative. Equity raised rose by $317.9M, and new shares rose from 40.0% to 45.6% of FY2025 shares. Yearly raises were $0.0M / $762.8M / $974.0M / $750.0M / $106.9M for 2026–30. Every annual balance-sheet and cash-floor check passed. |
| Did the decision change? | **No.** The verdict stayed REJECT. The reason widened: the FCFE condition went from PASS to FAIL, and the dilution condition stayed FAIL. The reversal threshold stayed at `--revenue-pct 162.1`. |
| Did the outcome match the prediction? | Yes, in direction for all five numbers and for the verdict, the condition flip, and the threshold. Sizes were within $0.1M or 0.1 points. |
| Why it matched | Revenue passes through the model by fixed rules: gross profit = revenue × an unchanged margin; depreciation does not depend on revenue; 21% tax applies only to positive operating income; and any cash shortfall below $300M becomes new equity at $6.22. Because 2030 operating profit stayed positive, the hand calculation of the tax effect held. The $0.1M differences come from starting the hand calculation from rounded baseline figures ($375.1M rather than the unrounded value). |
| What this means for the decision | The rejection survives a 15% lower revenue path and becomes stronger, since it now fails both conditions. It does not test whether the rejection survives a *higher* path or a change in the equity issue price, which would move the dilution condition directly. |
