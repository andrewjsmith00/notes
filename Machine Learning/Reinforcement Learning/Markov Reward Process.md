To introduce reward, the [[Markov Process]] model a little bit. First a value needs to be added to the transition between states. The probability is already there which captures the dynamocs of the system, but an extra number needs to be added without burden.

Reward can be represented in many ways. The most general way is to have another square matrix, similar to the transition matrix, with reward given for transitioning from state *i* to *j*, which resides in row *i* and column *j*.

Reward can be positive or negative, large or small. In some cases, this representation is redundant and can be simplified. For example, if reward is given for reaching the state regardless of the previous, we can keep only **state** -> **reward** pairs, which are a more compact representation. But this is applicable only if the reward value depends solely on the target state which is not only the case.

The second thing we add to the model is the discount factor $\gamma$ (gamma), which is a single number from 0 to 1.

We observe a chain of state transitions in a [[Markov Process]]. This is the same for a Markov Reward Process, but for each transition there's a new value, the reward. So all observations now have a reward attached for each transition.

For every episode, we define **return** at time *t* as:

$$
G_t = R_{t+1} + \gamma R_{t+2} + ... = \sum_{k=0}^\infty{\gamma^k R_{t+k+1}}
$$
What this means:
For every point in time, the return is the sum of subsequent rewards, but more distant rewards are multiplied by the discount factor raised to the power of the number of steps away it is from *t*. The discount factor is the foresightedness of the agent. If gamma is 1, the return is the sum of all subsequent reards and the agent has perfect visibility of all subsequent rewards. If gamma is 0, the return is the immediate reward without any subsequent state and is absolute short-sightedness.

These extreme values are only useful in corner cases, and most of the time gamma will sit around 0.9 to 0.99. This means we look at future rewards but not too far. The value of $\gamma = 1$ might only be applicable of short finite episodes.

Gamma is important for [[Reinforcement Learning]], and it comes up a bit. For now, think of it about how far into the future to look into to estimate for future return. The closer it is to one, the more steps ahead are taken into account.

This is not very useful in practice, as it was defined for every specific chain observed from the Markov reward process, so it can vary widely even just for the same state. However if we calculate the expectation of return for any state (by averaging a large number of chains), we will get a much more useful quantity called the **value of the state**

$$
V(s) = \mathbb{E}[G|S_t = s]
$$

This means that for every state *s*, the value, *V(s)*, is the average (or expected) return we get by following the Markov reward process.
