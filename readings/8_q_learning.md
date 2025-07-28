# Q-Learning

## What if MDP is not known?

In many real-world scenarios, we don’t have access to the full MDP model — no transition probabilities, no reward function — just experience.

> **Q-learning** is a model-free reinforcement learning algorithm.
> It learns to act optimally by **interacting with the environment**, without ever knowing the full model.

Unlike value iteration, which plans before acting, Q-learning **learns as it goes** by updating estimates of how good specific actions are in specific states.

---

## The Q-Learning Update Rule

Each time the agent experiences a transition, it updates its Q-value for the (state, action) pair:

$$
Q(s, a) \leftarrow Q(s, a) + \alpha \left[ r + \gamma \max_{a'} Q(s', a') - Q(s, a) \right]
$$

Where:

* $\alpha$: learning rate
* $\gamma$: discount factor
* $r$: reward received after taking action $a$ in state $s$
* $s'$: next state
* $a'$: next possible action

> Q-values estimate the **expected future return** of taking an action in a state, and following the best policy afterward.

---

## ✏️ Your Task: Implement Q-LearningAgent

Open `qlearningAgents.py` and complete the `QLearningAgent` class. Select this agent in Gridworld with:

```bash
python gridworld.py -a q -k 5 -m
```

(Use `-m` for manual control; `-k` sets the number of episodes.)

What You Need to Implement

1. `getQValue(state, action)`

* Return the current Q-value of the given (state, action) pair.
* Default to 0.0 if it has never been seen before.

2. `computeValueFromQValues(state)`

* Return the maximum Q-value over all legal actions from this state.
* If no legal actions (e.g., terminal state), return 0.0.
* 💡 Only call `getQValue()` to access Q-values.

3. `computeActionFromQValues(state)`

* Return the action with the highest Q-value.
* Break ties randomly using `random.choice`.
* Return `None` if no legal actions.
* Only use `getQValue()` to access Q-values.

4. `update(state, action, nextState, reward)`

* Apply the Q-learning update rule.
* Update the Q-value of `(state, action)` based on observed `nextState` and `reward`.

---

## See in action

Let the Q-learner learn by interacting with the environment:

```bash
python gridworld.py -a q -k 5 -m
```

* Steer the agent using arrow keys.
* Watch how Q-values update for states it just left.
* Use `--noise 0.0` to turn off randomness during debugging:

```bash
python gridworld.py -a q -k 5 -m --noise 0.0
```

---

## Test Your Agent

Run the autograder to check correctness:

```bash
python autograder.py -q q6
```