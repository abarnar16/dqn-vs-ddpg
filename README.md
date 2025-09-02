### A Comparative Study of DQN and DDPG for Continuous Control in Reinforcement Learning

---

### Abstract
[cite_start]This project explores the limitations of Deep Q-Networks (DQN) in handling continuous action spaces and evaluates the effectiveness of Deep Deterministic Policy Gradient (DDPG) as an alternative[cite: 109, 112]. [cite_start]While DQN is effective in discrete environments, its application to continuous control tasks like `Pendulum-v0` requires action space discretization, which can lead to suboptimal performance and a hindered ability to learn fine-grained control[cite: 113, 114]. [cite_start]In contrast, DDPG is designed to operate in continuous domains using a model-free, actor-critic framework for more precise and flexible action selection[cite: 115]. [cite_start]The results show that DDPG learns smoother and more stable policies, outperforming DQN in both learning efficiency and final performance[cite: 116]. [cite_start]This highlights the importance of selecting the right reinforcement learning algorithm based on the structure of the action space[cite: 117].

---

### Introduction to Reinforcement Learning
[cite_start]Reinforcement Learning (RL) is a powerful framework where an agent learns optimal behaviors by interacting with a dynamic environment and receiving rewards as feedback[cite: 119, 120]. [cite_start]Unlike supervised learning, RL is well-suited for sequential decision-making problems[cite: 121]. [cite_start]The agent's goal is to learn a policy that maximizes its cumulative reward over time[cite: 124]. [cite_start]Deep Reinforcement Learning (DRL) uses neural networks to approximate policies and value functions, greatly expanding the application of RL to high-dimensional settings[cite: 125].

---

### Methodology and Implementation
[cite_start]This project compares two major DRL algorithms: DQN and DDPG, on the `Pendulum-v0` environment from OpenAI Gym[cite: 113]. The implementation details are as follows:

* **Deep Q-Network (DQN) Training**:
    * Since `Pendulum-v0` has a continuous action space, the DQN implementation discretizes the torque range into 5 bins.
    * The agent uses an ε-greedy policy to select actions and updates its Q-network using experience replay.
    * The reward logs show a fluctuating but slowly improving learning trajectory due to the limitations of action discretization.

* **Deep Deterministic Policy Gradient (DDPG) Training**:
    * DDPG is an actor-critic method designed for continuous action spaces. The actor network maps states directly to continuous actions, while the critic network estimates Q-values.
    * To encourage exploration, DDPG adds Ornstein-Uhlenbeck noise to the actor's actions.
    * The algorithm utilizes experience replay and soft target network updates to stabilize learning.
    * The reward logs for DDPG show a smoother and more consistent improvement in performance, as the agent learns precise torque values.

---

### Results and Conclusion
[cite_start]The comparative experiment demonstrates that DDPG significantly outperforms DQN in this continuous control task[cite: 116]. The reward curves reveal that while DQN struggles to achieve smooth control due to action discretization, DDPG's ability to directly output continuous actions allows it to learn more effective policies. [cite_start]This project confirms that for continuous control problems in a real-world context, policy-based methods like DDPG are more appropriate and effective than value-based methods like DQN[cite: 117].
