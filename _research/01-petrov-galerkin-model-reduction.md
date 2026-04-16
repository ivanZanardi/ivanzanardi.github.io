---
title: "Petrov-Galerkin Model Reduction"
excerpt: "<img src='/images/rom/2d_plasma.jpg'>"
collection: research
---

[**Projection-based reduced-order models (ROMs)**](https://doi.org/10.1137/130932715) are a powerful tool for accelerating simulations of high-dimensional dynamical systems by projecting the governing equations onto a carefully chosen low-dimensional subspace. This reduces computational cost significantly while retaining the system's essential dynamics.

Traditional ROMs typically rely on **orthogonal (Galerkin) projection** using energy-optimal bases such as Proper Orthogonal Decomposition (POD). However, these approaches often break down in highly non-normal systems, where low-energy directions can strongly influence the dynamics—leading to instability and poor accuracy. In contrast, **oblique (Petrov–Galerkin) projection** uses distinct trial and test spaces, allowing for greater flexibility. This enables the ROM to capture both the directions of high variance in the state and those to which the system’s outputs are most sensitive—leading to more stable and accurate models.

---

### 🔬 Application to Nonequilibrium Plasmas

Simulating **nonequilibrium thermochemical plasma flows** poses significant challenges due to the **high dimensionality** introduced by detailed, state-specific kinetics. While full [state-to-state (StS)](https://doi.org/10.1016/S0301-0104(99)00213-X) models provide the highest physical accuracy, they are computationally intractable when embedded directly into multidimensional CFD solvers.

To address this, I developed a reduced-order modeling strategy based on an extension of the [**CoBRAS**](https://doi.org/10.1137/130932715) framework — a method that constructs **oblique projection operators** for nonlinear systems by balancing statistical information from both forward and adjoint trajectories.

In my work, CoBRAS is adapted specifically for StS nonequilibrium plasmas by first building and training the ROM in zero-dimensional settings, then integrating it into a finite-volume CFD solver for realistic multidimensional simulations. This approach yields physically consistent, robust, and efficient surrogates for use in high-speed plasma flow modeling.

---

## 📚 Selected Publications

**I. Zanardi**, A. Padovan, D. J. Bodony, and M. Panesi.  
"Petrov‑Galerkin model reduction for thermochemical nonequilibrium gas mixtures".  
In: *Journal of Computational Physics 533* (Apr. 2025).  
[DOI](https://doi.org/10.1016/j.jcp.2025.113999){: .btn--research}
[GitHub](https://github.com/ivanZanardi/ronek){: .btn--research}

**I. Zanardi**, A. Meini, A. Padovan, D. J. Bodony, and M. Panesi.  
"Petrov‑Galerkin model reduction for collisional‑radiative argon plasma".  
In: *Physics of Plasmas 33* (Jan. 2026).  
[DOI](https://doi.org/10.1063/5.0306085){: .btn--research}
[GitHub](https://github.com/ivanZanardi/romar){: .btn--research}
