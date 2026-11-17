# Lab 20 Submission Audit — JOBY Project 2

**Audit date:** 2026-11-17 · **Branch audited:** `lab20-evidence-package` (not yet merged to `master`)

**Standard:** "A committee member who has never met me should be able to reach my decision
from the repository, and the decision should survive one changed input."

Statuses: **Complete** means the evidence is in the repository now. **Needs Human Evidence**
means only the author or partner can supply it. **Blocked** means it is waiting on an earlier
step. This audit does not claim any grade.

| # | Requirement | Status | Evidence / location | What is still needed |
|---|---|---|---|---|
| 1 | Tool: change one documented input, read the mandate verdict | Complete | `--revenue-pct` in [README](../README.md#the-one-documented-input); verdict in [decision.md](../outputs/baseline/decision.md) | — |
| 2 | README gives one exact command from a fresh clone | Complete, pending a cold run | [README → Run it](../README.md#run-it): `py joby_proforma_2026.py --revenue-pct 100` | Merge to `master` (the default clone) and confirm with the partner cold run |
| 3 | Decision numbers readable on GitHub without running code | Complete once pushed | [outputs/baseline/decision.md](../outputs/baseline/decision.md) | Commit and push |
| 4 | Decision memo matches visible output exactly | Complete except author fields | [decision-memo.md](decision-memo.md) | Author name, memo date, optional limitations |
| 5a | Baseline output | Complete | [outputs/baseline/](../outputs/baseline/) | — |
| 5b | Mandate check | Complete | Mandate check table in [decision.md](../outputs/baseline/decision.md) | — |
| 5c | Locked Changed-Input Record (prediction) | Complete except author name | [changed-input-record.md](changed-input-record.md), Part A; locked in commit `55dcb5c`, pushed before the run | Author name in the Lock table |
| 5d | Changed-input stress run | Complete | [outputs/revenue_pct_85/decision.md](../outputs/revenue_pct_85/decision.md); Parts C–D of the record. Verdict stayed REJECT; FCFE condition flipped to FAIL, as predicted | Author review of the AI-drafted Part D |
| 5e | Validation-and-AI-Use record | Needs Human Evidence | AI use so far: Claude drafted the CLI, mandate check, docs, and the Part A prediction on 2026-11-17 | Author's AI-use disclosure in the course's required format |
| 6 | Videos 1–3 with working links, each answering its question | Needs Human Evidence | [README → Videos](../README.md#videos-and-transcripts) | Recordings, links, assigned questions |
| 7 | Transcripts | Needs Human Evidence | Same table | Transcript files or links |
| 8 | Partner cold run (command, first failure, time, location) | Needs Human Evidence | [partner-cold-run.md](partner-cold-run.md) | Partner completes Run 1; fix and rerun if needed |
| 9 | Decision line with an allowed verb, plus a reversal condition | Complete | Decision section of [decision.md](../outputs/baseline/decision.md) and [memo](decision-memo.md) | — |
| 10 | Reflection (what the cold run found; what won't change) | Blocked | [partner-cold-run.md → Author reflection](partner-cold-run.md#author-reflection-author-fills-in-after-the-cold-run) | Comes after the cold run |
| 11 | GitHub checkout: working links to Markdown, code, outputs, videos, transcripts | Needs Human Evidence | All repository links are relative | Push; click-test on GitHub; add video and transcript links |

## Known risks

- **Project fit:** the course defines Project 2 as deciding whether to adopt, allocate to,
  rebalance, pilot or reject a *strategy*. This repo decides on a single-stock JOBY pilot. Confirm
  this framing is acceptable for Project 2.
- **Stale market quote:** $6.22 is a September 24, 2026 intraday quote. It is not used in the
  decision, but the code labels it "replace with the close."
- **Judgment inputs:** the revenue, margin, cost and capex paths are author judgment, not guidance.
- **Earlier partner text:** commit `9abf46f` put a partner answer into the code's printed output.
  Confirm that partner approved those words.
