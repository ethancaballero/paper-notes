Professor Forcing:
https://arxiv.org/pdf/1610.09038.pdf
^MILA used GAN to regularize generative rnns by having discriminator discriminate between teacher forced rnn hidden states (which are continuous/differentiable distributions) (as opposed to discrete outputs) and free running rnn hidden states.
^results in better training and test time NLL (even when length of generation is longer than length of training data points) and faster converence
