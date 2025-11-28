---
layout: project
title: "Physics-Informed Neural Networks in PyTorch"
description: "PyTorch implementations of physics-informed neural networks for classic PDEs such as Burgers, KdV, Navier–Stokes, and Schrödinger equations."
date: 2023-03-05
image: /assets/img/projects/pinns.png
tags: ["scientific machine learning", "PINNs", "PDEs", "PyTorch"]
links:
  github: https://github.com/manhbeo/Physics-Inform-Neural-Network
  paper1: https://arxiv.org/pdf/1711.10561.pdf
  paper2: https://arxiv.org/pdf/1711.10566.pdf
---

## Overview

This repository contains **PyTorch implementations** of physics-informed neural networks (PINNs)
for a range of canonical partial differential equations (PDEs), following the framework introduced
by Raissi et al. in *Physics-Informed Deep Learning*. :contentReference[oaicite:11]{index=11}

PINNs incorporate the governing PDE directly into the loss function, so that the neural network
approximation respects both **data observations** and **physical laws** (e.g., residuals of the
differential equation and boundary/initial conditions).

## What the code covers

The repository includes experiments for multiple PDEs: :contentReference[oaicite:12]{index=12}

- **Burgers’ equation** (continuous and discrete identification).
- **KdV equation** (nonlinear wave propagation).
- **Navier–Stokes** equations (fluid dynamics).
- **Schrödinger** equation (quantum dynamics).

For each problem, I implement:

- A neural network that maps space–time coordinates to the solution field.
- A **physics-informed loss** combining:
  - Data mismatch (observed points).
  - PDE residuals computed via automatic differentiation.
- Training scripts / notebooks for solving both **forward** and **inverse** problems (e.g.,
  recovering unknown parameters from observed dynamics).

## Highlights

- Hands-on implementation of **PINNs** for several benchmark PDEs.
- Shows how to integrate **automatic differentiation** with PDE residuals in PyTorch.
- A useful starting point for more advanced **scientific machine learning** and
  **physics-constrained neural operators**.
