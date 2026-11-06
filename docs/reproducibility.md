# AgriGene Insight — Reproducibility and Computational Validation

## 1. Purpose

Reproducibility is an essential requirement in computational biology research.

This document describes the computational workflow, input requirements, analysis definitions and information needed to independently reproduce the reported validation results of AgriGene Insight.

The documentation is based on the project's reported methodology and validation activities.

## 2. Overview of the Computational Workflow

The documented analysis follows these stages:

1. Nucleotide FASTA input.
2. FASTA format and sequence validation.
3. Multiple Sequence Alignment using Clustal Omega.
4. Conservation analysis.
5. Sequence variation analysis.
6. Pairwise sequence identity calculation.
7. Alignment coverage calculation.
8. Comparative Sequence Priority Score (CSPS) calculation.
9. Computational result generation.

Each stage contributes to the final sequence-analysis output.

## 3. Input Dataset Requirements

The framework accepts nucleotide sequences in FASTA format.

The input dataset should contain:

- At least two nucleotide sequences.
- Unique sequence identifiers.
- Valid nucleotide characters under the configured validation rules.
- Non-empty sequence records.
- Sequence information suitable for comparative alignment.

The original validation report documents an analysis involving 10 nucleotide sequences.

The original FASTA records and their accession-level provenance must be included in a reproducibility package before the analysis can be independently repeated.

## 4. Computational Tools and Environment

The project report identifies the following technologies:

| Technology | Role in the Project |
|---|---|
| Python | Computational development |
| Biopython | Biological sequence processing |
| Clustal Omega | Multiple Sequence Alignment |
| FastAPI | Backend API development |
| React | Frontend development |
| TypeScript | Frontend programming |
| ReportLab | Report generation |

Exact software versions, dependency versions and execution configurations must be recorded in a future reproducibility release.

They should not be assumed from the technology names alone.

## 5. Multiple Sequence Alignment

Validated nucleotide sequences are aligned using Clustal Omega.

The resulting Multiple Sequence Alignment provides a common coordinate system for downstream analysis.

The alignment is used for:

- Identifying conserved alignment positions.
- Detecting variable positions.
- Performing reference-based comparisons.
- Calculating pairwise sequence identity.
- Evaluating alignment coverage.

For independent reproduction, the original input sequences, Clustal Omega version, execution parameters and alignment output must be retained.

## 6. Conservation and Variation Calculations

### 6.1 Conservation Analysis

An alignment column is classified as conserved when all analysed sequences contain the same nucleotide at that position, according to the documented implementation rule.

The overall conservation percentage is calculated as:

Conservation (%) = (Conserved alignment positions / Total alignment positions) × 100

### 6.2 Variation Analysis

Variable alignment positions are columns containing more than one nucleotide.

Reference-based variant observations are evaluated separately against the selected reference sequence.

The number of variable alignment positions and the number of reference-based variant observations are not necessarily identical.

## 7. Pairwise Identity and Alignment Coverage

### 7.1 Mean Pairwise Identity

Pairwise identity measures nucleotide similarity between two aligned sequences.

The documented approach excludes gap-containing positions from the denominator when calculating pairwise identity.

Mean Pairwise Identity (MPI) is calculated as the average of the valid pairwise identity values for an individual sequence against the other sequences.

### 7.2 Alignment Coverage

Alignment Coverage (AC) represents the proportion of the total alignment represented by non-gap positions in an individual sequence.

AC = Non-gap aligned positions / Total alignment columns

Both identity and coverage contribute to the CSPS calculation.

## 8. Comparative Sequence Priority Score

The project uses a geometric-mean-based scoring approach:

CSPS = 100 × √(AC × MPI)

Where:

- AC = Alignment Coverage.
- MPI = Mean Pairwise Identity.

The score combines sequence similarity and alignment coverage.

A high score indicates stronger sequence comparability within the analysed dataset.

CSPS does not predict drought tolerance, heat tolerance, disease resistance, breeding superiority or field performance.

For independent verification, the exact numerical representation of AC and MPI, including whether percentages are converted to proportions before calculation, must be retained consistently with the implementation.

## 9. Reported Validation Results

The project report documents the following results from its 10-sequence validation dataset:

| Validation Parameter | Reported Result |
|---|---:|
| Input sequences | 10 |
| Total alignment positions | 54 |
| Conserved alignment positions | 51 |
| Variable alignment positions | 3 |
| Conservation percentage | 94.44% |

The conservation percentage is calculated as:

(51 / 54) × 100 = 94.44%

These values represent the reported test dataset only.

They should not be interpreted as general findings about millet genetic diversity or biological stress tolerance.

## 10. Information Required for Independent Reproduction

The following materials are required to independently reproduce the reported analysis:

- Original nucleotide FASTA dataset.
- Sequence identifiers and accession information.
- Selected reference sequence.
- FASTA validation rules.
- Clustal Omega version and execution parameters.
- Original alignment output.
- Conservation and variation calculation definitions.
- Pairwise identity and alignment coverage implementation.
- CSPS calculation implementation.
- Software dependency versions.
- Original computational output for comparison.

## 11. Current Reproducibility Status

**Status: Documentation available; independent reproduction pending.**

The project report documents the computational workflow and a validation run with reported results.

However, the complete source-code implementation and original input dataset are not yet available in this GitHub repository.

Therefore, independent reproduction of the reported results has not yet been demonstrated through this repository.

This distinction is maintained to ensure transparent and scientifically responsible reporting.

## 12. Future Reproducibility Improvements

Future development will focus on:

1. Integrating the complete source-code implementation.
2. Publishing the original validation dataset with sequence provenance.
3. Recording software and dependency versions.
4. Documenting Clustal Omega execution parameters.
5. Providing reproducible execution instructions.
6. Adding automated tests for individual computational modules.
7. Comparing independently generated outputs with the reported validation results.

## 13. Conclusion

AgriGene Insight aims to provide a transparent and reproducible framework for nucleotide sequence analysis and evidence-guided candidate investigation.

Documenting the computational workflow, calculation definitions, input requirements and limitations establishes a foundation for independent verification and future research development.

The long-term objective is to make the framework more reproducible, extensible and scientifically reliable.
