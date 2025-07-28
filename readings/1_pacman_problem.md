# The Pacman Problem

:::{admonition} Why Pacman?
:class: tip

Although Pacman may look like a simple game, it captures many of the same challenges faced by intelligent agents in the real world. That’s what makes it a powerful learning tool!
:::

When Pacman chooses where to move next, it’s solving a version of the same problem faced by:

- 🤖 A robot navigating through a cluttered warehouse  
- 🚁 A drone planning a path while avoiding obstacles  
- 🧠 A recommendation system choosing what to suggest next  

---

## Elements of the Pacman Game

Before we dive into search algorithms, here’s a quick overview of the game elements you'll be working with:

- **🔲 Maze:**  
  A 2D grid of walls and open spaces.

- **👾 Pacman (the Agent):**  
  Moves in four directions; you'll control its logic.

- **🟢 Food Pellets:**  
  Pacman's goal is to eat as many as possible.

- **🟣 Ghosts (Optional):**  
  Moving threats that Pacman must avoid.

---

## ❓ The Problem the Agent Faces

Try it yourself!
```bash
cd pacman
python pacman.py
```
Play a few rounds and record your best score.
Now imagine designing an agent that plays autonomously — could it do better than you?

:::{admonition} As you play, consider these questions:
:class: important

- What does the agent know at each step?  
  Does it see the whole maze? Does it know where the food and ghosts are?

- What actions can the agent take?

- What changes after each move?  
    How does the world change? Does the agent get any feedback?
:::