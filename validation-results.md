# AgriGene Insight — Prototype Validation Results

## 1. Overview

This document presents the reported computational validation results of the AgriGene Insight prototype.

The documented validation run used a test dataset containing 10 nucleotide sequences to examine the sequence alignment and conservation analysis workflow.

These results represent the specific test dataset and are not general biological conclusions.

## 2. Test Dataset

| Parameter | Reported value |
|---|---:|
| Number of input sequences | 10 |
| Total alignment positions | 54 |
| Conserved alignment positions | 51 |
| Variable alignment positions | 3 |

## 3. Reported Validation Results

Conservation Analysis

The prototype reported:

- Conserved alignment positions: 51
- Total alignment positions: 54
- Variable alignment positions: 3
- Overall conservation percentage: 94.44%

The conservation percentage is calculated as:

### Conservation (%) = (51 / 54) × 100 = 94.44%

### Interpretation

In this test dataset, 94.44% of the alignment columns were classified as conserved, while 3 columns were classified as variable.

This indicates a high degree of positional conservation within the analysed alignment.

It does not independently establish gene function, disease resistance or stress tolerance.

## 4. Documented Computational Components

The project report documents the following components:

- FASTA input and sequence validation.
- Multiple Sequence Alignment using Clustal Omega.
- Conservation analysis.
- Sequence variation analysis.
- Pairwise sequence comparison.
- Comparative Sequence Priority Score (CSPS) methodology.

## 5. Validation Scope

The reported results demonstrate a prototype analysis using a defined test dataset.

Further work is required to establish independent reproducibility and evaluate performance using additional datasets.

The current repository does not yet contain the complete source-code implementation.

## 6. Limitations

- The validation dataset contains only 10 nucleotide sequences.
- The reported conservation percentage applies only to this alignment.
- Sequence conservation does not independently establish biological function.
- Additional datasets are needed for broader computational validation.
- Independent reproducibility testing remains pending.

## 7. Conclusion

The reported validation run demonstrates the prototype's documented ability to analyse a nucleotide sequence alignment and report conserved and variable positions.

Further validation, source-code integration and reproducibility testing are necessary before making broader claims about the framework's performance.

---

## Project: AgriGene Insight
## Document: Prototype Validation Results
## Status: Reported prototype results; further validation pending.
