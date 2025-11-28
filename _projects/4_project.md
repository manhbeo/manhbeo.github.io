---
layout: project
title: "SenNet + HOA: 3D Blood Vessel Segmentation"
description: "U-Net-based segmentation of 40GB+ 3D kidney scans for the SenNet + HOA Kaggle competition."
date: 2023-06-20
image: /assets/img/projects/sennet.png
tags: ["medical imaging", "3D segmentation", "U-Net", "Kaggle"]
links:
  github: https://github.com/manhbeo/SENNET
  competition: https://www.kaggle.com/competitions/blood-vessel-segmentation
---

## Overview

This project is my implementation for the **“SenNet + HOA – Hacking the Human Vasculature in 3D”**
Kaggle competition. The task is to segment blood vessels in large **3D TIFF scans of human kidneys**
(>40 GB of data). :contentReference[oaicite:8]{index=8}

Because competition rules prohibit releasing the dataset, only the code and modeling pipeline are
public, but they are fully reproducible if you have access to the original data.

## Method

- I use a **U-Net architecture** for volumetric segmentation of the 3D scans. :contentReference[oaicite:9]{index=9}
- The model predicts voxel-wise vessel masks, which are then converted into
  **run-length encoded (RLE) masks** to match the Kaggle submission format. :contentReference[oaicite:10]{index=10}
- The repository includes:
  - Notebooks for training and validation (`U_net.ipynb`).
  - Utilities for handling large TIFF volumes efficiently.
  - Code that transforms U-Net outputs into RLE strings for submission.

## Highlights

- Hands-on experience with **3D medical image segmentation** on large datasets.
- Practical handling of **GPU memory** and I/O constraints for 40GB+ of volumetric data.
- A reusable template for future **Kaggle medical imaging** or 3D segmentation challenges.
