---
title: "Data-Driven Finite Element Method as Foundation Model"
excerpt: "<img src='/images/dd_fem/burgers.png'>"
collection: research
---

Recent advances in machine learning have opened the door to **foundation models** for scientific computing—general-purpose, physics-grounded models designed to scale across problems, geometries, and applications. Drawing inspiration from traditional finite element methods (FEM), we proposed a unifying framework called **Data-Driven FEM (DD-FEM)**, where trainable components are assigned to local subdomains and then composed through interface constraints. This **modular, compositional architecture** enables generalization to arbitrary global configurations, reuse across problems, and consistent physical grounding.

DD-FEM builds on principles long valued in numerical physics—modularity, locality, and generalizability—but reimagines them through the lens of machine learning. Rather than hand-coding the behavior of each element, DD-FEM learns local representations (e.g., within small subdomains) from data and governing physics, while maintaining compatibility and consistency at interfaces. This enables the construction of extensible, reusable surrogates that act as **scientific building blocks**—not just single-use approximators.

---

### 🧱 From Theory to Implementation: DD NM-ROMs

As a concrete realization of the DD-FEM concept, I augmented the [**domain-decomposition nonlinear manifold reduced-order model (DD NM-ROM)**](https://doi.org/10.1016/j.cma.2024.116943). This framework uses shallow, sparse autoencoders trained on subdomains (e.g., 2×2 patches) and composes them into full-domain solvers via algebraic constraints on interface states. It avoids the scalability bottlenecks of monolithic training while retaining physical structure.

- Achieves **700× speedups** with <1% error
- Enables training on small domains and inference on large (e.g., 10×10) patched domains
- Supports composability, parallelism, and cross-problem generalization

---

## 📚 Selected Publications

Y. Choi, S. W. Cheung, Y. Kim, P.‑H. Tsai, A. N. Diaz, **I. Zanardi**, S. W. Chung, D. M. Copeland, C. Kendrick, W. Anderson, T. Iliescu, and M.
Heinkenschloss.  
"Defining Foundation Models for Computational Science: A Call for Clarity and Rigor".  
*arXiv preprint* (May 2025).  
[DOI](https://doi.org/10.48550/arXiv.2505.22904){: .btn--research}

I. Zanardi, A. N. Diaz, S. W. Chung, M. Panesi, and Y. Choi.  
"Scalable nonlinear manifold reduced order model for dynamical systems".  
*arXiv preprint* (Nov. 2024).  
[DOI](https://doi.org/10.48550/arXiv.2412.00507){: .btn--research}
[NeurIPS](https://ml4physicalsciences.github.io/2024/){: .btn--research}

---

## 💻 Scientific Software

**DD-NM-ROM**  
Open-source PyTorch framework for building, training, and composing domain-decomposed nonlinear manifold ROMs.  
[GitHub (LLNL)](https://github.com/LLNL/DD-NM-ROM){: .btn--research}
