# Breadth-First Search (BFS)

Imagine you're exploring a maze again — but this time, instead of diving deep into one path, you explore all possible paths that are just one step away, then all paths that are two steps away, and so on.

That’s Breadth-First Search (BFS) — it explores the shallowest (closest) nodes first.


## ✏️ Your Task: Implement BFS
In the same file where you wrote DFS (`search.py`), find the function stub for `breadthFirstSearch`:
```python
def breadthFirstSearch(problem):
    """
    Search the shallowest nodes in the search tree first.
    Returns a list of actions to reach the goal.
    """
    "*** YOUR CODE HERE ***"
```
Replace the placeholder with a working graph-based BFS algorithm.


## Test your BFS Agent
Use the following commands to test your implementation:
```bash
python pacman.py -l mediumMaze -p SearchAgent -a fn=bfs
python pacman.py -l bigMaze -p SearchAgent -a fn=bfs -z .5
```

## Try BFS on a New Puzzle
If your code is general (and it should be!), it should also work on other problems — like the classic 8-puzzle!
```bash
python eightpuzzle.py
```
Try it and see BFS solving a sliding-tile puzzle!


## Run the Autograder
To make sure your BFS is working correctly, run:
```bash
python autograder.py -q q2
```