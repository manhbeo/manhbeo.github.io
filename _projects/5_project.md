---
layout: page
title: "PINNs in PyTorch"
description: "PINN implementations for Burgers, KdV, Navier–Stokes, Schrödinger and related PDEs."
date: 2023-03-05
image: /assets/img/projects/pinns.png
tags: ["scientific machine learning", "PINNs", "PDEs", "PyTorch"]
links:
  github: https://github.com/manhbeo/Physics-Inform-Neural-Network
---

This project collects **PyTorch implementations of physics-informed neural networks (PINNs)** for a
range of canonical PDEs, following the Physics-Informed Deep Learning framework.

---

## 🔍 Summary

PINNs approximate the solution of a PDE by training a neural network \(u_\theta(x, t)\) that:

- Fits observed data points.
- Minimizes the **PDE residual** and boundary / initial condition violations via automatic
  differentiation.

This allows solving both **forward** (solve PDE) and **inverse** (identify parameters) problems in a
unified way.

---

## 🧪 PDEs covered

Experiments in the repo include:

- **Burgers’ equation** – nonlinear advection-diffusion.
- **KdV equation** – nonlinear wave propagation.
- **Navier–Stokes** – incompressible fluid dynamics.
- **Schrödinger equation** – quantum wave dynamics.

For each equation, the repo provides:

- Network architectures for \(u_\theta\).
- Physics-informed loss functions combining data and residuals.
- Training scripts / notebooks that reproduce classical PINN demos.

---

## 📂 GitHub repository

- Code & experiments:  
  **[github.com/manhbeo/Physics-Inform-Neural-Network](https://github.com/manhbeo/Physics-Inform-Neural-Network)**
