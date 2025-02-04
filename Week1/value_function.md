# 📌 Value Function in Reinforcement Learning (RL)

In **Reinforcement Learning (RL)**, a **Value Function** estimates the expected cumulative reward an agent can obtain from a given state or action. It helps the agent evaluate different states and actions to make optimal decisions.

## 🔹 Types of Value Functions

1. **State-Value Function (V(s))**  
   - Measures the expected reward from state **s** under policy **π**.  
   - **Formula:**  
     ```math
     V^\pi(s) = \mathbb{E}_\pi \left[ \sum_{t=0}^{\infty} \gamma^t r_t | s_0 = s \right]
     ```

2. **Action-Value Function (Q(s, a))**  
   - Estimates the expected reward of taking action **a** in state **s** and following policy **π** afterward.  
   - **Formula:**  
     ```math
     Q^\pi(s, a) = \mathbb{E}_\pi \left[ \sum_{t=0}^{\infty} \gamma^t r_t | s_0 = s, a_0 = a \right]
     ```

Value functions are central to **value-based RL methods** like **Q-learning and Deep Q Networks (DQN)**. 🚀
