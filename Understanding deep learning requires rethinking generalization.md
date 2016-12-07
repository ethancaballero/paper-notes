https://arxiv.org/abs/1611.03530

tl;dr, vc-dimension (expressivity) does not necessarily correlate with generalization error
  
the fact that we use gradient descent to train might be what's causing this
  
why does it generalize to test data even though we don't have theoretical guarantees like we do with other model?

If we get better generalization theories than vc-dimension or rademacher complexity, we can probably design better regularizers than dropout, bachnorm, l2, etc.
