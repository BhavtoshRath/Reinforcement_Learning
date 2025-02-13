# 📌 Value Function in Reinforcement Learning (RL)

In **Reinforcement Learning (RL)**, a **Value Function** `estimates the expected cumulative reward` an agent can obtain from a given state or action. 
It helps the agent `evaluate different states` and actions to make optimal decisions.

## 🔹 Types of Value Functions

1. **State-Value Function (V(s))**  
   - Measures the expected reward from state **s** under policy **π**.  
   - **Formula:**  
     ```math
     V^π(s) = \mathbb{E}_π \left[ \sum_{t=0}^{\infty} \gamma^t r_t | s_0 = s \right]
     ```

2. **Action-Value Function (Q(s, a))**  
   - Estimates the expected reward of taking action **a** in state **s** and following policy **π** afterward.  
   - **Formula:**  
     ```math
     Q^π(s, a) = \mathbb{E}_π \left[ \sum_{t=0}^{\infty} \gamma^t r_t | s_0 = s, a_0 = a \right]
     ```

Value functions are central to **value-based RL methods** like **Q-learning and Deep Q Networks (DQN)**. 🚀

---

| Feature            | **State-Value Function (`(V(s)`)** | **Action-Value Function (`Q(s, a)`)** |
|--------------------|---------------------------------|---------------------------------|
| **Definition**     | Expected return from state \(s\) following policy \( π \). | Expected return from taking action \( a \) in state \( s \) and then following policy \( π \). |
| **Depends on**     | Only the state \( s \). | Both the state \( s \) and the action \( a \). |
| **Purpose**        | Evaluates how good a state is under policy \( π \). | Evaluates how good a particular action is in a state under policy \( π \). |
| **Usage**          | Used in policy evaluation and value iteration methods. | Used in action selection (e.g., Q-learning, policy improvement). |
| **Example (Gridworld)** | In a simple 3×3 Gridworld, if the agent is at state (2,2), \( V(2,2) = 5.2 \) means the expected return from this state following policy \( π \) is 5.2. | \( Q(2,2, up) = 6.0 \) and \( Q(2,2, left) = 4.5 \) indicate that moving up from (2,2) is expected to give a higher return than moving left. |
