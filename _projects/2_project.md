---
layout: page
title: "cDDPM in PyTorch"
description: "Implementing classifier-free diffusion guidance and exploring U-Net + attention designs for diffusion models."
date: 2023-02-01
image: /assets/img/projects/cddpm.png
tags: ["diffusion models", "generative models", "guidance", "PyTorch"]
links:
  github: https://github.com/manhbeo/cDDPM
  paper: https://arxiv.org/abs/2207.12598
---

cDDPM is a PyTorch implementation of **classifier-free diffusion guidance**, with experiments on how
U-Net depth, width, and attention affect the trade-off between sample quality and diversity.

---

## 🔍 Summary

Instead of using a separate classifier at sampling time, classifier-free guidance trains a single
diffusion backbone in two modes—**conditional** and **unconditional**—and combines their scores
with a tunable guidance scale. This project:

- Implements a DDPM-style backbone with classifier-free guidance.
- Exposes the guidance weight as a simple knob for quality vs. diversity.
- Uses the implementation as a sandbox to study architectural tweaks.

---

## 🧠 Architecture & experiments

- U-Net backbone with configurable:
  - Number of channels per stage.
  - Attention blocks at chosen resolutions.
- Experiments on:
  - Varying guidance scales and observing mode collapse vs. sharpness.
  - Changing attention configuration (heads, resolutions) and U-Net depth.

---

## 📂 GitHub repository

- Code & training scripts: **[github.com/manhbeo/cDDPM](https://github.com/manhbeo/cDDPM)**
- Reference: *Classifier-Free Diffusion Guidance* (Ho & Salimans, 2022, arXiv:2207.12598).
