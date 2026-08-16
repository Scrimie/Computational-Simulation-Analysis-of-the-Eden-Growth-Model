# Computational-Simulation-Analysis-of-the-Eden-Growth-Model
# 🦠 Eden Growth Model: Stochastic Surface Simulation

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![NumPy](https://img.shields.io/badge/NumPy-Grid_Computing-green.svg)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Animation-orange.svg)
![Status](https://img.shields.io/badge/Status-Complete-success.svg)

> **🎓 Computational Physics Coursework Project**
> *Queen's University Belfast - MSci Physics*

## 📌 Project Overview
This repository contains the computational simulation and structural analysis of the **Eden Growth Model**. Originally proposed to model the expansion of biological clusters like bacterial colonies, this stochastic lattice model is a fundamental example of non-equilibrium surface growth. The project simulates the cluster formation and quantitatively analyses the resulting fractal boundary properties, specifically tracking surface roughness and dynamical scaling laws.

## 🧮 Methodology & Mathematics
The simulation is built on a 2D grid. Growth occurs stochastically by adding new elements to the perimeter of the existing cluster. At each time step, an empty lattice site adjacent to the cluster (a perimeter site) is selected with uniform probability $P = \frac{1}{N_p}$, where $N_p$ is the total number of currently available perimeter sites.

To characterize the morphology of the cluster's boundary, we compute the **surface roughness** $W(L, t)$, defined as the root-mean-square fluctuation of the cluster height:

$$W(L, t) = \sqrt{\frac{1}{L} \sum_{i=1}^L \left( h_i(t) - \bar{h}(t) \right)^2}$$

Where:
* $L$ is the system size (width of the lattice).
* $h_i(t)$ is the height of the interface at position $i$ and time $t$.
* $\bar{h}(t)$ is the mean interface height at time $t$.

The evolution of the surface is analysed using the **Family-Vicsek scaling relation** to verify its universality class:

$$W(L, t) \sim L^\alpha f\left(\frac{t}{L^z}\right)$$

Where $\alpha \approx 0.5$ is the roughness exponent and $z \approx 1.5$ is the dynamic scaling exponent for 1+1 dimensional growth.

## 📊 Key Results & Visualisations
*(Add your generated cluster images and scaling plots here!)*

* **Figure 1: Stochastic Cluster Formation (t = 50,000 steps)**
  `![[Insert GIF or Image of the Eden Cluster here]]`
  *Description: A 2D simulation of Eden growth starting from a single central seed, demonstrating the compact interior and actively roughening surface characteristic of the model.*

* **Figure 2: Surface Roughness Scaling over Time**
  `![[Insert Log-Log Plot of W(L,t) vs t here]]`
  *Description: A log-log plot verifying the dynamical scaling of the surface roughness, plateauing at a saturation width dependent on the lattice boundaries.*

## 📂 Repository Structure
```text
├── data/                   # Exported cluster coordinates and roughness metrics (CSV)
├── scripts/                # Python scripts for simulation and analysis
│   ├── eden_simulation.py  # Main lattice growth algorithm
│   ├── scaling_analysis.py # Calculation of W(L,t) and scaling exponents
├── plots/                  # Visualisations and generated GIFs of the growth
├── requirements.txt        # Python dependencies (NumPy, Matplotlib)
└── README.md
