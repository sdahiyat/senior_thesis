# SpliceAI Interpretability via Transcriptome Perturbation

This project investigates what the deep learning model [SpliceAI](https://github.com/Illumina/SpliceAI) learns about splicing by introducing controlled perturbations to transcript sequences. We use synthetic transcriptomes to dissect the sequence-level signals that drive its predictions.

## Overview

We explore two classes of experiments:

### 1. Sequence Shuffling Experiments

We generate perturbed transcriptomes by modifying only **exonic regions**, preserving splice junctions and introns.

- **Nucleotide Shuffling**: Destroys local sequence context by fully randomizing each exon, while retaining exon-intron architecture.
- **Codon Shuffling**: Shuffles codons (3-mers) instead of single nucleotides to preserve GC content and coding frame, while disrupting known motifs.

These perturbations test whether SpliceAI's performance depends on:
- Global structure (e.g., codon bias, exon length)
- Local motif presence (e.g., splicing enhancers)

### 2. Motif Perturbation Experiments

We selectively manipulate known RNA-binding protein motifs, such as **SRSF1**, using position weight matrices (PWMs). We test whether:
- SpliceAI prediction scores drop when motifs are scrambled
- Introducing motifs can boost splicing confidence at weak junctions

---

## Reproducibility

Scripts used to preprocess data, shuffle sequences, and run SpliceAI are included. This complements the formal reproducibility appendix in my report.

### Requirements

- Python ≥ 3.8
- [SpliceAI](https://github.com/Illumina/SpliceAI)
- Biopython, NumPy, Pandas
- PyTorch (for GPU inference)

To install dependencies:

```bash
pip install -r requirements.txt
