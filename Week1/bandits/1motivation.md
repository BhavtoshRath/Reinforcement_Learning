# Evaluative Feedback in Reinforcement Learning

## Overview  

Reinforcement Learning (RL) differs from supervised learning by using **evaluative feedback** rather than **instructive feedback**.  

- **Evaluative Feedback**: Assesses how good an action was but does not specify the best action.  
- **Instructive Feedback**: Provides the correct action independently of what was chosen (used in supervised learning).  

Evaluative feedback requires **active exploration** to improve decision-making, making it a core feature of RL.  

## k-Armed Bandit Problem  

To study evaluative feedback in a simple setting, we use the **k-armed bandit problem**, where `an agent must choose between multiple actions with unknown rewards.`
This problem introduces fundamental RL methods that extend to more complex environments.  

### Associative Bandit Problem  

An extension of the k-armed bandit problem considers **state-dependent** actions, meaning the best action varies with the situation. This transition leads toward solving **full reinforcement learning problems**.  

🚀 Reinforcement Learning progresses from basic exploration strategies to advanced decision-making in dynamic environments!
