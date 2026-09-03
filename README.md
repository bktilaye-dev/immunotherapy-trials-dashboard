# RTK II Glioblastoma Trial Finder

An interactive dashboard of **United States clinical trials** — recruiting or about to open — of
**immunotherapy and EGFR-targeted approaches** for an adult with **glioblastoma, IDH-wildtype,
DNA-methylation class "GBM, RTK II"** (the EGFR / classical family).

Case it was built around: a treatment-naïve adult whose **1.2 cm lesion was gross-totally resected**,
now deciding next steps before radiation or chemotherapy.

- **Dashboard:** open `index.html` (also published as a Claude Artifact).
- **Data:** `data/rtk2-gbm-trials-dataset.csv` and `data/rtk2-gbm-trials-dataset.json` — one row per trial with
  methodology, eligibility, endpoints, an evidence score, outcomes so far, source links, sites, and contacts.

## Not medical advice

This is an information aid compiled from public registry records and published literature. It may contain
errors or be out of date. It does not replace the treating neuro-oncology team or a molecular tumour board,
and it cannot determine whether a specific person is eligible — only a trial's investigators can. Trial
status, sites, and criteria change frequently; **verify every detail on
[ClinicalTrials.gov](https://clinicaltrials.gov) and with the study team** before acting. Nothing here should
delay standard care that the treating team recommends.

## What is included

22 trials that are: adult (≥18), IDH-wildtype adult-type glioblastoma, ≥1 US site, an immunotherapy or
EGFR-targeted mechanism, and open to **newly diagnosed** disease. Recurrent-only trials are listed separately
for future reference. Trials that require tumour tissue still in the brain (a planned biopsy-then-resection,
or a drug/wafer placed during surgery) are flagged as generally not open after a completed gross-total
resection.

### Evidence score

How much clinical **outcome** data stands behind each approach so far:

| Score | Meaning |
|---|---|
| 5 / 5 | Positive randomised phase 3 |
| 4 / 5 | Positive randomised phase 2 |
| 3 / 5 | Single-arm survival signal vs historical control |
| 2 / 5 | Early biological or radiographic signal, survival immature |
| 1 / 5 | First-in-human, no outcomes yet |
| ⚠ caution | A prior pivotal trial of this approach was negative |

The score is **not** a prediction for any individual patient.

## How it was built

Source: ClinicalTrials.gov API v2, queried **2 September 2026**, condition "glioblastoma", status
`RECRUITING` or `NOT_YET_RECRUITING`, across mechanism keyword clusters (immunotherapy / checkpoint,
cell & CAR therapy, EGFR, vaccine / oncolytic / gene therapy). Effectiveness notes are drawn from
peer-reviewed papers, ASCO / SNO abstracts, and sponsor releases; trials with no efficacy data are marked
first-in-human. "Fit" and "evidence score" labels are the compiler's, for triage only.

Generated with [Claude Code](https://claude.com/claude-code). Not affiliated with any sponsor or institution named.
