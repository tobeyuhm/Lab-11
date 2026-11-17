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
| Prediction commit hash | [TO COMPLETE: full hash from `git log -1 --format=%H` after committing this file] |
| Prediction commit link | [TO COMPLETE: https://github.com/tobeyuhm/Lab-11/commit/HASH] |
| Commit date and time | [TO COMPLETE: from `git log -1 --format=%ci`] |

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

*Fill in only after the Part A commit exists.*

Source: [TO COMPLETE: link to `../outputs/revenue_pct_85/decision.md` once it is generated and committed]

| Decision number | Value |
|---|---:|
| 2030 operating profit | [TO COMPLETE] |
| 2030 FCFE before funding | [TO COMPLETE] |
| Cumulative 2026-30 equity raised | [TO COMPLETE] |
| 2030 shares outstanding | [TO COMPLETE] |
| New shares 2026-30, % of FY2025 shares (915.1M) | [TO COMPLETE] |

**Mandate verdict:** [TO COMPLETE]

**Decision line (output):** [TO COMPLETE]

**Reversal condition (output):** [TO COMPLETE]

---

## Part D — What happened

| Question | Entry |
|---|---|
| What happened to each decision number | [TO COMPLETE] |
| Did the decision change? | [TO COMPLETE] |
| Did each number move in the predicted direction? | [TO COMPLETE] |
| Why the outcome did or did not match the prediction | [TO COMPLETE] |
