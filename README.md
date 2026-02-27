# Taxiv3.SARSA
Taxi-v3 Reinforcement Learning with SARSA

This repository contains an implementation of the SARSA (State-Action-Reward-State-Action) algorithm to solve the classic Taxi-v3 environment from OpenAI Gymnasium.

The Taxi-v3 environment involves a 5×5 grid world. The goal is to navigate a taxi to a passenger's location, pick them up, drive to the destination, and drop them off. The agent must manage 500 discrete states and 6 possible actions while avoiding penalties for illegal moves.

Features

Tabular SARSA Implementation: An "on-policy" reinforcement learning algorithm that updates the Q-values based on the action actually taken by the agent.

ϵ-Greedy Strategy: Balanced exploration and exploitation with a decaying epsilon to ensure the agent learns an optimal path.

Custom Reward Shaping: Slight modification to step rewards to encourage faster convergence.

Dual Visualization: Includes both matplotlib for Jupyter Notebook rendering and human mode for real-time visualization of the trained policy.


Algorithm Details
The SARSA update rule used in this implementation is:

Q(s,a)←Q(s,a)+α[r+γQ(s′,a′)−Q(s,a)]

Hyperparameters

Alpha (α): 0.1 (Learning Rate)

Gamma (γ): 0.99 (Discount Factor)

Epsilon (ϵ): Starts at 1.0 (Exploration) with a decay of 0.9995.

Episodes: 5,000

Usage

Training: The agent initializes a 500×6 Q-table and trains for 5,000 episodes.

Static View: A matplotlib plot shows the initial environment state.

Simulation: The code runs a "human-mode" visualization where you can watch the taxi navigate the grid in real-time.


After 5,000 episodes, the agent successfully identifies the color-coded pickup and drop-off points, learning to avoid hitting walls and minimizing the steps taken per trip.
