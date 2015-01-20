# Union-intersection blog post

Recently, JJ Emerson wrote a [blog
post](http://samplingprocess.org/2015/01/19/measuring-differential-expression-in-the-context-of-isoforms/)
with some simulations on the union-intersection (UI) model
[[1](http://www.biomedcentral.com/1471-2105/11/94),
[2](http://master.bioconductor.org/help/course-materials/2009/SeattleNov09/RNASeq/RNASeqTools.pdf)].
This directory is dedicated to addressing those issues.

# Summary

(TODO: Write up a quick summary of what JJ did)

# Issues to address

## Assumptions

We should address the following assumptions:

- **Uniform coverage**: Coverage is almost never uniform in RNA-Seq. Bias is
  well known to exist. In such situations, the exonic regions one chooses can
  bias the estimate.

    - **Action item**: look at some recent data sets and plot the bias. One way
      is to use eXpress and simply look at the bias weights. We should look at
      least two data sets.
        - Data set: genentech data. (TODO: put a link)
    - **Action item**: write up some examples with real annotations where
      unequal coverage will bias your estimates
    - **Action item** (*theoretical*): One of the benefits of the "isoform normalization"
    approach (perhaps we should suggest a different name) is that the sampling, itself,
    happens at the level of individual transcripts.  This means that it makes more sense 
    (and is likely much more accurate) to learn bias models at the whole-transcript level
    rather than at the intersection level.  This suggests that more effective bias 
    correction can be done when considering entire isoforms as opposed to intersecting
    genomic regions.
    
- **Information available to union-intersection vs. isoform**: The union-intersection
  model *ignores* any information that is not unique to a particular gene.  This choice seems
  particularly problematic in the case of overlapping genes where the isoform-based approach
  can potentially incorporate much more information into the inference than the intersection
  based method.  Perhaps we can highlight an analysis of some genes to explore how what
  differences appear in this situation.

- **Sequencing depth**
    - (TODO)
