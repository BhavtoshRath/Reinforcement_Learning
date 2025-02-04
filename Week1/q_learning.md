# 🤖 Q-learning: A Reinforcement Learning Algorithm

**Q-learning** is a value-based **Reinforcement Learning (RL)** algorithm used to find the optimal action-selection policy. It learns the **Q-value (Q(s, a))**, which represents the expected cumulative reward for taking action **a** in state **s** and following the optimal policy thereafter.

## 🔹 Key Concepts

- **Bellman Equation (Q-value Update):**  
  ```math
  Q(s, a) \leftarrow Q(s, a) + \alpha \left[ r + \gamma \max_{a'} Q(s', a') - Q(s, a) \right]


- **Exploration vs. Exploitation:**
  - Uses an ε-greedy strategy to balance trying new actions (exploration) and choosing the best-known action (exploitation).
- **Off-policy Learning:**
  - Learns the optimal policy independent of the agent’s actions.


Q-learning is widely used in robotics, game AI, and autonomous systems.