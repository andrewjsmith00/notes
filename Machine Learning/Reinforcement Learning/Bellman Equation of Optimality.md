This is a deterministic case where all actions have 100% guaranteed outcome.

Imagine an agent that observes state $s_0$ and has $N$ available actions. Each action leads to another state with it's own reward. Also assume all values for all states is known. What is the best course of action that the agent can take in such a state

If action $a_i$ is chosen, the value needs to be calculated for this action. This value will be $V_0(a=a_i) = r_i + V_i$. So to choose the best possible action, the agent needs to calculate the resulting values for every action and choose the maximum possible. In other words:
$$
V_0 = max_{a\in1...N}(r_a + V_a)
$$

If we are using the discount factor $\gamma$, the value of the next state needs to be multiplied by gamma:
$$
V_0 = max_{a\in1...N}(r_a + \gamma V_a)
$$

This looks like the greedy example from the previous section, but there is a difference. When acting greedily, the immediate reward is not the only thing looked at, but also the long-term value of the state.

Bellman proved that with extension, the behaviour will get the best possible outcome. So the preceding equation is called the Bellman equation of value (for a deterministic case).

It's not complicated to extend this to a stochastic case, when our actions have the chance of ending up in different states. To do this, calculate the expected value for every action, instead of just taking the value for the next state.
For example, let's consider a single action available from state $s_{0}$ with three possible outcomes.

Here one action can lead to three different states wtih different probabilities. With probability $p_1$, the action can end up in state $s_{1}$ with $p_2$ in state $s_{2}$ and with $p_3$ in state $s_3$. Each target state has its own reward. To calculate the expected value after issuing action 1, we need to sum all values multiplied by their probabilities:
$$
V_0(a = 1) = p_1(r_1 + \gamma V_1) + p_2(r_2 + \gamma V_2) + p_3(r_3 + \gamma V_3)
$$

Or formally:
$$
V_0(a) = \mathbb{E}_{s\~S}[r_{s,a} + \gamma V_s] = \sum_{s\in S}p_{a,0 \rightarrow s}(r_{s,a} + \gamma V_s) 
$$
By combining the Bellman equation we get:
$$
V_0 = max_{a\in A} \mathbb{E}_{s \~ S}[r_{s,a} + \gamma V_s] = max_{a\in A} \sum_{s\in S} p_{a, 0 \rightarrow s}(r_{s,a} + \gamma V_s)
$$

Note that $p_{a,i \rightarrow j}$ means the probability of action $a$, issued in state $i$, ending up in state $j$.

The interpretation is still the same. The optimal value of the state is equal to the action, which gives the maximum possible expected immediate reward, plus the discounted long-term reward for the next state.
You may also see that this is recursive. The value of the state is defined via values of the immediately reachable states. 

These values not only give the best reward that can be obtained but also the best policy to obtain that reward. If the agent knows the value for every statem then it knows how to gather all this reward. With the proof, at every state the agent is in, itneeds to select the action with the max reward, which is a sum of the immediate reward and the one-step discounted long-term reward.

## The value of the action
Different quantities can be defined, in addition to the value of the state $V(s)$, as the value of the action $Q(s,a)$. This value is the total reward that can be achieved by executing action $a$ in state $s$ and can be defined via $V(s)$.
Being much less fundamental than $V(s)$, this quantity gave a name to the family of methods called Q-learning because it is more convenient.

In these methods, the primary objective is to get values of $Q$ for all pairs of state and action.
$$
Q(s,a) = \mathbb{E}_{s\prime \~ S}[r(s,a) + \gamma V(s\prime)] = \sum_{s\prime \in S}p_{a,s \rightarrow s\prime}(r(s,a) + \gamma V(s\prime)) 
$$
$Q$ for this state, $s$ and action $a$, is equal to the expected immediate reward and the discounted long-term reward of the desinationstate. $V(s)$ can also be defined via $Q(s,a)$:
$$
V(s) = max_{a \in A} Q(s,a)
$$

This means the value for some state is equal to the value of the maximum action that can be executed from this state. Finally, $Q(s,a)$ can be expressed recursively:
$$
Q(s,a) = r(s,a) + \gamma max_{a\prime \in A} Q(s\prime,a\prime)
$$

In this formula, the index on the immediate reward, $s$,$a$, depends on environment details. If immediate reward is given to us after executing a particular action $a$, from state $s$, index ($s$, $a$) is used and the formula is exactly as above. But if reward is provided for reaching some state $s\prime$ via action $a\prime$ the reward will have the index ($s\prime$,$a\prime$) and will need to be moved into the max operator. That difference would not be very significant mathematically but could be important during the implementation of the methods.
