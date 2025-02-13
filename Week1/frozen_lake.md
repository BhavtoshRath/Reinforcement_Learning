## FrozenLake Reinforcement Learning (RL) Problem

### **Objective**
Navigate a frozen grid world to reach the goal while avoiding holes. The environment can be deterministic or stochastic, simulating slippery ice.

### **Environment Details**
- **Grid Size:** `4x4` (default) or `8x8` (larger challenge)
- **State Space:** Discrete, representing each cell in the grid.
- **Action Space (Discrete 4):**
  - `0` → Left  
  - `1` → Down  
  - `2` → Right  
  - `3` → Up  

### **Grid Layout (`S = Start, G = Goal, H = Hole, F = Frozen Surface`)**
```
S  F  F  F  
F  H  F  H  
F  F  F  H  
H  F  F  G  
```

### **Rewards & Termination**
- Reward **+1** for reaching the goal (`G`).
- Episode **ends** if the agent falls into a hole (`H`) or reaches the goal (`G`).

### **Two Versions**
1. **Deterministic (`is_slippery=False`)** – Moves exactly as chosen.
2. **Stochastic (`is_slippery=True`)** – Movement has some randomness, simulating slipperiness.

### **Goal**
Find an optimal policy that **maximizes the chance of reaching the goal** while avoiding holes.

### **Popular RL Algorithms Used**
- **Dynamic Programming (Value Iteration, Policy Iteration)**
- **Q-Learning (Table-based)**
- **Deep Q-Networks (DQN) (for larger grids)**

This problem is widely used to test RL algorithms' ability to handle **stochastic environments** and **optimal pathfinding strategies**.
