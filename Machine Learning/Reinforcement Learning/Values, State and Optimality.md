## Value
Value is defined as the expected total reward (optionally discounted) that is obtainable from the state. In a formal way, the value of the state is:
$$
V(s) = \mathbb{E}[\sum_{t=0}^\infty r_t\gamma^t]
$$
where $r_t$ is the local reward obtained at step $t$ of the episode.

The total reward could be discounted with $\gamma$ or not (the undiscounted case corresponds to $\gamma = 1$).

The value is always calculated in terms of some policy that our agent follows. To illustrate this, we can consider a simple environment with 3 states:
1. The agent's initial state
2. The final state that the agent is in after executing the action "right" from the initial state. The reward is 1
3. The final state that the agent is in after action "down". The reward is 2

The environment is always deterministic - every action succeeds and we always start from state 1. Once state 2 or 3 is reached, the episiode ends.

So the question becomes, what is the value of state 1? This is meaningless without information on the policy. Even in a simple environment there can be infinite behaviours each with their own value for state 1. For example:
- Agent always goes down
- Agent always goes right
- Agent goes right with P=0.5 and down with P=0.5
- Agent goes right with P=0.1 and down with P=0.9

To demonstrate how this value is calculateed, we can do it for the above policies:
- The value of state1 for "always down" is 2.0 (every time it goes down, obtains 2 and episode over)
- For "always right" the value of state 1 is 1.0
- For 50% right/50% down, the value is (1.0\*0.5) + (2.0\*0.5) = 1.5
- For 10% right/90% down, the value is (1.0\*0.1) + (2.0\*0.9) = 1.9

So now the next question is: what is the best policy? The goal of RL is to get as much total reward as possible. For this one-step environment, the total reward is equal to the value of state 1, which at max is policy 1 (always down)


Formulating the optimal policy is hard and it is even harder to prove their optimality.

## Optimality
[[Bellman Equation of Optimality]]