# Dynamic Programming in Reinforcement Learning

## Overview
- Dynamic Programming (DP) is a set of algorithms used to solve Markov Decision Processes (Environments are MDP) when the environment's transition dynamics are known. 
- It relies on recursive Bellman equations to compute optimal policies.
- DP methods assume a finite MDP where states, actions, and rewards are discrete.

GOAL: Optimize policy to maximize future reward.

## Key Concepts


Policy Evaluation, also known as the Prediction Problem, aims to compute the state-value function  for a given policy .

### 1. Bellman Equations in DP
Bellman equations form the foundation of DP methods by describing the relationship between the value of a state and the values of its successor states. They provide a recursive way to compute optimal value functions and policies.

#### Bellman Expectation Equation for Value Function
For a given policy ( π ), the value function ( V_π(s) ) represents the expected cumulative reward starting from state ( s ) and following policy ( π ). It satisfies the equation:

```math
V_π(s) = \sum_{a} π(a | s) \sum_{s'} P(s' | s, a) [R(s, a, s') + \gamma V_π(s')]
```

#### Bellman Optimality Equation
The Bellman optimality equation defines the value function under the optimal policy ( π^* ), which maximizes expected rewards:

```math
V^*(s) = \max_{a} \sum_{s'} P(s' | s, a) [R(s, a, s') + \gamma V^*(s')]
```

## Example: Grid World
### Grid Setup
Consider a **4x4 Grid World**, where:
- The agent moves in four directions (Up, Down, Left, Right).
- The goal is at the bottom-right corner.
- The agent receives a reward of **+1** at the goal and **-1** for all other moves.
- The transition is **deterministic**.
- Discount Factor ( \gamma = 0.9 ).

#### **Grid Representation (State Numbers)**
```
0   1   2   3  
4   5   6   7  
8   9   10  11  
12  13  14  15  (Goal)
```

### Bellman Expectation Equation (Policy Evaluation)
If the agent follows a **random policy** (equal probability for each action), the value function is computed iteratively:

```math
V(s) = \sum_{a} π(a | s) \sum_{s'} P(s' | s, a) [R(s, a, s') + \gamma V(s')]
```

For state **10**, possible moves are **Right (11), Left (9), Up (6), Down (14)**. The expected value is the average of the rewards plus the discounted values of the next states.

### Bellman Optimality Equation (Value Iteration)
Instead of averaging across all actions, we compute the **best action**:

```math
V^*(s) = \max_a \sum_{s'} P(s' | s, a) [R(s, a, s') + \gamma V^*(s')]
```

For **state 14**, possible moves:
- **Right to 15 (goal, ( V(15) = 1 ))**
- **Left to 13**
- **Up to 10**

Using Value Iteration:

```math
V^*(14) = \max \{ -1 + 0.9 \times 1, -1 + 0.9 \times V(13), -1 + 0.9 \times V(10) \}
```

```math
V^*(14) = \max \{ -0.1, -1, -1 \} = -0.1
```

Thus, the best move from **state 14** is **Right to 15**.

### Extracting the Optimal Policy
After computing the optimal values, we derive the best policy:

```math
π^*(s) = \arg\max_a \sum_{s'} P(s' | s, a) [R(s, a, s') + \gamma V^*(s')]
```

#### **Final Value Grid After Convergence**
```
-3.8  -3.4  -3.0  -2.7  
-3.4  -3.0  -2.6  -2.3  
-3.0  -2.6  -2.2  -1.9  
-2.7  -2.3  -1.9  1.0 (Goal)
```

#### **Optimal Policy Representation**
```
→   →   →   ↓  
↑   →   →   ↓  
↑   →   →   ↓  
↑   →   →   ⃝ (Goal)
```
- The agent follows the **highest-value states** toward the goal.
- The arrows show the **best possible moves**.

## Limitations of DP in RL
- Requires a known model (transition probabilities and rewards), which is often unavailable in real-world problems.
- Computationally expensive for large state spaces.

## Alternatives to DP
- **Monte Carlo Methods** for model-free episodic learning.
- **Temporal Difference (TD) Learning** (e.g., Q-learning, SARSA) for learning without an explicit model.

## Conclusion
- The **Bellman Expectation Equation** helps evaluate a policy by averaging future rewards.
- The **Bellman Optimality Equation** finds the best policy by choosing the highest-value action.
- **Dynamic Programming (Value Iteration)** repeatedly updates state values until they converge to the optimal values.
- The **optimal policy** guides the agent efficiently to the goal.

Dynamic Programming provides foundational methods for solving MDPs, but its reliance on a known model limits its applicability in large-scale RL problems.
