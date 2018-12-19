Translating Neuralese

https://arxiv.org/abs/1704.06960

Training Semantic Belief Translator (simplification):

x (state) is represented by hidden state of RNN that is trained to predict msg/actions/next_state given previous timesteps.
Q is kl div between x_robot & x_human from which Messages (z_robot & z_human) were respectively sent. 
(z_robot, z_human) pairs with lowest q are the best translations/dictionaries.

TODO: Try using more recent unsupervised translation methods in place of Semantic Belief Translation method.
