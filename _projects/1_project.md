---
layout: page
title: "TreeCLR: Hierarchical Multi-Label Contrastive Learning"
description: "PyTorch reimplementation of a hierarchical multi-label contrastive learning framework on ImageNet-style label trees."
date: 2023-01-15
image: /assets/img/projects/treeclr.png
tags: ["contrastive learning", "representation learning", "hierarchical labels", "PyTorch"]
links:
  github: https://github.com/manhbeo/TreeCLR
  paper: https://arxiv.org/abs/2204.13207

---

TreeCLR is a PyTorch reimplementation of the *Use All The Labels: A Hierarchical Multi-Label
Contrastive Learning Framework* (CVPR 2022). It adapts supervised contrastive learning to
hierarchical label spaces, so nearby nodes in the label tree are embedded closer than distant ones.

---

## 🔍 Summary

Instead of treating all non-matching classes as equally negative, TreeCLR leverages a label
hierarchy (e.g., WordNet for ImageNet) to:

- Treat semantically related classes as **softer negatives** or **additional positives**.
- Encode the label tree into the contrastive loss so that the representation space preserves
  coarse-to-fine semantics.
- Improve downstream performance on classification and retrieval under hierarchical labels.

---

## 🛠️ What I implemented

- A **hierarchy-aware contrastive loss** extending supervised contrastive learning to multi-label
  trees.
- Data loading utilities for ImageNet-style datasets with child→parent mappings.
- Training & evaluation scripts for:
  - Representation learning with TreeCLR.
  - k-NN / linear probing on the learned embeddings.

---

## 📂 GitHub repository

- Code & experiments: **[github.com/manhbeo/TreeCLR](https://github.com/manhbeo/TreeCLR)**
- Reference paper: *Use All The Labels: A Hierarchical Multi-Label Contrastive Learning Framework*  
  (arXiv:2204.13207).
