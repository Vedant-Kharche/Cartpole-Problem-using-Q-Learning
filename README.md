# Cartpole-Problem-using-Q-Learning Overview 

This project implements Q-learning to solve the CartPole-v1 control problem from OpenAI Gymnasium. The goal is to balance a pole on a moving cart by applying forces to the left or right. The state space is continuous, so we discretize it using bins to make it suitable for tabular Q-learning. 

## Key features:

State Discretization: The 4-dimensional continuous state is binned into discrete categories.
Epsilon-Greedy Policy: Balances exploration and exploitation.
Q-Table Update: Employs the Q-learning update rule to learn optimal policies.
Training & Testing: The agent is trained over 1000 episodes and tested over 100 episodes.
Visualizations include:
Training Reward Curve – shows learning progress.
Test Performance Bar Chart – shows consistency of the trained agent.

## Q-Learning Parameters

| Parameter            | Value           |
|----------------------|-----------------|
| State Bins           | (6, 12, 6, 12)  |
| Learning Rate (α)    | 0.001           |
| Discount Factor (γ)  | 0.99            |
| Initial Epsilon      | 1.0             |
| Epsilon Decay Rate   | 0.995           |
| Minimum Epsilon      | 0.01            |
| Training Episodes    | 1000            |
| Test Episodes        | 100             |

---

## Results and Validation

### Training Results

During the training phase, the agent showed **steady improvement** in balancing the pole over **1000 episodes**. Initially, the agent had minimal understanding of the task, achieving low rewards (e.g., reward of **20** around Episode 100). As training progressed, the agent learned better policies, especially after **Episode 600**, where rewards began rising more consistently.

By the **final episode**, the agent achieved a reward of **108**, a significant improvement compared to early training. The **training reward curve** reflects this upward trend, despite occasional **fluctuations** around Episodes 400–500, which are expected due to the **exploration-exploitation trade-off** in Q-learning. These fluctuations indicate the agent was still exploring less-optimal actions in search of a more effective long-term policy.

![cartpoole_training](https://github.com/user-attachments/assets/48b870a4-0197-4053-88ee-6d365994dfda)


---

### Evaluation Results

After training, the agent was **evaluated over 100 episodes** without exploration (pure exploitation using the learned Q-table). The agent's **average reward during evaluation** was **73.71**, indicating it learned to balance the pole for a substantial number of timesteps in most episodes.

While some evaluation episodes demonstrated the agent’s ability to **sustain balance for extended periods**, occasional **failures to recover from unstable states** resulted in lower rewards in certain episodes. The **bar chart below** displays the variation in episode rewards, reflecting the learned policy’s **strength and occasional limitations**.
![cartpoole_performance](https://github.com/user-attachments/assets/d03a101d-408b-4514-8e12-0f6dd1f8b64b)

---

### Reward Trends

The **moving average** of training rewards highlights the **agent’s learning trajectory**, showing a clear **upward trend** over time. The **evaluation results** reinforce the **robustness** of the learned policy, with consistently higher rewards compared to early training performance.

Overall, these results validate that **Q-learning with discretized state space** can effectively solve the CartPole-v1 problem, enabling the agent to develop a policy that balances the pole for extended durations.
