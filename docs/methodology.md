# AgriGene Insight — Computational Methodology

## 1. Overview

AgriGene Insight is a modular computational framework for nucleotide sequence analysis and evidence-guided candidate prioritization.

The workflow integrates sequence validation, Multiple Sequence Alignment (MSA), conservation analysis, variation analysis, pairwise comparison, alignment coverage calculation and the Comparative Sequence Priority Score (CSPS).

The computational engine is designed for general nucleotide FASTA analysis, with millet genomics serving as its current biological application context.

## 2. Input and Sequence Validation

The analysis begins with nucleotide sequences submitted in FASTA format.

The validation stage checks:

- FASTA headers and sequence content.
- Unique sequence identifiers.
- Valid nucleotide characters under the configured rules.
- Minimum requirement of two sequences for comparative analysis.
- Empty or invalid input records.
- Presence of the selected reference sequence.

The current prototype is documented as accepting unequal-length nucleotide sequences up to 500 bp.

Invalid records are rejected with an error message rather than silently modified.

## 3. Multiple Sequence Alignment

Validated nucleotide sequences are aligned using Clustal Omega.

The resulting Multiple Sequence Alignment establishes a common coordinate system for downstream calculations.

The same alignment is used for:

- Conservation analysis.
- Variable-position identification.
- Reference-based variant observations.
- Pairwise sequence identity.
- Alignment coverage.

This ensures that the reported sequence-level measurements are derived from the same alignment.

## 4. Conservation Analysis

An alignment column is classified as conserved when all analysed sequences carry the same nucleotide at that position, according to the implementation rule.

Overall conservation is calculated as:

Conservation (%) = (Number of conserved alignment columns / Total alignment columns) × 100

Conservation describes the analysed alignment. It does not independently establish the functional importance of a nucleotide or its relationship with a biological trait.

## 5. Sequence Variation Analysis

A variable alignment column contains more than one nucleotide.

The framework also records reference-based variant observations against an explicitly selected reference sequence.

Two measurements are kept distinct:

- Variable alignment positions: Number of alignment columns containing variation.
- Reference-based variant observations: Differences recorded relative to the selected reference.

Multiple sequences may differ from the reference at the same alignment position. Therefore, the number of variant observations may exceed the number of variable alignment positions.

## 6. Pairwise Identity

Pairwise identity measures nucleotide similarity between two aligned sequences.

The documented method considers positions where both sequences contain a residue.

Gap-gap and gap-residue positions are excluded from the denominator.

Mean Pairwise Identity (MPI) for a sequence is calculated as the average of its valid pairwise identity values against the other sequences.

This gap-aware approach supports comparisons involving sequences of unequal lengths.

## 7. Alignment Coverage

Alignment Coverage (AC) describes the proportion of the total alignment represented by non-gap residues in an individual sequence.

AC = Non-gap aligned positions represented by the sequence / Total alignment columns

Coverage is considered alongside identity because a sequence may show high similarity across a short region without representing the full alignment.

## 8. Reference Sequence Selection

Reference-based variation analysis requires an explicitly selected reference sequence from the submitted dataset.

In the demonstration dataset, the selected reference was:

"Millet_1_Sitalica"

The reference identifier is included in the output to make the comparison traceable and reproducible.

## 9. Comparative Sequence Priority Score (CSPS)

The framework combines Alignment Coverage and Mean Pairwise Identity through a geometric-mean-based metric.

CSPS = 100 × √(AC × MPI)

Where:

- AC: Alignment Coverage.
- MPI: Mean Pairwise Identity.

The geometric mean ensures that both similarity and coverage contribute to the score.

A high identity value cannot completely compensate for poor alignment coverage, and high coverage cannot completely compensate for low identity.

CSPS is intended to represent sequence comparability within the analysed dataset.

It is not a prediction of drought tolerance, heat tolerance, disease resistance, breeding superiority or field performance.

## 10. Biological Evidence Integration

Biological evidence is maintained separately from the numerical scoring process.

The project report discusses literature concerning stress-responsive genes, including SiARDP and SiHSF3, to provide biological context for further investigation.

Literature findings are not converted into arbitrary numerical bonuses or added to CSPS.

This separation prevents biological claims from being confused with sequence-derived measurements.

## 11. Computational Architecture

The documented prototype architecture consists of:

- Frontend: React and TypeScript.
- Backend API: FastAPI.
- Sequence processing: Python and Biopython.
- Multiple Sequence Alignment: Clustal Omega.
- Data exchange: Structured JSON responses.
- Result presentation: Report, scoring and recommendation interfaces.

The frontend collects input and displays results, while the backend performs sequence processing and returns structured analysis outputs.

## 12. Reproducibility Considerations

Reproducing a reported result requires retaining:

- Original input FASTA records.
- Selected reference sequence.
- Clustal Omega configuration.
- Software and dependency versions.
- Alignment output.
- Validation cases.
- Calculation definitions.

These materials should be maintained alongside future releases to allow independent verification.

## 13. Scientific Limitations

AgriGene Insight is a sequence-analysis and candidate-investigation framework.

Its numerical outputs do not establish biological function or phenotype.

Sequence similarity, conservation and alignment coverage must be interpreted within their computational context. Biological conclusions require supporting literature and, where appropriate, experimental or phenotypic validation.

---

Project: AgriGene Insight
Domain: Computational Biology | Bioinformatics | Comparative Genomics
Document: Computational Methodology
Status: Based on the project report; independent reproducibility work remains pending.
