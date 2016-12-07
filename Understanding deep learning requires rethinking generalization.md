https://arxiv.org/abs/1611.03530

This paper is a more approachable version of this paper:
  * Train faster, generalize better: Stability of stochastic gradient descent
    https://arxiv.org/pdf/1509.01240.pdf


tl;dr, vc-dimension (expressivity) does not necessarily correlate with generalization error
  
the fact that we use gradient descent to train might be what's causing this
  
why does it generalize to test data even though we don't have theoretical guarantees like we do with other model?

If we get better generalization theories than vc-dimension or rademacher complexity, we can probably design better regularizers than dropout, bachnorm, l2, etc.
