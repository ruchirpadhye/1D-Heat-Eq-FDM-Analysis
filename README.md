# 1D-Heat-Eq-FDM-Analysis
Solving 1D Steady State Equation using FDM

# 1D Steady-State Heat Conduction Simulator 

A Python-based numerical solver that uses the Finite Difference Method (FDM) to analyze steady-state heat transfer across multi-layer composite walls (such as rocket engine casings, insulated pipes, or building walls).
All computations and visualizations are contained within a single interactive Jupyter Notebook: `FDM Analysis.ipynb.`

## Features

* **Dynamic Multi-Layer Support**: Automatically handles any number of composite materials.
* **Algorithmic Interface Handling**: Calculates the exact junction temperatures between different materials using Heat Flux Continuity principles.
* **Global Matrix Assembly**: Constructs a unified Tridiagonal Matrix ($A \cdot \mathbf{T} = \mathbf{b}$) to solve for all internal and interface nodes simultaneously.
* **Automated Visualization**: Uses matplotlib to generate a color-coded, scaled 1D plot of the temperature gradient, with highlighted boundary and interface pivots.

# The Physics

The tool is built on Fourier's Law of Heat Conduction. For a 1D steady-state system without internal heat generation:

$$ \frac{d}{dx} \left( k \frac{dT}{dx} \right) = 0 $$

The continuous differential equation is discretized using the Central Difference Approximation.
* **Internal Nodes**: Follow the standard $T_{i-1} - 2T_i + T_{i+1} = 0$ relationship.
* **Interface Nodes**: Handled dynamically via thermal conductance ($C = \frac{k}{\Delta x}$) to ensure the heat leaving Layer $A$ equals the heat entering Layer $B$: $C_A T_{i-1} - (C_A + C_B) T_i + C_B T_{i+1} = 0$.

# Methodology

To run this notebook, you will need Python 3.x and the following libraries:
* **`numpy`** (For array manipulation)
* **`scipy`** (For optimized linear algebra matrix solving)
* **`matplotlib`** (For plotting the temperature gradient)


# Contributing

Feel free to fork this project, submit pull requests, or suggest new features (e.g., adding cylindrical/spherical coordinates, or convective boundary conditions). 


---
*Developed as part of an autonomous systems and computational engineering portfolio.*
