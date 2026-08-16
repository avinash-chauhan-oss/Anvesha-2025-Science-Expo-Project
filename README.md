# Classical-Quantum Hybrid Classifier

[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![PennyLane](https://img.shields.io/badge/Framework-PennyLane-blueviolet.svg)](https://pennylane.ai/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Anvesha 2025](https://img.shields.io/badge/Anvesha-2025_Science_Expo-orange.svg)]()

> **Anvesha 2025 Science Expo** | IISER Thiruvananthapuram
> **Authors:** Debashis Saikia & Avinash Chauhan

A novel hybrid machine learning protocol that combines classical dimensionality reduction with quantum state-overlap measurement for non-linear classification tasks.

---

## Overview

Classical machine learning struggles at the quantum scale. This project proposes and implements a **Classical-Quantum Hybrid Classifier** that fuses the best of both paradigms:

1. **Classical pre-processing** extracts structure from high-dimensional data using PCA and K-Means clustering.
2. **Quantum measurement** uses a parameterized quantum circuit to measure fidelity (state overlap) between an input and reference centroids.

The protocol replaces the classical distance metric with a **quantum fidelity score** derived from a UUt circuit architecture, enabling a geometrically richer similarity measure.

---

## Methodology

### Step 1 — Classical Preprocessing
- **PCA** reduces input data to a lower-dimensional representation.
- **K-Means Clustering** identifies representative centroids for each class label.

### Step 2 — Quantum State Encoding
Each data point and its corresponding class centroid are encoded as normalized quantum states using **amplitude encoding**.

### Step 3 — UUt Circuit & Fidelity Measurement
A parameterized quantum circuit `U` encodes the data state. The circuit then applies `U†` (conjugate transpose) to the reference state. The probability of measuring the `|0⟩` state corresponds directly to the **fidelity** (state overlap):

$$F(|\psi\rangle, |\phi\rangle) = |\langle \phi | \psi \rangle|^2$$

High fidelity → same class. Low fidelity → different class.

### Step 4 — Classification
The data point is assigned to the class whose centroid yields the highest quantum fidelity score.

---

## Tech Stack

| Component | Tool |
|-----------|------|
| Quantum Circuits | [PennyLane](https://pennylane.ai/) |
| Classical ML | [Scikit-learn](https://scikit-learn.org/) |
| Numerical Computing | [NumPy](https://numpy.org/) |
| Visualization | [Matplotlib](https://matplotlib.org/) |

---

## Results

The hybrid classifier demonstrates competitive accuracy against purely classical baselines on benchmark datasets, with the quantum fidelity metric providing improved separation in non-linearly separable feature spaces.

---

## Repository Structure

```
Anvesha-2025-Science-Expo-Project/
├── notebooks/          # Jupyter notebooks with full implementation
├── src/                # Core circuit and classifier modules
├── data/               # Benchmark datasets
└── README.md
```

---

## Authors

- **Avinash Chauhan** — BS-MS Mathematics, IISER Thiruvananthapuram
- **Debashis Saikia** — IISER Thiruvananthapuram

---

*Presented at Anvesha 2025, the annual Science Expo of IISER Thiruvananthapuram.*
