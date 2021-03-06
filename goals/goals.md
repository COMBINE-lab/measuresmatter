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

One *key* idea here is that the notion of a gene, in the context of RNA-seq
experiments, is a conceptual (and computational) convenience.  In fact, while
it is the most prevalent such abstraction, it may not even be the most advantageous.

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
            - What is the biological interpretation of 'gene expression' using these models?
            - What would be a natural interpretation of 'gene expression', and can we derive a model that supports that interpretation? show that it requires isoform-level abundance estimation.
        - Abundance estimation of isoforms
            - Is a gene an aggregate of isoforms? Goes back to question of what
              a is gene biologically...
            - Dealing with multimapping reads
            - What is the biological interpretation of 'isoform expression'?
        - What difference does the choice make? Does it matter?
            - worked examples/simulations illustrating:
                - what kinds of errors arise from gene vs. isoform models, under what conditions?
                - the magnitude of the differences (e.g. how gene counting error scales with isoform [length/expression] differential)
                - how prevalent these errors might be in real data
        - Units of expression and how they affect interpretation.
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
            - If so, *why* does this happen, and can it be avoided?
        - How does a bad annotation affect "gene" expression?
        - How should one consider the multitude of contigs produced by many *de
          novo* assemblers?  Tools like
          [Corset](http://genomebiology.com/2014/15/7/410) exist to solve
          problems like this but, unfortunately, still rely on counting and are
          subject to the same theoretical and conceptual difficulties.

# Differential expression

- What does differential expression in RNA-Seq actually mean? If we knew where
  the reads came from, how would we compute "gene" expression and differential
  expression? Sum of isoform expression? A switch in relative isoform
  expression? This section might be a bit redundant with parts of the gene
  structure section. (*Note*: While many of the same caveats that apply to
  quantification also apply to DE, I believe that it is nonetheless important
  for this content to have section in its own right.  While the caveats may
  be the same, the nature of the analysis and the potential nature of the errors
  may be different).
- What does differential expression mean in other assays? What does it mean
  biologically?
- Do gene counts actually represent something meaningful? That is to say, if
  there is a statistical difference in the pileup of read counts, does this
  mean anything interesting biologically?

# Recommended pipelines
TODO...
