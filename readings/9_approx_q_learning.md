# Approximate Q-Learning

## Why Approximate Q-Learning?

Traditional Q-learning stores a separate value for **every (state, action) pair**, which becomes impractical in large or continuous state spaces.

> **Approximate Q-learning** allows us to generalize by representing Q-values as a **weighted sum of features**.
> This makes learning tractable even in huge environments, like full-sized Pacman grids.

---

## Q(s, a) as a Weighted Sum of Features

We define the Q-value for a (state, action) pair as:

$$
Q(s, a) = \sum_{i=1}^{n} f_i(s, a) \cdot w_i
$$

Where:

* $f_i(s, a)$: value of the $i$th feature for this state-action pair
* $w_i$: learned weight for that feature

---

## Weight Update Rule

After each experience (transition), update each weight as:

$$
w_i \leftarrow w_i + \alpha \cdot \text{difference} \cdot f_i(s, a)
$$

Where:

$$
\text{difference} = \left[ r + \gamma \max_{a'} Q(s', a') \right] - Q(s, a)
$$

> **Can you derive this weight update rule?**  
> *Hint:* Think about how to define a squared error loss between the target and predicted Q-value, and then use gradient descent to minimize that loss with respect to the weights.  

---

## ✏️ Your Task: Implement `ApproximateQAgent`

Open `qlearningAgents.py` and complete the `ApproximateQAgent` class, which is a subclass of `QLearningAgent`.

What You Need to Implement

1. `getQValue(state, action)`

* Return $Q(s, a) = \sum_i w_i \cdot f_i(s, a)$
* The feature vector is provided by a feature extractor as a `util.Counter`.

2. `update(state, action, nextState, reward)`

* Compute the TD error (difference).
* For each feature, update its weight using the rule above.

> Weights are stored as a dictionary: `self.weights[feature] = weight_value`

---

## Feature Extractors

The feature extractor defines what features are available. We provide:

* **IdentityExtractor** (default): One feature per (state, action) — no generalization.
* **SimpleExtractor**: General-purpose features for Pacman (e.g., distance to ghost, food).

Feature extractors return a `util.Counter` mapping feature names to values.

---

## Test with IdentityExtractor

First, confirm your approximate agent behaves like a basic Q-learning agent:

```bash
python pacman.py -p ApproximateQAgent -x 2000 -n 2010 -l smallGrid
```

---

## Generalize with SimpleExtractor

Now run with real features that enable generalization:

```bash
python pacman.py -p ApproximateQAgent -a extractor=SimpleExtractor -x 50 -n 60 -l mediumGrid
```

You should see your agent **learn to win reliably** in only 50 games.

Try it on larger layouts too:

```bash
python pacman.py -p ApproximateQAgent -a extractor=SimpleExtractor -x 50 -n 60 -l mediumClassic
```

---

## Grading

Run the autograder to verify your implementation:

```bash
python autograder.py -q q10
```

Congratulations! You have a learning Pacman agent!