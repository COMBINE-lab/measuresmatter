# Introduction

This document presents a high-level outline of things we might want to talk
about.

# What is RNA-Seq *actually* measuring?

Explain protocol here at a high level necessary for understanding modeling of
RNA-Seq. Under the assumption we know everything about the experiment (i.e.
where the fragments are actually coming from) we know all of the isoforms, and
there are no biases, what is RNA-Seq measuring and what does each read
represent? This might help with the disconnect of why counting across genes is
a bad idea.

## Biases -- not all reads are created equal

We probably don't want to go into biases too much, but should probably discuss
length bias.

- Length bias (inherent in RNA-Seq design)
- Priming bias dependent on sample prep
- Other biases (lane effects?)

# Gene structure

- What is a "gene"?
    - Biology
        - Each isoform can theoretically be different functional product -- how
          does this translate to differential expression?
    - Models for gene expression
        - Gene counting models
            - Union-intersection (UI)
            - Union
            - What happens to multimapping reads? How many reads do you see
              multimappings across genes in real experiments? Might consider
              looking at the "mappability" of regions in the genome (I think
              there is an ENCODE track for this).
        - Abundance estimation of isoforms
            - Is a gene an aggregate of isoforms? Goes back to question of what
              a is gene biologically...
            - Dealing with multimapping reads
    - Comparisons of quantification to other experiments. Might want to discuss
      what the measurement actually means in RNA-Seq compared to other
      experiments.
        - RT-PCR
        - RT-qPCR
        - Microarray
    - Gene Annotations and their importance in RNA-Seq
        - Does taking a naive model of a gene, such as the UI model outperform
          a quantification method when the annotation is very clearly wrong or
          incomplete?
        - How does a bad annotation affect "gene" expression?

# Differential expression

- What does differential expression in RNA-Seq actually mean? If we knew where
  the reads came from, how would we compute "gene" expression and differential
  expression? Sum of isoform expression? A switch in relative isoform
  expression? This section might be a bit redundant with parts of the gene
  structure section.
- What does differential expression mean in other assays? What does it mean
  biologically?
- Do gene counts actually represent something meaningful? That is to say, if
  there is a statistical difference in the pileup of read counts, does this
  mean anything interesting biologically?
