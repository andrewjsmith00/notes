The simple definition for polcy is some set of rules that controls the agent's behaviour. Even for simple environments there can be a variety of policies.

The main objective of [[Reinforcement Learning]] is to gather as much return as possible Different policies can give different amounts of return, which makes it important to find a good policy.

Formally, the policy is defined as the probability distribution over actions for every possible state:

$$
\pi(a|s) = P[A_t = a | S_t = s]
$$
This is defined as probability and not concrete to introduce randomness into the behaviour.

Another useful notion is that if a policy is fixed and not changing, then the [[Markov Decision Process]] becomes a [[Markov Reward Process]], as we can reduce the transition and reward matrices with a policy's probabilities and get rid of the action dimension.