---
layout: project
title: "cDDPM: Classifier-Free Diffusion Guidance in PyTorch"
description: "Implementation and extensions of classifier-free diffusion guidance, exploring attention and U-Net architectures."
date: 2023-02-01
image: /assets/img/projects/cddpm.png
tags: ["diffusion models", "generative models", "guidance", "PyTorch"]
links:
  github: https://github.com/manhbeo/cDDPM
  paper: https://arxiv.org/abs/2207.12598
---

## Overview

This project implements **classifier-free diffusion guidance** (Ho & Salimans, 2022) in PyTorch. :contentReference[oaicite:2]{index=2}  
Instead of using a separate classifier to guide sampling, classifier-free guidance jointly trains
**conditional** and **unconditional** diffusion models and mixes their score estimates at sampling
time, trading off sample quality vs. diversity through a single guidance weight.

Starting from a faithful implementation of the original method, I then explore architectural and
training-time modifications to better understand how guidance interacts with the **U-Net backbone**
and **self-attention** layers.

## What I implemented

- A minimal yet complete **DDPM-style diffusion model** (`diffusion.py`, `model.py`) with
  classifier-free guidance.
- Training loop that jointly learns conditional and unconditional score networks, matching the
  setup in the original paper. :contentReference[oaicite:3]{index=3}
- Sampling code that exposes a **guidance scale** hyperparameter to control quality vs. diversity.
- Checkpointing and utilities for experimenting with different guidance strengths (weights).

## Architecture & experiments

- **U-Net backbone** with attention blocks, where I:
  - Modify the **attention mechanism** (number of heads, attention resolutions).
  - Vary U-Net depth/width and compare their effect under strong vs. weak guidance.
- Ablation studies on:
  - Guidance scales (how far we can push quality before diversity collapses).
  - Different conditioning setups (e.g., class labels, simple text/labels).

Overall, cDDPM serves as a compact codebase for experimenting with **guidance strategies and
architectural tweaks** in diffusion models.
