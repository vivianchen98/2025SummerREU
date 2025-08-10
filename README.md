# Search & RL in Pacman

This Summer REU project investigates how intelligent agents can make decisions in dynamic environments with Pacman as a testbed. 

> **Acknowledgements**: The Pac-Man projects were originally developed for UC Berkeley's introductory artificial intelligence course.

## 📚 Project Overview

This repo has two main components:

### 1. [📖 Jupyter Book](https://vivianchen98.github.io/2025SummerREU/)

A guided learning path that covers:

1. **Search Algorithms** – DFS, BFS, and systematic exploration
2. **Markov Decision Processes** – Modeling sequential decision-making
3. **Value Iteration** – Dynamic programming for optimal policies
4. **Q-Learning** – Model-free reinforcement learning
5. **Approximate Q-Learning** – Generalizing with features to scale up

### 2. 🧪 Code Implementation

```
2025SummerREU/
├── pacman_search/                  # Search algorithms
│   ├── search.py                   # DFS, BFS, etc.
│   ├── searchAgents.py             # Agents that use search
│   └── ...                         
├── pacman_rl/                      # Reinforcement learning
│   ├── valueIterationAgents.py     # Value iteration agents
│   ├── qlearningAgents.py          # Q-learning & Approximate Q-learning
│   └── ...
```

## 🚀 Quick Start

## Before You Start

[**Project Setup 101**](https://boatneck-iberis-1aa.notion.site/Project-Setup-101-23a187290fc08029843bdb7cf3969231) covers basic Python, virtual environments, and Git to get you ready fast.

### Step 1: Clone and Set Up

```bash
git clone https://github.com/vivianchen98/2025SummerREU.git
cd 2025SummerREU
```

### Step 2: (Optional) Create Conda Environment

```bash
conda create -n pacman python=3.9
conda activate pacman
```

If you see missing packages during runtime (e.g., `numpy`), install them manually:

```bash
pip install numpy
```


## 🛠️ How to Use

1. Start by reading the [Jupyter Book](https://vivianchen98.github.io/2025SummerREU/)
2. Follow the instructions in each section
3. Implement and test your code in the corresponding Python files


## 📄 License

Portions of this project are adapted from UC Berkeley CS188.
See individual files for licensing and attribution.
