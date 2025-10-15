---
permalink: /research/
title: "Research"
author_profile: true
---

My research focuses on developing and implementing robust **numerical algorithms** for complex mathematical models, primarily in the fields of **Partial Differential Equations (PDEs)** and **Integral Equations**. My goal is to turn challenging mathematical problems into **efficient, reliable software solutions** for scientific and engineering applications.

---

## Current Research

### Integral Equation Methods for Time-Dependent Problems

This is the primary focus of my Ph.D. research. I am working on creating **fast, high-order accurate integral equation solvers** for time-dependent PDEs. These methods are crucial for rapidly and accurately simulating physics in complex domains, with applications in areas like geophysics and materials science. I presented a poster on this topic at the Rice RTG Annual Workshop in October 2025.

---

## Past Projects

### Newton’s Method Beyond the Local Regime

Nonlinear partial differential equations arise frequently in applied mathematics — but unlike linear systems, their solutions can’t be obtained in a single step. The **Newton–Kantorovich method** provides a powerful iterative framework: given an operator equation  

$$
F(u) = 0,
$$

it linearizes $F$ around a current approximation $u_k$ and solves a sequence of linear problems  

$$
DF(u_k)\,\delta u_k = -F(u_k), \quad u_{k+1} = u_k + \delta u_k.
$$

Under favorable conditions, this process converges **quadratically** — errors shrink rapidly once we are close to the solution.

The challenge is that this convergence is **local**. If the initial guess is too far, the method may diverge or oscillate. In practice, this sensitivity limits Newton’s effectiveness on nonlinear PDEs, where good initial guesses are rarely available.

To address this, I explored **globalization strategies** that preserve Newton’s efficiency while improving its robustness:

- **Backtracking line search**, which adaptively scales each update to ensure a decrease in the residual norm.  
- **Load continuation**, which introduces the nonlinearity gradually by solving a sequence of easier problems leading to the full system.

I implemented and compared these strategies in a **finite element setting** using the **Firedrake** framework. The results show that with proper globalization, Newton’s method becomes a **reliable general-purpose solver** for nonlinear PDEs, maintaining fast convergence without relying on a perfect starting point.

I also presented related work on *Newton’s method in infinite dimensions and Galerkin approximations* ([slides]({{ "/files/Newton_s_method_in_infinite_dimensions_and_Galerkin_approximations.pdf" | relative_url }})), introducing Newton's method for solving nonlinear PDEs from a functional-analytic perspective.

Nie, S., Aznaran, F. R. A., & Parker, C. (2023). *Nonlinear elasticity and Newton’s method in infinite dimensions.* Oxford Mathematical Institute. [PDF]({{ "/files/Newton_s_method_for_nonlinear_PDEs_report.pdf" | relative_url }})

### Analytical Lower Bound for Probability of m-out-of-n events

Many reliability and stochastic problems reduce to estimating $$P(\mu \ge m),$$ where $\mu$ denotes the **number of events that occur** among $n$ possible ones. Exact computation is rarely tractable since the number of event intersections grows exponentially with $n$. This motivates analytical **lower bounds** that can be computed from partial probabilistic information.

Building on work by Prékopa, Gao, and others, we extend known bounds for $m=1$ to $m=2$ and $m=3$ using **probabilistic inequalities** and **linear programming (LP) formulations**. Our analysis incorporates **disaggregated partial information**—probabilities of specific events and their intersections—yielding tighter bounds than classical aggregated approaches.

For $m=2$, we show that bounds derived from **Cauchy–Schwarz inequalities** and **LP formulations** coincide. For $m=3$, we construct a new **LP-based analytical bound** that systematically improves existing results. These formulations provide a unified, computationally efficient way to obtain **explicit analytical bounds** for general *m*-out-of-*n* probability problems. 

Nie, S., & Yang, J. (2023). *Analytical lower bounds for m-out-of-n probabilities.* University of Oxford, MMath Thesis, Mathematics and Statistics, Trinity Term 2023.
[PDF]({{ "/files/Analytical_Lower_Bounds_for_Union_Probability_Songlan_Nie.pdf" | relative_url }})

### Finite Volume Method for Gradient Flow Problems: Simulating Crystal Growth

The growth of crystalline surfaces, such as CuO₂, can be modeled as an **energy minimization problem**. While the physics is well-understood, numerical simulation is challenging due to **stiff dynamics** and the need to preserve **energy dissipation**.

We implemented a **semi-implicit 1D scheme** with **convex splitting of the potential**, which preserves two key properties at the discrete level:

- **Mass conservation** – the total mass of the crystal remains constant.
- **Energy dissipation** – the discrete free energy decreases over time.

Simulations show the **coarsening of the surface**, producing piecewise linear facets with sharp transitions. This approach provides an **efficient, unconditionally energy-stable scheme** suitable for stiff gradient-flow problems in materials science.

Nie, S., & Bailo, R. (2023). *Finite volume methods for gradient-flow crystal growth problems.* Oxford Mathematical Institute. [PDF]({{ "/files/Finite_volume_methods_for_gradient_flow_crystal_growth_problems.pdf" | relative_url }})

### Image Compression using Singular Value Decomposition (SVD)

As a short MATLAB exercise, this project illustrates how **Singular Value Decomposition (SVD)** can be used for basic image compression. Viewing an image as a matrix, SVD allows simple **low-rank approximations** that capture the main visual structure while reducing data size.

The code:
- Converts images to grayscale and applies SVD.
- Reconstructs the image using different ranks to compare compression quality.
- Improves runtime from about one minute to a few seconds.

The project also includes a brief look at how the **singular values decay** and how this affects image reconstruction. 

Code and short report: [GitHub](https://github.com/SonglanNie/SVD_Image_Compression) · [PDF]({{ "/files/Image_Compression_Project.pdf" | relative_url }})

