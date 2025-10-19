# 🧠 Causality-Response-ML  
**Building causation links in stochastic nonlinear systems from data**  
[https://arxiv.org/abs/2509.07701](https://arxiv.org/abs/2509.07701)

---

## 📘 Overview

This repository implements and extends the methods proposed in  
[*Building causation links in stochastic nonlinear systems from data*](https://arxiv.org/abs/2509.07701)  
by **Davide Rossetti, Sergio Chibbaro, Cyril Furtlehner, Théo Marchetta,** and **Andrei-Tiberiu Pantea** (2025).

The work explores how **response theory**—traditionally used in physics to quantify how a system reacts to perturbations—can be combined with **machine learning** to infer **causal relationships** directly from data, without explicit knowledge of the underlying equations of motion.

Two main classes of systems are considered:
1. **Linear stochastic processes**, modeled via Markovian dynamics and treated with Lasso-regularized regression.
2. **Nonlinear or chaotic systems**, where neural and data-driven models approximate the system evolution and its causal response.

The repository reproduces the experimental results through Jupyter notebooks and modular Python code.

---

## ⚙️ Methods and Models

### 🔹 Linear and Weakly Nonlinear Systems
- Based on regression of the Markov operator \( A \) using **Lasso**.
- Evaluates the causal response function \( R_{j \to i}(t) \) through perturbation analysis.
- Implements the **Fluctuation-Dissipation Relation (FDR)** in the data-driven regime.

### 🔹 Nonlinear and Chaotic Systems
- Uses **polynomial dictionary regression** (SINDy) and **MLP neural networks** to reconstruct dynamics \( \dot{x} = f(x) \).
- Applies perturbations to simulated trajectories to compute causal responses \( R_{j \to i}(\tau) = \frac{\delta x_i(t+\tau)}{\delta x_j(t)} \).
- Benchmarks the models on the **Lorenz ’63** system, comparing physical and learned responses.

### 🔹 Reservoir and Nested Neural Models
- Introduces **Reservoir Computing** for high-dimensional embedding and efficient nonlinear prediction.
- Develops a **Nested Neural Network** architecture (linear + nonlinear branches) to retain physical interpretability and causal traceability.

---

## 🧩 Repository Content

| Notebook | Description |
|-----------|--------------|
| `01_linear_lasso.ipynb` | Linear stochastic case; estimation of the Markov operator and linear causal response via Lasso. |
| `02_nonlinear_regression.ipynb` | Nonlinear stochastic system modeled with dictionary regression and L1 sparsity. |
| `03_reservoir_lasso.ipynb` | Reservoir computing with Lasso readout for chaotic or non-Markovian responses. |
| `04_nested_nn.ipynb` | Physics-informed nested neural architecture combining linear and nonlinear effects. |

Each notebook reproduces numerical experiments and figures consistent with those in the paper.
