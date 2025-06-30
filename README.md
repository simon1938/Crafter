# Deep Reinforcement Learning Agent for Crafter

## 📌 Objective
Develop a **Deep Reinforcement Learning (DRL)** agent capable of playing the **Crafter** game more effectively than a random policy. This project explores challenges such as exploration, long-term credit assignment, and generalization in a procedurally complex environment.

## 🎮 Environment: Crafter
Crafter is a simplified 2D version of Minecraft, with:
- Procedural map generation at each episode
- A complex tech tree
- An ideal framework to test agents’ abilities to learn long-term policies

> 📦 [Crafter GitHub](https://github.com/danijar/crafter)

---

## 🧠 Implementations

### 🔸 Random Agent
- Naive baseline: actions are selected randomly.
- Serves as a minimum performance reference.

---

### 🔹 Deep Q-Network (DQN)
- Approximates Q-values via a neural network.
- Learns from past experiences (Replay Buffer).
- Uses ε-greedy policy for exploration.

---

### 🔹 Double DQN
- Addresses Q-value overestimation in DQN.
- Uses two networks: one for action selection, one for value estimation.

---

### 🔹 Double Dueling DQN + Categorized Loss
- **Dueling architecture**: separates value and advantage streams.
- **Double DQN** for stability.
- **Categorized Loss**: emphasizes critical error zones → more efficient learning.

---

## 📈 Results

| Agent                              | Average Reward / Episode |
|-----------------------------------|---------------------------|
| Random Agent                      | ~1.5                      |
| DQN                               | ~3                        |
| Double DQN                        | ~3.8                      |
| Double Dueling DQN + Cat. Loss    | ~5                        |

> Results averaged over several runs with different seeds.

---

## 🔧 Files

- `train.py`: entry point for training (`python train.py`)
- `agents/`: implementations of various architectures (DQN, Double DQN, etc.)
- `analysis/plot_eval_performance.py`: script to plot performance curves
- `logdir/`: log folders for each agent
- `images/`: result plots

---

## 📝 Installation and Execution

```bash
# Install dependencies
pip install -r requirements.txt

# Train the agent with best hyperparameters
python train.py

# Visualize performance
python analysis/plot_eval_performance.py --logdir logdir/my_agent


## 👥 Authors
- **Simon Illouz--Laurent**
- **Aubin-Bonnefoy**

---

## 💡 Possible Extensions
- Training from **human demonstrations**

---

## 📚 References
- Danijar Hafner, *"Benchmarking the Spectrum of Agent Capabilities"*, 2021.
- H. van Hasselt et al., *"Deep Reinforcement Learning with Double Q-learning"*, 2016.
- Ziyun Wang et al., *"Dueling Network Architectures for Deep RL"*, 2016.
- Marc G. Bellemare et al., *"A Distributional Perspective on Reinforcement Learning"*, 2017.
