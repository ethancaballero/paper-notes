Hybrid computing using a neural network with dynamic external memory
https://www.dropbox.com/s/0a40xi702grx3dq/2016-graves.pdf

- changes from ntm: https://www.reddit.com/r/MachineLearning/comments/575hlx/research_new_nature_paper_by_deepmind_hybrid/d8p48rw
- temporal link keeps track of order that writes happened
- controller can choose whether or not to write anything to memory each timestep
- same controller can do transitive reasoning (a new read conditioned on read from previous timestep) during inference time.
- three attention: content, temporal, allocation
