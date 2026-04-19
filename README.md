# The Bias-Variance Trade-off in Predictive Modeling

Visual demonstration of the bias-variance decomposition of mean squared error through polynomial regression. Illustrates the fundamental trade-off between model underfitting and overfitting using Monte Carlo simulations.

---

## Overview

This project demonstrates the **bias-variance trade-off** — a fundamental principle in predictive modeling — through a controlled simulation.

By fitting polynomial models of varying complexity (degree 1, 4, and 15) to multiple independent samples from the same data-generating process, we visualize:

- **Squared Bias** (red): Systematic deviation from the true function
- **Estimation Variance** (cyan): Instability across simulations
- **Process Variance** (irreducible noise in the data)

The analysis reveals why neither pure simplicity (high bias) nor complexity (high variance) minimizes prediction error — the optimum lies in balance.

---

## Theory

### MSEP Decomposition

The expected squared prediction error decomposes as:

```
E[(Y − A(Yₙ))²] = (E[Y] − E[A(Yₙ)])² + Var(A(Yₙ)) + Var(Y)
                   └────────────────┘    └──────────┘   └────┘
                      Squared Bias      Est. Variance   Process
                                                        Variance
```

where:
- **Squared Bias²** — how far the average prediction is from the true function
- **Estimation Variance** — how much predictions vary across different training datasets
- **Process Variance** — irreducible noise (σ² of the data-generating process)

---

## Results

### Degree 1 Polynomial (High Bias, Low Variance)

| Metric | Value | Interpretation |
|---|---|---|
| **Bias** | High | Systematically underestimates curved relationship |
| **Variance** | Low | Stable across simulations |
| **Overall** | Underfitting | Simple model fails to capture true risk profile |

The model is wrong but consistent — useful only if true function is actually linear.

### Degree 4 Polynomial (Balanced)

| Metric | Value | Interpretation |
|---|---|---|
| **Bias** | Low | Average prediction tracks true function |
| **Variance** | Low | Predictions stable across samples |
| **Overall** | **Optimal** | Best generalization to unseen data |

The Goldilocks zone — neither too simple nor too complex.

### Degree 15 Polynomial (Low Bias, High Variance)

| Metric | Value | Interpretation |
|---|---|---|
| **Bias** | Low | Perfectly fits each training set |
| **Variance** | Very High | Fits noise; predictions diverge across samples |
| **Overall** | Overfitting | Excellent in-sample, poor out-of-sample |

At the boundaries, individual fits scatter drastically — the model memorizes training noise instead of learning the underlying pattern.

---
