## 🧬 SpliceAI Interpretability via Transcriptome Perturbation
This project investigates what SpliceAI learns about splicing by introducing controlled perturbations to transcript sequences. Rather than treating SpliceAI as a black box, we use synthetic transcriptomes to dissect the sequence-level signals that drive its predictions.

We explore two strategies:

1. Sequence Shuffling Experiments
We generate modified transcriptomes by shuffling only exonic regions, using:

- Nucleotide Shuffling: Fully destroys local sequence context while preserving intron positions and splice junctions.

- Codon Shuffling: Retains 3-mer composition to preserve global grammar like GC content and coding frame, but disrupts known splicing motifs.

These perturbations allow us to separate SpliceAI's reliance on global structure from local motifs.

2. Motif Perturbation Experiments
We selectively shuffle or insert known RNA-binding protein motifs (e.g., SRSF1) near splice junctions to test:

- Whether SpliceAI uses these motifs to reinforce predictions

- How much confidence drops when these motifs are destroyed

Why This Matters
Our findings show that SpliceAI doesn't simply memorize GT/AG signals—it relies on a hierarchy of contextual features, combining:

- Global structure like codon usage and exon-intron patterns

- Localized regulatory grammar like splicing enhancer motifs

By systematically degrading or modifying these cues, we expose when and why SpliceAI fails, and what sequence logic it has learned to recognize.

