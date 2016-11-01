Professor Forcing:

https://arxiv.org/pdf/1610.09038.pdf

-MILA used GAN to regularize generative rnns by having discriminator discriminate between teacher forced rnn hidden states (which are continuous/differentiable distributions) (as opposed to discrete outputs) and free running rnn hidden states.

-results in better training and test time NLL (even when length of generation is longer than length of training data points) and faster converence

-It's significantly harder to use GAN on outputs because they are discrete as (as opposed to continuous like the hidden states). They would have had to estimate discrete outputs with policy gradient like in seqGAN which is harder to get to converge, which is why they probably just stuck with the hidden states which already contain info about the output (the index of the highest probability in the the distribution) anyway. Professor Forcing method is unique in that one has access to the continuous probability distribution of each token at each timestep of the two sequence generation modes trying to be pushed closer together. Conversely, when applying GANs to pushing real samples and generated samples closer together as is traditionally done in models like seqGAN, one only has access to the next dicrete token (not continuous probability distributions of next token) at each timestep, which prevents straight-forward differentiation (used in professor forcing) from being applied and forces one to use policy gradient estimation.
