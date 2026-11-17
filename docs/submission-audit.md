# Lab 20 Submission Audit — JOBY Project 2

**Audit date:** 2026-11-17 · **Branch audited:** `master` (merged from `lab20-evidence-package` at `df5f07f`)

**Standard:** "A committee member who has never met me should be able to reach my decision
from the repository, and the decision should survive one changed input."

Statuses: **Complete** means the evidence is in the repository now. **Needs Human Evidence**
means only the author or partner can supply it. **Blocked** means it is waiting on an earlier
step. This audit does not claim any grade.

| # | Requirement | Status | Evidence / location | What is still needed |
|---|---|---|---|---|
| 1 | Tool: change one documented input, read the mandate verdict | Complete | `--revenue-pct` in [README](../README.md#the-one-documented-input); verdict in [decision.md](../outputs/baseline/decision.md) | — |
| 2 | README gives one exact command from a fresh clone | Complete, pending a cold run | [README → Run it](../README.md#run-it): `py joby_proforma_2026.py --revenue-pct 100` | Confirm with the partner cold run |
| 3 | Decision numbers readable on GitHub without running code | Complete once pushed | [outputs/baseline/decision.md](../outputs/baseline/decision.md) | Commit and push |
| 4 | Decision memo matches visible output exactly | Complete except author fields | [decision-memo.md](decision-memo.md) | Author name, memo date, optional limitations |
| 5a | Baseline output | Complete | [outputs/baseline/](../outputs/baseline/) | — |
| 5b | Mandate check | Complete | Mandate check table in [decision.md](../outputs/baseline/decision.md) | — |
| 5c | Locked Changed-Input Record (prediction) | Complete except author name | [changed-input-record.md](changed-input-record.md), Part A; locked in commit `55dcb5c`, pushed before the run | Author name in the Lock table |
| 5d | Changed-input stress run | Complete | [outputs/revenue_pct_85/decision.md](../outputs/revenue_pct_85/decision.md); Parts C–D of the record. Verdict stayed REJECT; FCFE condition flipped to FAIL, as predicted | Author review of the AI-drafted Part D |
| 5e | Validation-and-AI-Use record | Needs Human Evidence | AI use so far: Claude drafted the CLI, mandate check, docs, and the Part A prediction on 2026-11-17 | Author's AI-use disclosure in the course's required format |
| 8 | Partner cold run (command, first failure, time, location) | Needs Human Evidence | [partner-cold-run.md](partner-cold-run.md) | Partner completes Run 1; fix and rerun if needed |
| 9 | Decision line with an allowed verb, plus a reversal condition | Complete | Decision section of [decision.md](../outputs/baseline/decision.md) and [memo](decision-memo.md) | — |
| 10 | Reflection (what the cold run found; what won't change) | Blocked | [partner-cold-run.md → Author reflection](partner-cold-run.md#author-reflection-author-fills-in-after-the-cold-run) | Comes after the cold run |
| 11 | GitHub checkout: working links to Markdown, code, outputs | Needs Human Evidence | All repository links are relative; pushed to `master` | Click-test the links on GitHub |

## Author pre-check before the partner cold run (not the partner cold run)

On 2026-11-17, Claude (an AI assistant working for the author) cloned the repository from GitHub into an
empty folder on the author's machine (Windows, Python 3.14.7) and ran the README command
`py joby_proforma_2026.py --revenue-pct 100`.

- **Found:** the run worked (exit 0, about 1 second, same numbers). However, `git status` then showed
  `outputs/baseline/decision.md` and `full_report.txt` as modified. Only the line endings differed:
  Windows Git checked the files out as CRLF, and the script writes LF.
- **Fix:** commit `99f1d42` added `.gitattributes` (`outputs/** text eol=lf`).
- **Recheck:** a second fresh clone at `99f1d42` ran cleanly, and `git status` showed no changes.

This pre-check does not replace the partner cold run in [partner-cold-run.md](partner-cold-run.md).

## Known risks

- **Project fit:** the course defines Project 2 as deciding whether to adopt, allocate to,
  rebalance, pilot or reject a *strategy*. This repo decides on a single-stock JOBY pilot. Confirm
  this framing is acceptable for Project 2.
- **Stale market quote:** $6.22 is a September 24, 2026 intraday quote. It is not used in the
  decision, but the code labels it "replace with the close."
- **Judgment inputs:** the revenue, margin, cost and capex paths are author judgment, not guidance.
- **Earlier partner text:** commit `9abf46f` put a partner answer into the code's printed output.
  Confirm that partner approved those words.
