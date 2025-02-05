# Markov Decision Processes (MDPs) in Reinforcement Learning  

## Overview  
A **Markov Decision Process (MDP)** is a mathematical framework used to model decision-making in **Reinforcement Learning (RL)**. It provides a structured way to represent environments where outcomes are influenced by both randomness and the agent’s actions.  

## Key Components  
An MDP consists of the following elements:  

- **States (S):** The set of all possible situations the agent can be in.  
- **Actions (A):** The set of all possible actions the agent can take.  
- **Transition Probability (P):** The probability of moving from one state to another given an action.  
- **Reward Function (R):** The immediate feedback the agent receives after taking an action.  
- **Discount Factor (γ):** A factor (0 ≤ γ ≤ 1) that determines the importance of future rewards.  

## Markov Property  
An MDP follows the **Markov Property**, which states that the future state depends **only on the current state and action**, not on past states.  

## Goal in Reinforcement Learning  
The objective in RL is to learn an **optimal policy (π)** that maps states to actions, maximizing the **expected cumulative reward** over time.  

---

# Interview Qs:

- **What is a Markov Decision Process (MDP), and why is it important in reinforcement learning??**
  - `It is a mathematical framework for decision-making in environment with stochastic outcomes.`
  -  Important concepts: `states (S), actions (A), transition probabilities (P), rewards (R), and a discount factor (γ).`
  - MDPs are crucial in RL because they provide a structured way to model an agent's interaction with an environment to learn an optimal policy.

- **What is the Markov Property, and why is it important in MDPs?**
   - `The Markov Property states that the future state of a process depends only on the current state and action, not on the history of past states.` 
   - This assumption simplifies decision-making and enables efficient learning algorithms like Dynamic Programming, Q-Learning, and Policy Gradient Methods in RL.

- **What is the difference between a deterministic and a stochastic policy in MDPs?**
  - A deterministic policy selects the same action a for a given state s every time
  - A stochastic policy defines a probability distribution over actions
  - Stochastic policies are often used in exploration-exploitation trade-offs and in policy gradient methods.

## Markov Decision Process (MDP) in Reinforcement Learning

A Markov Decision Process (MDP) is defined by the tuple:

\[
MDP = (S, A, P, R, \gamma)
\]

where:

- \( S \) : Set of states
- \( A \) : Set of actions
- \( P(s' | s, a) \) : Transition probability from state \( s \) to \( s' \) given action \( a \)
- \( R(s, a) \) : Reward function, which returns a scalar reward for taking action \( a \) in state \( s \)
- \( \gamma \) : Discount factor (\( 0 \leq \gamma \leq 1 \)), determining the importance of future rewards

The objective in RL is to learn a policy \( \pi(a | s) \) that maximizes the **expected cumulative reward**:

```math
V^\pi(s) = \mathbb{E} \left[ \sum_{t=0}^{\infty} \gamma^t R(s_t, a_t) \mid s_0 = s \right]
```

where \( V^\pi(s) \) is the value function under policy \( \pi \), which represents the expected reward starting from state \( s \) and following policy \( \pi \).

