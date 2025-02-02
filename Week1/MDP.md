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
