# Models for gene expression

Currently, there are two main schools of thought when it comes to measuring
_gene expression_: raw counts and expected counts (Note: expected counts are
_always_ defined with respect to some model, M).

## Raw count models

In this section we will review "raw count models." Raw counts typically refer
to _uniquely mapping_ counts across a gene. The notion of a "gene" is
defined in several different ways, but typically refers to aggregating isoforms
into one set of genomic coordinates. After aggregation, the number of reads
which uniquely map to only this specific genomic location are referred to as
the count of the gene, which serves as a proxy for gene expression.


### Intersection model

Perhaps the most popular (is this true?) raw counts model is the
union-intersection (UI) model first described in Bulled _et. al._. We (and
others) refer to
it as the _intersection_ as the use of union can add to confusion with the
_union_ model which is conceptually different.

The _intersection_ step involves taking the intersection of exonic regions
across all isoforms in a gene (exonic regions which are contained in every
isoform of the gene). The union part refers to taking the union of all of these
regions (see Figure X). Exonic regions which overlap which overlap exonic
regions of other genes are discarded.

TODO: find which tools implement UI

TODO: cite a few papers using UI

### Union model

The union model, implemented in HTSeq [@anders2014htseq] is also widely used. In this
model, a gene is constructed as the union of all exonic regions (Figure X).
Note, the use of _union_ here is different than in the UI model.

### Other models

(TODO: let's discuss original Marioni paper?)

### References

@article{anders2014htseq,
  title={HTSeq--A Python framework to work with high-throughput sequencing data},
  author={Anders, Simon and Pyl, Paul Theodor and Huber, Wolfgang},
  journal={Bioinformatics},
  pages={btu638},
  year={2014},
  publisher={Oxford Univ Press}
}
