## Actions
To extend a [[Markov Reward Process]] to include actions we have to add a finite set of actions *A*. This is the agent's **action space**. Second, we need to change the transition matrix with actions, which adds a new dimension, making it a cube.

Before with the [[Markov Process]] and [[Markov Reward Process]], the transition matrix was a sqaure, with the source state in the row and target in the columns. So every row *i* contained the list of probabilities to jump to every state.

Now the agent no longer passively observes the transitions but can instead choose an action to take at every transition. So for every state, don't have a list of numbers but a matrix, where the **depth dimension** is the actions the agent can take, and the other dimension is the target state the agent will be in after performing the action. Each cell is the probability for transition $i \rightarrow j$ given action $k$.

In general, by choosing an action the agent can affect the probabilities of the target state, which is quite useful.






