# Evaluating the Faithfulness of Saliency-Based Explanations in Reinforcement Learning

This repository contains the implementation, experimental pipeline, and results for the research project:

> **Evaluating the Faithfulness of Saliency-Based Explanations in Reinforcement Learning: Do They Reflect What Actually Drives an Agent's Decision-Making?**

The project investigates whether gradient-based saliency maps genuinely reflect the causal factors underlying a Deep Q-Network (DQN) agent's decisions or merely provide plausible-looking explanations.

---

## Abstract

Gradient-based saliency maps are among the most widely used explanation methods for deep neural networks, including reinforcement learning agents. However, an important open question is whether these visualizations are faithful to the actual factors driving an agent's behavior.

This project evaluates explanation faithfulness through a causal perturbation framework. A DQN agent is trained to solve a custom GridWorld navigation task, after which obstacles identified as salient are systematically removed from the observation to determine whether the agent's decision changes.

Unlike purely qualitative evaluations, this work measures faithfulness quantitatively using perturbation experiments, matched control conditions, multi-seed replication, and rank-correlation analysis.

---

## Main Contributions

- Development of a custom GridWorld reinforcement learning environment.
- Training of Deep Q-Network (DQN) navigation agents using Stable-Baselines3.
- Generation of gradient-based saliency maps.
- Causal perturbation framework for evaluating explanation faithfulness.
- Comparison against least-salient and random-obstacle control conditions.
- Multi-seed evaluation across independently trained agents.
- Statistical analysis of explanation faithfulness using Spearman rank correlation.

---

## Experimental Pipeline

Observation

↓

DQN Agent

↓

Gradient-based Saliency Map

↓

Obstacle Ranking

↓

Targeted Perturbation

↓

Action Re-evaluation

↓

Statistical Analysis

---

## Results

The study found that gradient-based saliency maps contain a genuine but quantitatively weak signal about causal importance.

Main findings include:

- Positive Spearman correlation between saliency magnitude and causal effect.
- Top-salient perturbations changed agent actions significantly more often than both control conditions.
- Results reproduced across independently trained agents.
- Small pilot studies may substantially underestimate explanation faithfulness because of insufficient statistical power.

---
## Reproducibility

Exact numerical values may vary slightly between runs because Deep Q-Network training and GridWorld initialization are stochastic processes. However, the qualitative conclusions reported in this repository remained stable across repeated experiments.

---


## Repository Structure

```text
src/                Source code
models/             Trained DQN models
results/            Experimental results and figures
paper/              Research paper (PDF)
assets/             Images and diagrams
```

---

## Technologies

- Python 3
- PyTorch
- Stable-Baselines3
- Gymnasium
- NumPy
- Matplotlib

---

## Installation

```bash
git@github.com:notaylinn/RL--Saliency--Faithfulness.git

cd faithfulness-rl-saliency

pip install -r requirements.txt
```

---

## Running the Project

Experiments can be reproduced by executing the notebook:

notebook/XAI-3.ipynb

---

## Paper

The complete research paper is available here:

- [Research Paper](paper/Evaluating%20Faithfulness%20of%20Saliency%20Explanations%20in%20RL.pdf)
---

## Citation

If you find this repository useful, please cite:

---

## License

MIT License
