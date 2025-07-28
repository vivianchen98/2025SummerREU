# Search

## Framing Pacman as a Search Problem

Before diving into specific search strategies, it's important to understand how a Pacman game can be **formalized as a search problem**. In artificial intelligence, this means defining a framework where an agent (Pacman) must find a sequence of actions that moves it from a starting state to a goal state.

:::{admonition} Components of a Search Problem
A search problem consists of the following:

- **State Space:** All possible configurations the agent can be in.
- **Start State:** The initial configuration where the agent begins.
- **Goal Test:** A function that determines if the current state is a goal.
- **Successor Function:** Returns possible next states and actions.
- **Path Cost:** The total cost of a sequence of actions.

The solution is a sequence of actions (a plan) that transforms the start state into a goal state.
:::

Go to `pacman_search` directory.
In this project, search problems are defined through the `SearchProblem` class in `search.py`:

```python
class SearchProblem:

    def getStartState(self):
        """
        Returns the start state for the search problem.
        """

    def isGoalState(self, state):
        """
          state: Search state

        Returns True if and only if the state is a valid goal state.
        """

    def getSuccessors(self, state):
        """
          state: Search state

        For a given state, this should return a list of triples, (successor,
        action, stepCost), where 'successor' is a successor to the current
        state, 'action' is the action required to get there, and 'stepCost' is
        the incremental cost of expanding to that successor.
        """

    def getCostOfActions(self, actions):
        """
         actions: A list of actions to take

        This method returns the total cost of a particular sequence of actions.
        The sequence must be composed of legal moves.
        """
```

---

## Why This Matters

By converting different Pacman tasks into search problems, we can use the same solution method for a variety of goals and layouts.

> The key is to define the problem clearly—then the same algorithm can handle many different cases.

---

## Search Algorithms

In the next sections, you’ll explore and compare:

- **Depth-First Search (DFS):** Explores as far as possible along each branch before backtracking.
- **Breadth-First Search (BFS):** Explores all nodes at the current depth before moving to the next level.

Both algorithms generate the same search tree, but the order in which they expand nodes (and the solutions they find) can be very different.

