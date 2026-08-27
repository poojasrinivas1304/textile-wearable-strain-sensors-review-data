# Supplementary scoring and agreement data

Study-level scoring files supporting the systematic review *Textile wearable
strain sensors for human monitoring: a systematic critical review of
deployment readiness, validation, and standardization*.

Two reviewers scored every included study using predefined operational
rubrics. Agreement was quantified using weighted Cohen's kappa, and residual
differences were resolved by consensus against the full texts.

## Files

| File | Content |
|---|---|
| `Azza_Figure5_scoring.xlsx` | Reviewer A ratings for the Figure 5 validation-depth and deployment-readiness axes, with evidence and page numbers |
| `Pooja_Figure5_scoring.xlsx` | Reviewer B ratings for the Figure 5 axes, with evidence and page numbers |
| `Azza_Figure6_scoring.xlsx` | Reviewer A scores for the nine Figure 6 reporting and validation items, with item-level evidence |
| `Pooja_Figure6_scoring.xlsx` | Reviewer B scores for the nine Figure 6 items, with item-level evidence and page numbers |
| `Figure6_final_consensus.xlsx` | Final agreed Figure 6 score matrix for the 29 included studies |
| `Final_consensus_and_kappa_29_studies.xlsx` | Consolidated rubrics, consensus assignments, score summaries, kappa results and disagreement-resolution log |
| `kappa_summary.md` | Inter-rater agreement statistics and sensitivity analysis |
| `calculate_kappa.py` | Reproducible calculation of exact agreement and unweighted, linear- and quadratic-weighted Cohen's kappa |
| `requirements.txt` | Python dependencies required by the calculation script |

## Scoring frameworks

- **Figure 5 axes:** validation depth (1 = laboratory proof of concept to 5 =
  near-deployment validation) and deployment readiness (1 = material/sensing
  element to 5 = advanced prototype). Operational definitions are provided in
  the `Scoring rubric` sheet of each Figure 5 workbook.
- **Figure 6 items:** F1 architecture/integration route; F2
  material/substrate composition; E1 working strain range; E2 gauge factor and
  strain regime; E3 signal-quality descriptors; E4 dynamic/durability
  descriptors; R1 environmental robustness; V1 on-body/garment evidence; and
  V2 comparator/structured validation. Items are scored 2 (clearly and
  quantitatively reported), 1 (partially or qualitatively reported), 0
  (applicable but not reported), or NA (genuinely not applicable).

## Reproducing the agreement analysis

With Python 3 installed, run:

```bash
python -m pip install -r requirements.txt
python calculate_kappa.py
```

The script aligns reviewers by study and year, excludes Fan et al. (2024) from
the final 29-study dataset, excludes Figure 6 NA cells pairwise, and obtains
95% confidence intervals by resampling studies with replacement (10,000
bootstrap samples; fixed random seed 2026).

## Data-use note

This repository contains reviewer-generated extraction and scoring data only.
Copyrighted full-text articles used for verification are not redistributed.
