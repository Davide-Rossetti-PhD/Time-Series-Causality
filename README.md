# 🧠 Causality-Response-ML  
**Building causation links in stochastic nonlinear systems from data**  
📄 [https://arxiv.org/abs/2509.07701](https://arxiv.org/abs/2509.07701)

---

## 📘 Overview
The work explores how **response theory**—traditionally used in physics to quantify how a system reacts to perturbations—can be combined with **machine learning** to infer **causal relationships** directly from data, without explicit knowledge of the underlying equations of motion.

Two main classes of systems are considered:

1. **Linear stochastic processes** — modeled via Markovian dynamics and estimated using **Lasso-regularized regression**.  
2. **Nonlinear or chaotic systems** — where **data-driven** and **neural** models approximate the system evolution and its causal response.

All experiments are implemented in **Jupyter notebooks** and modular Python code for full reproducibility.

---

## ⚙️ Methods and Models

### 🔹 Linear and Weakly Nonlinear Systems
- Regression of the **Markov operator A** using **Lasso** regularization.  
- Evaluation of the **causal response function** through perturbation analysis:  
  > **R<sub>j→i</sub>(t)** quantifies the average change in variable *i* after a perturbation in *j*.  
- Implementation of the **Fluctuation–Dissipation Relation (FDR)** in the data-driven regime.

### 🔹 Nonlinear and Chaotic Systems
- **Polynomial dictionary regression** (SINDy-style) and **MLP neural networks** to reconstruct the dynamics *ẋ = f(x)*.  
- Perturbations applied to simulated trajectories to compute the causal response function:  
  > **R<sub>j→i</sub>(τ) = δx<sub>i</sub>(t + τ) / δx<sub>j</sub>(t)**  
- Benchmarked on the **Lorenz ’63** system, comparing physical and learned responses.

### 🔹 Reservoir and Nested Neural Models
- **Reservoir Computing** for nonlinear projection and short-term prediction in high-dimensional spaces.  
- **Nested Neural Networks** combining a linear branch (explicit causal path) and a nonlinear MLP branch for interpretability.

---

## 🧩 Repository Structure

| Notebook | Description |
|-----------|--------------|
| `Lasso Linear Regression.ipynb` | Linear stochastic system; estimation of the Markov operator and causal response via Lasso. |
| `Non-Linear Regression.ipynb` | Nonlinear stochastic system modeled with polynomial dictionary regression and L1 sparsity. |
| `Reservoir + Lasso Regularization.ipynb` | Reservoir computing model with Lasso readout for chaotic or non-Markovian responses. |
| `Nest Neural Network.ipynb` | Physics-informed Nested Neural Network combining linear and nonlinear causal effects. |

Each notebook reproduces the numerical experiments and visualizations consistent with the results shown in the paper.

---
