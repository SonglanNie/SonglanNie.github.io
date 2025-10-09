<!-- ---
permalink: /research/
title: "Research"
author_profile: true
--- -->

My research focuses on developing and implementing robust **numerical algorithms** for complex mathematical models, primarily in the fields of **Partial Differential Equations (PDEs)** and **Integral Equations**. My goal is to turn challenging mathematical problems into **efficient, reliable software solutions** for scientific and engineering applications.

---

## Current Research

### Integral Equation Methods for Time-Dependent Problems

This is the primary focus of my Ph.D. research. I am working on creating **efficient, high-order accurate solvers** for time-dependent wave propagation and diffusion problems. These methods are crucial for rapidly and accurately simulating physics in complex domains, with applications in areas like geophysics and materials science. I presented a poster on this topic at the Rice RTG Annual Workshop in October 2025.

---

## Past Projects

### Newton's Method for Nonlinear Elasticity: Modeling Materials Under Stress

This project addressed the challenge of numerically solving models for **hyperelasticity** (materials that undergo large, reversible deformations).

* **Problem:** Accurately and efficiently solving the complex, nonlinear governing equations for highly deformable materials.
* **Method:** I derived the **Newton linearization** of the St Venant-Kirchhoff (SVK) hyperelasticity model, investigated globalization strategies (like backtracking and critical point line search), and implemented a **high-order Finite Element Method (FEM)** using the Firedrake library in Python.
* **Impact:** The implementation produced the **optimal rate of convergence**.

### Analytical Lower Bound for Union Probability: Sharpening Statistical Estimates

This was a theoretical project focusing on improving established limits in probability theory.

* **Problem:** Deriving tighter **lower bounds** for the probability of at least $m$-out-of-$n$ events occurring.
* **Method:** I used techniques from **Linear Programming (LP)** to analyze and strengthen existing bounds, including a particular relaxation used in the Yang-Alajaji-Takahara (YAT) bound.
* **Impact:** I derived a **novel analytical lower bound** for the "3-out-of-$n$" events case with three constraints.

### Finite Volume Method for Gradient Flow Problems: Simulating Crystal Growth

This research focused on developing a stable computational scheme for physical systems that naturally lose energy over time (a gradient flow structure).

* **Problem:** Simulating the **coarsening behavior** of a $\text{CuO}_2$ crystal growth model, ensuring the simulation respects the underlying physics (conservation of mass and dissipation of free energy).
* **Method:** I simplified the model to a one-dimensional PDE and developed an **implicit-explicit (IMEX) convex-splitting numerical scheme**.
* **Impact:** The simulations, implemented and visualized using **Julia**, correctly matched the expected coarsening behavior of crystal growth.

### Optimization of SVD for Image Compression

This project focused on the practical application and efficiency of a core linear algebra tool, **Singular Value Decomposition (SVD)**.

* **Problem:** Efficiently generating a sequence of low-rank approximations from an image matrix using SVD to produce compressed images.
* **Method:** I **optimized the code** used in MATLAB.
* **Impact:** This optimization reduced the runtime for generating compressed images from **one minute to five seconds**.