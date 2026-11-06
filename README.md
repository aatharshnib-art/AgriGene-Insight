# AgriGene Insight

### An Evidence-Based Computational Framework for Sequence Analysis and Candidate Prioritization in Millets

**AgriGene Insight** is an ongoing computational biology project designed to analyse nucleotide sequences and support evidence-based prioritization of disease-resistance gene candidates in cultivated and wild millet genotypes.

The project explores how multiple sequence alignment, conservation analysis, sequence variation analysis, and biological evidence integration can support comparative genomic investigations.

---

## Research Motivation

Millets are important climate-resilient crops. Understanding genetic variation in their wild and cultivated relatives can contribute to research on plant stress-response mechanisms and disease resistance.

AgriGene Insight aims to provide a structured computational workflow for comparing candidate gene sequences and organizing the resulting evidence.

## Research Objectives

- Develop a reproducible nucleotide FASTA analysis workflow.
- Perform multiple sequence alignment using Clustal Omega.
- Quantify sequence conservation across aligned positions.
- Identify substitutions, insertions, deletions, and variable regions.
- Compare sequence similarity between candidate sequences.
- Develop a transparent candidate prioritization framework.
- Integrate traceable biological evidence from literature and databases.

## Biological Context

The project focuses on comparative analysis involving:

- *Setaria italica* — cultivated foxtail millet.
- *Setaria viridis* — green foxtail, a wild relative.

**Current case-study direction:** SiHSF3, a heat-shock-factor-related candidate being investigated through literature and sequence evidence.

This case study is not a validated prediction of stress tolerance.

## Computational Workflow

1. FASTA sequence input
2. Sequence validation
3. Multiple sequence alignment using Clustal Omega
4. Conservation analysis
5. Sequence variation analysis
6. Pairwise sequence comparison
7. Candidate prioritization
8. Biological evidence integration
9. Structured report generation

## Technology Stack

| Area | Technologies |
|---|---|
| Programming | Python |
| Bioinformatics | Biopython |
| Multiple Sequence Alignment | Clustal Omega |
| Backend | FastAPI |
| Reporting | ReportLab |
| Data Analysis | NumPy, Pandas |

*Listed technologies represent the intended project stack; implementation and integration are ongoing.*

## Development Status

**Project stage: Prototype development and computational validation**

The project report documents a validation run using 10 nucleotide sequences.

### Reported Validation Results

- Input sequences: 10
- Conserved alignment positions: 51
- Variable alignment positions: 3
- Total alignment positions: 54
- Conservation percentage: 94.44%

These values describe the reported test dataset and should not be interpreted as general biological conclusions.

### Documented Computational Components

- [x] FASTA input and sequence validation
- [x] Multiple sequence alignment using Clustal Omega
- [x] Conservation analysis
- [x] Sequence variation analysis
- [x] Pairwise sequence comparison
- [x] Comparative Sequence Priority Score (CSPS) methodology
- [ ] Complete source-code integration into this repository
- [ ] Independent reproducibility testing
- [ ] Further validation using additional datasets

The computational results and prototype are documented in the project report. The complete implementation is not yet available in this repository.

## Scientific Scope and Limitations

AgriGene Insight is intended as a sequence-analysis and evidence-organization platform.

- Sequence similarity does not independently establish biological function.
- Conservation does not automatically indicate disease resistance.
- Candidate prioritization scores are not phenotype predictions.
- The framework does not currently claim to predict drought tolerance, heat tolerance, or breeding superiority.
- Biological interpretations require independent experimental or literature-based validation.

## Long-Term Direction

The long-term goal is to develop a reproducible and extensible computational framework that supports comparative sequence analysis and evidence-based candidate investigation in millet genomics.

---

## Project Information

- **Project:** AgriGene Insight
- **Domain:** Computational Biology | Bioinformatics | Comparative Genomics
- **Developer:** Aatharshni B
- **Institution:** Sathyabama Institute of Science and Technology, Chennai

*Building computational tools to investigate biological questions through reproducible analysis and evidence.*
