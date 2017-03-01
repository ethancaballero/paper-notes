# Bridging the Gap Between Value and Policy Based Reinforcement Learning

https://arxiv.org/abs/1702.08892

Acknowledging that γ-discounted entropy regularization is used in reward expectation, they formulate a new notion of softmax temporal consistency for optimal Q-values as: 
Q∗(s,a) = r(s,a)+γτ log a′ exp(Q∗(s′,a′)/τ) .

They then introduce a new RL algorithm called Path Consistency Learning (PCL) that extends this softmax temporal consistency to arbitrary (multi-step) trajectories. Pseudocode of PCL Algorithm can be seen in Section 3.5 .

Unlike algorithms using Qπ- values, PCL seamlessly combines on-policy and off-policy traces. Unlike algorithms based on hard-max consistency and Q◦-values, PCL easily generalizes to multi-step backups on arbitrary paths, while maintaining proper regularization and consistent mathematical justification (that they outline in Section 3 and the appendix).


PCL is similar to A3C (and actor-critics in general) and PGQ (policy gradient q-learning) [arxiv:1611.01626], but has some key differences/improvements.

A3C vs PCL:
In comparison to A3C, PCL’s advantage function is more aligned with rewards in that advantage is 0 on every trajectory for its optimal policy, which is not the case for A3C. Also, PCL’s value function is not dependent on the current policy.

PGQ vs PCL:
PQQ relates the optimal policy to the hard-max Qvalues in the limit of τ = 0, and thus proposes to augment the actor-critic objective with offline updates that minimize a set of single-step hard-max Bellman errors; PQQ's weakness is assuming limit of τ = 0 (τ is entropy).
PCL extends the relationship to τ > 0 by exploiting a notion of softmax consistency of Q-values.


They compare performance of PCL, A3C, & DQN on the algorithmic tasks from OpenAI Gym, and PCL outperforms or equates A3C & DQN on all tasks.

Most impressively in my opinion:
PCL can incorporate expert trajectories very easily and very effectively.
Inserting just 10 expert trajectories in a size 400 batch drastically improves performance (e.g. solving tasks with max reward in just ~50 iterations as opposed to only getting to ~half of max reward after 4000 iterations).
They did not perform a direct comparison of effect of adding in expert trajectories to other RL algorithms (mostly because it’s more complicated to do so for others).
This attribute could be very useful for tasks with a few expert trajectories such as Description2Code.
