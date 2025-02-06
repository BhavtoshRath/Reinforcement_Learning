# The k-Armed Bandit Problem

## Overview
The **k-armed bandit problem** is a fundamental problem in **Reinforcement Learning (RL)** that illustrates the trade-off between **exploration and exploitation**.
It represents a scenario where an agent must repeatedly choose from **K different actions ("arms")** to maximize its total reward over time.

## Problem Description
- You are repeatedly faced with **k different actions (choices)**.
- Each action provides a **numerical reward** drawn from a stationary probability distribution.
- The goal is to **maximize the expected total reward** over a time period (e.g., 1000 steps).

## Action Values
Each action \( a \) has an **expected reward** (true value):

```math
q^*(a) = \mathbb{E}[R_t | A_t = a]
```

Since the true values \( q^*(a) \) are unknown, we maintain an **estimate**:

```math
Q_t(a) \approx q^*(a)
```

## Exploration vs. Exploitation
- **Exploitation**: Selecting the **greedy action** (highest estimated value) to maximize **immediate** reward.
- **Exploration**: Selecting **non-greedy actions** to gather information, potentially leading to better rewards in the long run.
- **The Dilemma**: Short-term gains (exploitation) vs. long-term improvement (exploration).
- A well-balanced strategy **learns optimal actions over time**.

## Broader Implications
- The **k-armed bandit problem** is a simplified **special case of RL**.
- Reinforcement Learning extends this idea to **sequential decision-making**, where:
  - States influence future rewards.
  - Actions impact both immediate and future rewards.

##  Common Strategies  
1. **ε-Greedy Algorithm**:  
   - With probability **ε**, explore a random arm.  
   - With probability **1 - ε**, exploit the best-known arm.  

2. **UCB (Upper Confidence Bound)**:  
   - Select arms optimistically, balancing exploration and exploitation based on confidence intervals.  

3. **Thompson Sampling**:  
   - Use **Bayesian probability** to sample arms based on their likelihood of being optimal.  

## 🔹 Applications 🚀  
- **Online Advertising** (choosing the best ad to display).  
- **Clinical Trials** (testing multiple treatments to find the best).  
- **Recommendation Systems** (selecting the best content for users).  
