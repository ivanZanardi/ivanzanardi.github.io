---
title: "Physics-Informed Neural Operators"
excerpt: "PINOs applied to nonequilibrium thermochemistry<br/><img src='/images/500x300.png'>"
collection: portfolio
---

[**Physics-informed neural operators (PINOs)**](https://arxiv.org/abs/2111.03794) are a class of machine learning models designed to learn **mappings between function spaces**, unlike conventional neural networks (NNs) which learn mappings between finite-dimensional vector spaces. While classical neural networks approximate input-output relationships at discrete points, **neural operators learn how entire input functions map to output functions**, making them well-suited to modeling physical systems described by differential equations. PINOs go further by **embedding governing physical laws directly into the architecture or loss function**, enforcing residuals from PDEs or ODEs during training. This physics-constrained approach improves generalization, reduces data requirements, and ensures **physically consistent predictions**, even under extrapolation regimes.

---

My research applies PINOs to the **surrogate modeling of thermochemical reactive operators** in nonequilibrium, multicomponent plasma flows. These systems involve **stiff, coupled ODEs** that govern species population dynamics and energy exchanges via collisional-radiative kinetics and chemical nonequilibrium. Conventionally, these source terms are integrated using **implicit ODE solvers** at every grid point — a process that is accurate but **extremely costly** and limits simulation scalability.

Accurately resolving these operators requires solving high-dimensional, nonlinear systems repeatedly, making the approach **computationally prohibitive** in high-fidelity 2D or 3D simulations. PINOs allow us to build **fast surrogates** that approximate these operators with high accuracy while embedding the correct physical behavior. They offer **orders-of-magnitude speedups** and enable tight coupling with unsteady CFD solvers, unlocking new capabilities for real-time simulations.

---

### 🔬 Physics-Embedded Learning

In this context, PINOs are not simply data-driven regressors — they function as **physics-preserving surrogates**. The models are explicitly designed to:
- Enforce **mass and energy conservation laws**
- Maintain **positivity** of species concentrations and temperatures
- Preserve the **equilibrium distribution function** of species' quantum energy levels

This is not achieved by merely augmenting the loss function with physics-based residuals (e.g., from ODE constraints). Instead, the proposed PINO architectures **embed the governing equations directly into the network design itself**, yielding substantial improvements in accuracy while ensuring **physically consistent behavior across regimes** — even under strong extrapolation regimes.

---

## 📚 Selected Publications

**Ivan Zanardi**, A. Padovan, D. J. Bodony, and M. Panesi  
“Petrov-Galerkin model reduction for thermochemical nonequilibrium gas mixtures.” *Journal of Computational Physics*, 2025  
[DOI](https://doi.org/10.1016/j.jcp.2025.113999){: .btn--research}

**Ivan Zanardi**, S. Venturi, and M. Panesi  
“Adaptive physics-informed neural operator for coarse-grained non-equilibrium flows.” *Scientific Reports*, 2023  
[DOI](https://doi.org/10.1038/s41598-023-41039-y){: .btn--research}

---

## 🛠️ Scientific Software

**PyCOMET**  
A modular, TensorFlow-based platform for physics-informed scientific machine learning.  
It enables rapid prototyping of PINO models, with:
- Operator learning modules targeting stiff ODE systems
- Constraints enforcing physics-based invariants
- GPU acceleration for large-scale training and inference

Coupled with in-house Fortran CFD solvers to enable real-time integration of PINOs in full-scale hypersonic simulations.  
[GitHub Repo](https://github.com/ivanZanardi){: .btn--research}

---

## 🎤 Presentations

- *APS DFD Annual Meeting 2024*: Projection-based model reduction for thermochemical nonequilibrium gas mixtures  
- *NeurIPS 2024 ML4PS Workshop*: Scalable nonlinear manifold reduced-order model for dynamical systems
