# Depth-First Search (DFS)

Imagine you're exploring a maze. At every fork, you pick a direction and keep going forward until you hit a wall or reach the goal. Only when you're stuck do you go back and try the next unexplored path.

That’s Depth-First Search (DFS) — always explore deeply before trying alternatives.

## Test setup
First, test that the `SearchAgent` is working correctly by running:
```bash
python pacman.py -l tinyMaze -p SearchAgent -a fn=tinyMazeSearch
```
The command above tells the `SearchAgent` to use `tinyMazeSearch` as its search algorithm, which is implemented in `search.py`. Pacman should navigate the maze successfully.


## ✏️ Your Task: Implement DFS
In `searchAgents.py`, you'll find a fully implemented `SearchAgent`, which plans out a path through Pacman's world and then executes that path step-by-step. Your job is to complete the `depthFirstSearch` function in `search.py`.

```python
def depthFirstSearch(problem):
    """
    Search the deepest nodes in the search tree first.
    Returns a list of actions to reach the goal.
    """
    "*** YOUR CODE HERE ***"
```

Important note: All of your search functions need to return a list of actions that will lead the agent from the start to the goal. These actions all have to be legal moves (valid directions, no moving through walls).

Important note: Make sure to use the Stack, Queue and PriorityQueue data structures provided to you in `util.py`! These data structure implementations have particular properties which are required for compatibility with the autograder.

## Test your DFS Agent
Your code should quickly find a solution for:

```bash
python pacman.py -l tinyMaze -p SearchAgent
python pacman.py -l mediumMaze -p SearchAgent
python pacman.py -l bigMaze -z .5 -p SearchAgent
```

The Pacman board will show an overlay of the states explored, and the order in which they were explored (brighter red means earlier exploration). 

Is the exploration order what you would have expected? Does Pacman actually go to all the explored squares on his way to the goal?

## Run the Autograder
Run the autograder to verify your implementation is correct:

```bash
python autograder.py -q q1
```