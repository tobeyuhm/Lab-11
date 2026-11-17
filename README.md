# Joby Aviation (JOBY) — Pro Forma Model and Committee Mandate Check

**Project 2 decision:** should the portfolio *pilot* a capped JOBY position or *reject* it?
The model forecasts Joby's 2026–30 statements from its FY2025 10-K, then tests the result
against a fixed committee mandate and prints a verdict, a decision line, and the condition
that would reverse it.

**Current baseline result:** [outputs/baseline/decision.md](outputs/baseline/decision.md)
(readable on GitHub without running anything).

## Run it

Requirements: Python 3.10 or newer. Standard library only — nothing to install.

From the cloned repository folder, run this one command:

```bash
py joby_proforma_2026.py --revenue-pct 100
```

> On macOS/Linux, or if `py` is not found, use `python3` (or `python`) in place of `py`.
> Everything else stays the same.

### Where the result appears

1. **In the terminal:** the decision result (decision numbers, mandate check, verdict,
   decision line, reversal condition), ending with a `Saved:` line.
2. **In files** (overwritten on each run, UTF-8):
   - `outputs/baseline/decision.md` — the decision result shown in the terminal
   - `outputs/baseline/full_report.txt` — full history, ratio, assumption, pro forma,
     and sensitivity report

For any other `--revenue-pct` value, the files go to `outputs/revenue_pct_<value>/`
(for example `outputs/revenue_pct_85/decision.md`).

## The one documented input

| Input | Units | Default | Meaning |
|---|---|---|---|
| `--revenue-pct` | percent of the base revenue path | `100` | Scales every 2026–30 revenue year. Base path is $75M / $300M / $800M / $1,800M / $3,500M. `85` means each year is 15% lower; `120` means 20% higher. Must be greater than 0. |

Every other assumption stays at its base value (listed in the decision file). The input
is load-bearing: revenue drives gross profit, which drives FCFE, the equity raised to
hold the $300M cash floor, and therefore dilution — both mandate conditions.

## The mandate (set 2026-11-17, before the mandate was run on any output)

A JOBY **pilot** of at most **1%** of the portfolio is allowed only if **both** hold:

1. 2030 FCFE before funding (net income + depreciation − capex) is above **$0.0M**; and
2. cumulative 2026–30 new shares are at or below **25%** of FY2025 shares (915.1M).

Otherwise the verdict is **reject**. The thresholds are in `MANDATE` in
[joby_proforma_2026.py](joby_proforma_2026.py).

## Repository map

| File | What it is |
|---|---|
| [joby_proforma_2026.py](joby_proforma_2026.py) | The model, mandate check, and command |
| [outputs/baseline/decision.md](outputs/baseline/decision.md) | Baseline decision result |
| [outputs/baseline/full_report.txt](outputs/baseline/full_report.txt) | Baseline full report |
| [docs/decision-memo.md](docs/decision-memo.md) | Decision memo (matches the baseline output) |
| [docs/changed-input-record.md](docs/changed-input-record.md) | Locked Changed-Input Record (Lab 20) |
| [docs/partner-cold-run.md](docs/partner-cold-run.md) | Partner cold-run record |
| [docs/submission-audit.md](docs/submission-audit.md) | Lab 20 requirement-by-requirement audit |
| [joby_proforma_2026_base_inputs.json](joby_proforma_2026_base_inputs.json) | Frozen base inputs (Lab 11) |
| [joby_locked_changed_input_record.md](joby_locked_changed_input_record.md) | Lab 11 sensitivity record (revenue ±30%, margin ±10 pts) |
| [joby_proforma_2026_visible_output.txt](joby_proforma_2026_visible_output.txt), [joby_proforma_2026_sensitivity_output.txt](joby_proforma_2026_sensitivity_output.txt) | Lab 11 report outputs, regenerated in UTF-8 from the current code |
| [joby_nuscale_partner_input_review.md](joby_nuscale_partner_input_review.md), [lab12_live_review.md](lab12_live_review.md) | Earlier partner and live-review records |

## Partner instructions (cold run)

1. Clone this repository into **your own new, empty folder** — not the author's folder.
2. Use **only this README**. Do not read other instructions, and do not ask the author
   or anyone else for help or coaching during the run.
3. Start a timer, run the command in [Run it](#run-it) exactly as written, and stop the
   timer when you can see the decision result.
4. Record what happened yourself, in your own words, directly in
   [docs/partner-cold-run.md](docs/partner-cold-run.md): the exact command, the first
   failure (or "No failure"), elapsed time, where the result appeared, and any question
   this README did not answer.
5. If something fails, stop and record it. The author will fix it, push, and ask you to
   rerun from a fresh clone.

## Limitations

The 2026–30 revenue, margin, cost, and capex paths are author judgment, not company
guidance (see the assumption set in the full report). The per-share terminal value printed
in the full report is illustrative only and is not used in the decision. The $6.22 market
quote (September 24, 2026, intraday) is shown for comparison only.
