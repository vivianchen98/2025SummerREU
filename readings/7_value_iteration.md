# Value Iteration

## How to solve a given MDP?
Given a known MDP, you don’t need to explore through trial and error.
Instead, you can plan ahead to compute the best possible strategy before acting.

> Value Iteration is a method for solving MDPs by repeatedly applying the **Bellman update** to estimate the best long-term value of each state.

This lets the agent build a value function and derive an optimal policy — without ever stepping into the world.

---

## The Bellman Update

To find the best action in each state, we use the **Bellman optimality equation**:

$$
V_{k+1}(s) = \max_{a \in \mathcal{A}(s)} \sum_{s'} T(s, a, s') \left[ R(s, a, s') + \gamma V_k(s') \right]
$$

Where:

* $V_k(s)$: estimate of the value at state $s$ after $k$ iterations
* $\gamma$: discount factor
* $\mathcal{A}(s)$: set of legal actions in state $s$

You iteratively apply this update to all states until values converge.

> The value of a state is the **expected reward** of the best action, assuming future values are accurate.

---

## ✏️ Your Task: Implement Value Iteration

Open the file `valueIterationAgents.py`. You'll complete the class:
```python
class ValueIterationAgent(ValueEstimationAgent):
    def __init__(self, mdp, discount=0.9, iterations=100):
        ...
```

in which you need to implement the functions:

1. `runValueIteration(self)`

    * Loop for the given number of iterations.
    * For each state:
        * Skip if terminal.
        * Compute Q-values for all possible actions.
        * Set the state’s value to the max Q-value.
    * Use a copied value map each iteration (batch update).

2. `computeQValueFromValues(state, action)`

   * Compute the Q-value of a state-action pair using the current value estimates:

     $$
     Q(s, a) = \sum_{s'} P(s, a, s') \left[ R(s, a, s') + \gamma V(s') \right]
     $$

3. `computeActionFromValues(state)`

   * Return the best action from the current value function:

     $$
     \pi(s) = \arg\max_a Q(s, a)
     $$

---

## Test Your Implementation

To see your `ValueIterationAgent` in action:
```bash
python gridworld.py -a value -i 100 -k 10
```
This command loads your `ValueIterationAgent`, which will compute a policy and execute it 10 times. Press a key to cycle through values, Q-values, and the simulation. You should find that the value of the start state (V(start), which you can read off of the GUI) and the empirical resulting average reward (printed after the 10 rounds of execution finish) are quite close.

Run the autograder:

```bash
python autograder.py -q q1
```
