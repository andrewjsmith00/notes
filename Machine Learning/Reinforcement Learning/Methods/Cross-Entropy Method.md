The cross-entropy method falls under the [[Model-Free Method]] and [[Policy-Based Method]] categories of [[RL Methods]].

This method:
- Doesn;t build a model of the environment, it just says what to do next
- Approximates the policy
- Requires fresh data obtained from the environment

## In practice
This method's description is in two parts, the practical which is intuitive, and the theoretical which is why it works.

The policy is usually represented as a probability distribution over actions, which makes it similar to a classification problem, with the amount of classes being the amount of actions.

This abstraction makes the agent fairly smple. The agent needs to pass an observation from the environment to a neural network, get a probability distribution over the actions, and perform random sampling using the probability distribution to get the action to take. This random sampling adds randomness to the agent which is good.

During the lifetime of an agent, it's experience is presented as episodes. Each episode is a sequence of observations that the agent got from the environment, actions it took and rewards for those actions.
For every episode, the total reward that the agent receives is calculated It can be discounted or not discounted.

The core of the cross-entropy method is to throw away bad episodes and train on better ones. So the steps look like:
1. Play *N* number of episodes with the current model and environment
2. Calculate the total reward for each episode and decide on a reward boundary. This is normally done by using a percentile of all rewards.
3. Throw away all episodes with a reward below the boundary
4. Train on the remaining episodes with observations as input and issued actions as output
5. Repeat from step 1 until the process is good.