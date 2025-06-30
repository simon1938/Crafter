# Deep Reinforcement Learning Agent for Crafter

## 📌 Objective
Développer un agent d'apprentissage par renforcement profond (DRL) capable de jouer au jeu **Crafter** de manière plus performante qu'une politique aléatoire. Ce projet explore des défis comme l’exploration, l’assignation de crédit à long terme, et la généralisation dans un environnement procédural complexe.

## 🎮 Environnement : Crafter
Crafter est une version simplifiée en 2D de Minecraft, avec :
- Génération procédurale de carte à chaque épisode
- Un arbre technologique complexe
- Un cadre idéal pour tester les capacités des agents à apprendre des politiques de long terme

> 📦 [Crafter GitHub](https://github.com/danijar/crafter)

---

## 🧠 Implémentations

### 🔸 Random Agent
- Baseline naïve : les actions sont choisies aléatoirement.
- Sert de référence de performance minimale.

![Random Agent Performance](images/random_agent_plot.png)

---

### 🔹 Deep Q-Network (DQN)
- Approximation des Q-valeurs via un réseau de neurones.
- Apprentissage à partir d’expériences précédentes (Replay Buffer).
- Politique ε-greedy pour l’exploration.

![DQN Performance](images/dqn_plot.png)

---

### 🔹 Double DQN
- Corrige la surestimation des Q-valeurs dans DQN.
- Utilise deux réseaux : un pour la sélection d’action, un pour l’estimation de valeur.

![Double DQN Performance](images/double_dqn_plot.png)

---

### 🔹 Double Dueling DQN + Categorized Loss
- Architecture **Dueling** : séparation des flux de valeur et d’avantage.
- **Double DQN** pour stabilité.
- **Categorized Loss** : priorité donnée aux erreurs dans les zones critiques → meilleure efficacité d’apprentissage.

![Double Dueling DQN with Categorized Loss Performance](images/double_dueling_categorized_plot.png)

---

## 📈 Résultats

| Agent                              | Reward moyen / épisode |
|-----------------------------------|-------------------------|
| Random Agent                      | ~X.XX                   |
| DQN                               | ~X.XX                   |
| Double DQN                        | ~X.XX                   |
| Double Dueling DQN + Cat. Loss    | **~X.XX**               |

> Les performances sont moyennées sur plusieurs runs avec des seeds différentes.

---

## 🔧 Fichiers

- `train.py` : point d’entrée pour l’entraînement (`python train.py`)
- `agents/` : implémentations des différentes architectures (DQN, Double DQN, etc.)
- `analysis/plot_eval_performance.py` : script pour tracer les courbes de performance
- `logdir/` : dossiers de log pour chaque agent
- `images/` : graphiques des résultats

---

## 📝 Installation et Exécution

```bash
# Installation des dépendances
pip install -r requirements.txt

# Entraîner l'agent avec les meilleurs hyperparamètres
python train.py

# Visualiser les performances
python analysis/plot_eval_performance.py --logdir logdir/my_agent

## 👥 Auteurs

- **Simon Illouz--Laurent**
- **Aubin-Bonnefoy**
---

## 💡 Idées et extensions possibles

- Entraînement à partir de **démonstrations humaines**
---

## 📚 Références

- Danijar Hafner, *"Benchmarking the Spectrum of Agent Capabilities"*, 2021.
- H. van Hasselt et al., *"Deep Reinforcement Learning with Double Q-learning"*, 2016.
- Ziyun Wang et al., *"Dueling Network Architectures for Deep RL"*, 2016.
- Marc G. Bellemare et al., *"A Distributional Perspective on Reinforcement Learning"*, 2017.
