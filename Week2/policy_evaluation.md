# Dynamic Programming: Policy Evaluation

## Overview
Goal of Policy Evaluation: Compute the **state-value function** ( v_{π}(s) ) for a given policy ( π ). It helps assess the expected return when following a fixed policy.

## Bellman Expectation Equation
The state-value function ( v_{π}(s) ) satisfies:
```math
v_{π}(s) = \mathbb{E}_{π} [R_{t+1} + \gamma v_{π}(S_{t+1}) | S_t = s]
```
This equation expresses the value of a state as the sum of the expected immediate reward and the discounted value of the next state.

## Iterative Policy Evaluation
Since solving the Bellman equation directly can be complex, iterative methods approximate ( v_{π}(s) ) using updates:
```math
v_{k+1}(s) = \sum_{a} π(a|s) \sum_{s', r} p(s', r | s, a) \left[ r + \gamma v_k(s') \right]
```

## Convergence and Implementation
- The method converges if the environment is finite and follows specific conditions.
- Uses two arrays: one for current estimates ( v_k(s) ) and another for updated values ( v_{k+1}(s) ).
- An **in-place update** strategy (overwriting old values) speeds up convergence.
- Convergence is determined when the maximum change in value across all states falls below a small threshold ( \theta ).

## Conclusion
Policy Evaluation is a fundamental step in **Dynamic Programming** that helps determine the value of states under a given policy. It serves as a building block for **policy improvement** and **policy iteration** in reinforcement learning.

