
---

# MDP Based RL Agent

Create a 100x100 grid with obstacles in between 2 random points. Build an MDP based RL agent to optimise both policies and actions at every state. Benchmark DP method with other RL solutions for the same problem.


1. **Environment Setup**:
   A 100 x 100 grid environment filled with obstacles all across it is constructed for the agent. The agent will start from one corner of the grid and must navigate to get to the opposite corner goal avoiding obstacles in each cell. Each cell represents the position of the agent. This includes obstacle cells and the goal cell for which a high reward is assigned.

2. **Formulation of MDP**:
   - **States**: All cells in the grid, approximately 10,000 numbers.
   - **Actions**: The agent can move up, down, left or right depending on the current positions and the obstacle cells.
   - **Transition Probability**: An action changes the position of the agent, unless the agent bumps into an obstacle or a boundary and remains in that cell and pays a penalty.
   - **Reward**: A reward structure that encourages fast attainment of the goal state. A large reward is given to the goal cell, whereas obstacles pay penalties. There is a small penalty to each cell related to the step taken.
   - **Discount Factor α**: It is designed so that it equilibrates short-term and long-term rewards. Hence making the agent head paths towards the goal without taking any detours.


**MDP-Agent with policy and action learning**:
1. **Value Iteration**: This method calculates the value of every cell by working out the expected outcome arising from any move. This is continued until it eventually finds the best choice for any position. Therefore, this method constructs a policy an agent could use to actually achieve his goal efficiently.
2. **Q-Learning**: In this approach, the agent explores the grid by trial and error, tries the actions, and learns from each move. It learns which action gives a better reward after many trials and refines its choice. Q-Learning is flexible and can adapt to changing environments since it uses the experiences it has to decide rather than a predetermined map.

**Value Iteration vs. Q-Learning**:
   - **Speed of Convergence**: Value Iteration converges relatively fast as it works under full information of the grid. However, Q-Learning takes much more time to converge as it is discovering the grid and learning by experience in a big grid.
   - **Adaptability**: Q-learning adapts well if the environment changes, say, with the introduction of new obstacles. It is a learning rather than knowing in advance, exactly how the environment is going to be. Value Iteration, on the other hand, being efficient, requires a fixed environment.

---
