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
- **Sequencing depth**
    - (TODO)
