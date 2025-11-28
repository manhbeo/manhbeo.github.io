---
layout: project
title: "SenNet + HOA: 3D Blood Vessel Segmentation"
description: "U-Net-based 3D vessel segmentation for the SenNet + HOA Kaggle competition."
date: 2023-06-20
image: /assets/img/projects/sennet.png
tags: ["medical imaging", "3D segmentation", "U-Net", "Kaggle"]
links:
  github: https://github.com/manhbeo/SENNET
  competition: https://www.kaggle.com/competitions/blood-vessel-segmentation
---

This project contains my solution for the **“SenNet + HOA – Hacking the Human Vasculature in 3D”**
Kaggle challenge, which focuses on segmenting blood vessels in large 3D TIFF scans of human kidneys.

---

## 🔍 Summary

Given massive 3D volumes, the goal is to produce voxel-wise vessel masks that can be used to study
vascular morphology and support the Human Reference Atlas effort. The main challenges are:

- 40GB+ of volumetric data per competition bundle.
- Highly imbalanced vessel vs. background classes.
- Tight GPU memory constraints for 3D convolutions.

---

## 🧠 Method

- A **3D U-Net** architecture for volumetric segmentation.
- Training and inference pipelines tailored to:
  - Patch-based processing of large volumes.
  - Careful memory management on commodity GPUs.
- Post-processing that converts predicted masks to **run-length encoded (RLE)** strings to match
  Kaggle’s submission format.

---

## 📂 GitHub repository

- Code & notebooks: **[github.com/manhbeo/SENNET](https://github.com/manhbeo/SENNET)**
- Competition: SenNet + HOA – *Blood Vessel Segmentation in 3D*.
