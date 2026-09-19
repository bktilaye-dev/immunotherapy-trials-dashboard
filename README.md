# RTK II Glioblastoma Trial Finder

An interactive dashboard of **United States clinical trials** — recruiting or about to open — of
**immunotherapy and EGFR-targeted approaches** for an adult with **glioblastoma, IDH-wildtype,
DNA-methylation class "GBM, RTK II"** (the EGFR / classical family).

Case it was built around: a treatment-naïve, **48-year-old** adult whose **1.2 cm lesion was gross-totally
resected 2 weeks ago**, now deciding next steps before radiation or chemotherapy.

- **Dashboard:** open `index.html` (also published as a Claude Artifact).
- **Data:** `data/rtk2-gbm-trials-dataset.csv` and `data/rtk2-gbm-trials-dataset.json` — one row per trial with
  methodology, eligibility, endpoints, an evidence score, outcomes so far, source links, sites, and contacts.

## Companion page — `neoantigen-peptide-atlas.html`

**Neoantigen & Personalized Peptide Vaccine Atlas** — the same patient (48-year-old, IDH-wildtype, methylation
class RTK II, 1.2 cm gross-totally resected, treatment-naïve), narrowed to one modality: a therapeutic vaccine
built from the tumour's own mutations (neoantigens), or from a per-patient selection of tumour-antigen peptides
(PPV), in any delivery format (synthetic peptide, mRNA, DNA, dendritic-cell).

Page order (revised): the how-it's-made and RTK II primers, then **Section 1 (open institutional trials)**, then
**Section 2 (private providers)** in the middle, then the reference tables, questions and glossary, and finally the
**completed / landmark trials** collected at the very end. Every list is **US-first**.

Two sections, as requested:

1. **Institutional trials the patient could qualify for — worldwide** (not US-only, because the field is heavily
   European and Asian), US entries sorted to the top. Six trials open or about to open (ZSNeo-DC1.1 neoantigen-DC
   + TMZ, which explicitly requires IDH-wildtype; UF RNA-LP autologous-mRNA; a Paris PTPRZ1/TERT peptide trial; an
   Italian DC + tumour-homogenate trial; a Brazilian placebo-controlled Phase 3; the Greek Tamavaq trial, weak fit).
   The four landmark platforms between trials (NeoVax / Dana-Farber, the Washington University neoantigen DNA
   vaccine, GAPVAC-101, XS15 / Tübingen) are now in a **"Completed & landmark trials"** section at the end of the
   page. Appendices: shared-antigen peptide vaccines (SurVaxM, rindopepimut ⚠, etc.) and recurrent-disease trials.
2. **Private providers around the world** that sell this outside a trial, grouped by region with **United States
   first**. Every card now carries the **same field set as this dashboard's own private-provider list** — contact /
   website, what is manufactured, starting material, regulatory framework, est. cost (also a badge), insurance,
   evidence, patient story — plus a plain "what is unverified" statement:
   - **United States** — a fresh 9 Sep 2026 search found **no clinic selling a tumour-sequenced neoantigen vaccine
     outside a trial**. Montana's "peptide" clinics sell catalogue research peptides (BPC-157, TB-500), not
     tumour-neoantigen vaccines; US-accessible private options are cross-border or a different technique —
     Immunocine Cancer Center (AZ intake → Cancún treatment, lysate-DC, ≈ USD 50k) and Williams Cancer Institute
     (Las Vegas — intratumoral ablation "in-situ vaccination", not a peptide vaccine). Moderna/BioNTech
     individualized neoantigen therapies have no GBM expanded-access pathway. The real US route is a trial.
   - **Europe** — CeGaT / cecava, Tübingen (the main documented route; 173-patient real-world series *and* the
     *Neuro-Oncology* rebuttal; ≈ €52k); Hallwang ⚠ (≈ USD 100–127k); IOZK (DC, cross-ref).
   - **Japan** — NEO Clinic Tokyo; the Kurume/Brightpath PPV lineage; peptide-pulsed-DC clinics.
   - **China** — Zhejiang University / iNeo, Hangzhou; NeoCura; ZSky; Shenzhen Geno-Immune.
   - **Mexico** — no verified neoantigen-peptide programme; the Baja integrative clinics market "cancer vaccines"
     without a published pipeline (≈ USD 45–60k / 3 weeks).

- **Data:** `data/rtk2-gbm-neoantigen-peptide-dataset.csv` and `data/rtk2-gbm-neoantigen-peptide-dataset.json`.
- Built from the ClinicalTrials.gov API v2 (queried 9 September 2026, worldwide), EU/Japan/China registry
  mentions in the literature, published trial results, and clinic/company/regulator sources for the private
  providers. Not medical advice; not an endorsement of any provider.

## Treatment-Optimization Atlas — `treatment-optimization-atlas.html`

**An interactive, toggleable decision timeline** for the same patient, now that the actual plan has firmed up:
standard chemoradiation starting **28 September 2026 (Day 0)**, a **Duke University immunotherapy trial** under
Dr. Henry Friedman afterward, and the **CeGaT GmbH / cecava GmbH** personalized neoantigen vaccine (documented in
the companion Neoantigen atlas above, cross-referenced rather than repeated here) as supportive treatment.

30 catalog items — 3 fixed standard-of-care entries plus 27 toggleable ones spanning the Duke trial, the CeGaT
vaccine, immune/NK-cell support, marrow/immune recovery, repurposed and investigational drugs (including OKN-007
trial access and pharmacologic-dose IV vitamin C), a steroid-sparing strategy, lifestyle adjuncts, and every
explicitly-requested weak-evidence item (ivermectin, fenbendazole, low-dose naltrexone) — are laid out on a
phase-by-phase timeline from Day 0. Every non-fixed item can be switched on or off, and a live, fully transparent
**optimization score** updates immediately, including warnings when active choices conflict (e.g. an oral
antioxidant supplement switched on during concurrent radiotherapy) and notes when they reinforce each other (e.g.
a steroid-sparing strategy paired with the immunotherapy trial). The page opens on a literature-informed
**"optimal preset"** and lets you experiment freely from there — nothing is sent anywhere; every toggle and
estimated date lives only in your browser's local storage.

- **Data:** `data/rtk2-gbm-treatment-optimization-dataset.csv` and `data/rtk2-gbm-treatment-optimization-dataset.json`.
- Built from published literature and clinical-trial records gathered 18 September 2026 (University of Iowa
  pharmacologic-ascorbate trials, the Care Oncology Protocol's METRICS cohort, the disulfiram/copper and CQ/HCQ
  randomised trials, the ERGO2 ketogenic-diet trial, and more — each item links its sources). Not medical advice;
  the score is an illustrative literature-alignment heuristic, not a survival or outcome prediction.

### Optimization score

Each of 11 categories has a fixed weight (summing to 100), split evenly across every item assigned to it. An
active item's contribution is scaled by its evidence grade, and interactions between active items add or subtract
points directly, surfaced as warnings (conflicts, timing cautions) or synergies:

| Category | Weight |
|---|---|
| Standard of care (fixed) | 20 |
| Immunotherapy trial access | 18 |
| Personalized vaccine (supportive) | 8 |
| Immune / NK-cell support | 10 |
| Marrow & immune recovery | 9 |
| Repurposed / investigational drugs | 12 |
| OKN-007 trial access | 5 |
| Steroid management | 8 |
| Anecdotal / weak evidence | 3 |
| Antioxidant supplements (timing caution) | 2 |
| Lifestyle & metabolic | 5 |

Evidence grade → contribution factor follows this dashboard's existing 1–5 evidence-score convention (5/5 = ×1.00
down to 1/5 = ×0.25), with a null score (protocol not yet confirmed, e.g. the Duke trial) at ×0.40 and a
⚠ caution flag (a trial of that specific approach was negative, or no human data exists at all for something with
real risk, e.g. disulfiram+copper, fenbendazole) at ×−0.30. **This score is not a prediction for this patient** —
it is a transparent way to see how a chosen combination stacks up against the literature gathered here.

## Not medical advice

This is an information aid compiled from public registry records and published literature. It may contain
errors or be out of date. It does not replace the treating neuro-oncology team or a molecular tumour board,
and it cannot determine whether a specific person is eligible — only a trial's investigators can. Trial
status, sites, and criteria change frequently; **verify every detail on
[ClinicalTrials.gov](https://clinicaltrials.gov) and with the study team** before acting. Nothing here should
delay standard care that the treating team recommends.

## What is included

16 trials that are: adult (≥18), IDH-wildtype adult-type glioblastoma, ≥1 US site, an immunotherapy or
EGFR-targeted mechanism, open to **newly diagnosed** disease, and **do not require MGMT-unmethylated status**
(6 trials that did were removed for this case). Recurrent-only trials are listed separately for future
reference. Trials that require tumour tissue still in the brain (a planned biopsy-then-resection, or a
drug/wafer placed during surgery) are flagged as generally not open after a completed gross-total resection.

### Tissue / specimen requirement

Every trial is also tagged with what it needs from the original resection — filterable in the dashboard:

| Tag | Meaning |
|---|---|
| Standard archival tissue only | The routine paraffin block from any resection is enough — no special banking needed |
| Fresh / viable tissue required | Needs living tumour cells or a cell line, not archival tissue |
| Fresh-frozen tissue required | Needs a specific mass of fresh-frozen tissue, not just a paraffin block |
| Blood only, no tumour tissue | Manufactured from blood/leukapheresis; biomarkers use the existing archival block |
| Needs an unscheduled resection | Drug/vector/wafer must be placed *at* surgery — not open after a completed resection |

### Time-since-surgery requirement

Each trial also states its timing relative to surgery specifically (not just the broader enrolment window),
evaluated against **2 weeks post-op** as of this compilation — flagging, for example, the one trial with an
explicit 2–4 week post-surgery enrolment window.

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
first-in-human. "Fit" and "evidence score" labels are the compiler's, for triage only. Updated
**3 September 2026** with case-specific refinements: patient age and surgery date, a tissue/specimen
requirement and a time-since-surgery requirement added per trial, and the 6 trials requiring
MGMT-unmethylated status removed.

Generated with [Claude Code](https://claude.com/claude-code). Not affiliated with any sponsor or institution named.
