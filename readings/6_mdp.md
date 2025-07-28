# Markov Decision Processes

## What Is an MDP?

A **Markov Decision Process (MDP)** provides a formal framework for modeling decision-making under uncertainty. It consists of:

* **States** $S$: Possible configurations of the environment.
* **Actions** $A$: Available choices the agent can make.
* **Transitions** $T(s, a, s') = P(s' \mid s, a)$: Probability of reaching state $s'$ when taking action $a$ in state $s$.
* **Rewards** $R(s, a, s')$: The numeric feedback the agent receives after a transition.
* **Discount factor** $\gamma \in [0, 1]$: Determines how much future rewards are valued compared to immediate ones.

The goal of the agent is to learn a **policy** $\pi(s)$—a mapping from states to actions—that **maximizes expected total reward** over time.

> MDPs are *stochastic*, meaning the same action can lead to different outcomes!

---

## Explore Gridworld

The code will be in `pacman_rl` directory.

We’ll use a simple grid-based world to explore MDPs.

### Run Gridworld in Manual Mode

Start by moving the agent yourself:

```bash
python gridworld.py -m
```

* You’ll see a blue dot (the agent) and two exits (double boxes).
* Use arrow keys to move.
* Note: When you press **UP**, the agent only goes north **80%** of the time!

> This reflects **stochastic transitions** — just like in a real MDP!

---

## A Random Gridworld Agent

Run 
```bash
python gridworld.py -g MazeGrid
```

You’ll see the **default random agent** stumble around until it accidentally reaches an exit. Not ideal.

---
**Note:** In Gridworld, you must first enter a pre-terminal state (the double boxes in the GUI), then take the special `exit` action to actually finish the episode. The true terminal state (`TERMINAL_STATE`) is not shown in the GUI. 

If you play manually, your total return may be lower than expected because of the discount rate (default: 0.9, change with `-d`).

Check the console output for details about each transition (or use `-t` for text-only mode). To hide these messages, add `-q`.

---

## Coordinate System Reminder

Gridworld uses standard (x, y) Cartesian coordinates:

* Increasing **x** → moves **east (right)**
* Increasing **y** → moves **north (up)**

Arrays are indexed as `grid[x][y]`.