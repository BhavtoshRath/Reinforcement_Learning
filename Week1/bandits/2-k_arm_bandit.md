# The k-Armed Bandit Problem

## Overview
The **k-armed bandit problem** is a fundamental problem in **Reinforcement Learning (RL)** that illustrates the trade-off between **exploration and exploitation**.
It represents a scenario where an agent must repeatedly choose from **K different actions ("arms")** to maximize its total reward over time.

## Problem Description
- You are repeatedly faced with **k different actions**.
- Each action provides a **numerical reward** drawn from a stationary probability distribution (stochastic policy).
- The goal is to **maximize the expected total reward** over a time period (e.g., 1000 steps).

---
## Stationary vs Non-stationary environments:

```Stationary```

Reward distribution for each action (or "arm") ```does not change over time```.  Example: Consider a multi-armed bandit problem 
where each slot machine (arm) has a fixed probability of payout. Once the agent has enough data, it can identify the 
optimal arm and continue pulling it.

```Non-Stationary```

Reward distribution for each arm ```changes over time```. Example: In online advertising, user behavior may change over time due to shifting preferences, seasonality, or external events 
(e.g., holidays). A banner ad that performed well last week may perform poorly this week as user interests shift.


---

## Action Values (Q(a))
Each action \( a \) has an **expected reward** (true value):

```math
q^*(a) = \mathbb{E}[R_t | A_t = a]
```

Since the true values \( q^*(a) \) are unknown, we maintain an **estimate**:

```math
Q_t(a) \approx q^*(a)
```
---

### Key Differences: Policy Gradient vs. Action Value Estimation (approaches for solving decision-making problems)

| **Aspect**              | **Action Value Estimation**  | **Policy Gradient**  |
|------------------------|--------------------------------|------------------------|
| **What is Learned?**  | Estimates the expected reward for each action \( Q(a) \). | Learns a direct policy \( \pi(a) \) (probability of selecting each action). |
| **Decision-Making** | Chooses actions based on estimated values (e.g., greedy, ε-greedy, UCB, etc.). | Chooses actions using a **probabilistic policy** (e.g., softmax). |
| **Update Mechanism** | Updates value estimates based on observed rewards. | Updates action preferences using a gradient of expected reward. |
| **Exploration Method** | Uses **explicit exploration** (ε-Greedy, UCB, Thompson Sampling). | Uses **inherent exploration** due to stochastic policy updates. |
| **Best Suited For** | **Stationary environments** (fixed reward distributions). | **Non-stationary environments** where rewards change dynamically. |
| **Used In** | Q-learning, SARSA, multi-armed bandits (ε-Greedy, UCB, etc.). | Reinforcement Learning (REINFORCE, PPO, A3C, etc.). |

---

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

---

### K-Armed Bandit Strategies

| Strategy               | Description                                                                                                                                                                    | Pros                                                                                                                                 | Cons                                              | Example Use Case |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------|------------------|
| **ε-Greedy**          | Chooses the best-known action with probability **1 - ε** and explores randomly with probability **ε**.                                                                         | Simple, effective, tunable. <br/>Works well for stationary environments (where rewards do not change over time).                     | can suffer from suboptimal exploration due to its random nature.  | Online ad selection (choosing the best ad while still testing new ones). |
| **Optimistic Initial Values** | Initializes action-value estimates optimistically to ```encourage early exploration```.                                                                                        | Encourages exploration without explicit randomness.<br/> Good for ```stationary environment (i.e. reward doesnt change over time)``` | Can mislead in non-stationary environments.       | A/B testing for new product features with limited data. |
| **Upper Confidence Bound (UCB)** | Selects the arm with highest UCB. It actively chooses arms that have high uncertainty (hence encouraging exploration) but also rewards high-performing arms (exploitation). | Usually performs well in the long run as it strategically balances exploration and exploitation based on uncertainty.                | More computationally expensive.                   | Recommender systems (e.g., choosing movies to suggest on a streaming platform). |
| **Thompson Sampling** | Uses Bayesian inference to model reward distributions and selects actions ```probabilistically```.                                                                             | Efficient exploration and strong empirical performance.                                                                              | Requires prior knowledge of reward distributions. | Medical trials (selecting the most effective treatment dynamically). |
| **Gradient Bandits** | Uses softmax selection with preference scores and updates them using gradient ascent.                                                                                          | Adaptive, works well with non-stationary rewards.                                                                                    | More complex and requires careful tuning.         | Dynamic pricing (adjusting product prices based on demand). |
| **Exp3 (Exponential-weight Algorithm)** | Assigns and updates weights for actions based on observed rewards using an exponential weighting scheme.                                                                       | Works well in adversarial environments.                                                                                              | Not optimal for stationary settings.              | Cybersecurity (detecting and adapting to evolving attack patterns). |


---

## 🔹 Applications 🚀  
- **Online Advertising** (choosing the best ad to display).  
- **Clinical Trials** (testing multiple treatments to find the best).  
- **Recommendation Systems** (selecting the best content for users).  

---

## Contextual Bandits vs. Multi-Armed Bandits: Key Differences

| **Aspect**               | **Multi-Armed Bandits (MAB)** 🎰 | **Contextual Bandits** 🎯 |
|--------------------------|--------------------------------|--------------------------|
| **Definition**           | ```Learns which action``` (arm) has the highest expected reward. | ```Learns which action``` is best depending on **contextual information** (features). |
| **Reward Estimation**    | Estimates **fixed reward distributions** for each action. | Estimates **context-dependent reward distributions** for each action. |
| **Exploration Methods**  | Uses ε-Greedy, UCB, or Thompson Sampling to explore. | Uses **LinUCB**, **Neural Bandits**, or **Contextual Thompson Sampling**. |
| **Use Case Examples**    | A/B testing, slot machines, clinical trials. | Personalized recommendations, online advertising, medical treatments. |
| **Learning Complexity**  | ✅ Simpler (only needs action-reward pairs). | ⚠️ More complex (requires learning a reward model per context). |
| **State Transitions**    | ❌ No state transitions (each action is independent). | ❌ No state transitions, but considers context. |
| **Comparison to RL**     | A **simplified RL model**—no states, only actions & rewards. | **Bridges the gap** between bandits and full RL (context-dependent learning). |

