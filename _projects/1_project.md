---
layout: project
title: "TreeCLR: Hierarchical Supervised Contrastive Learning"
description: "PyTorch implementation of supervised contrastive learning adapted to hierarchical multi-label data."
date: 2023-01-15
image: /assets/img/projects/treeclr.png
tags: ["contrastive learning", "representation learning", "hierarchical labels", "PyTorch"]
links:
  github: https://github.com/manhbeo/TreeCLR
  paper: https://arxiv.org/pdf/2204.13207.pdf
---

## Overview

TreeCLR is my implementation of **supervised contrastive learning** for datasets with
**hierarchical multi-label structure**. Instead of treating all non-matching labels as equally
negative, this variant uses a tree of class relationships (child–parent mappings) to shape which
examples are considered positives and how strongly they are pulled together in embedding space. :contentReference[oaicite:0]{index=0}

Concretely, the code adapts the supervised contrastive loss to leverage a label hierarchy (e.g.,
ImageNet’s WordNet tree) so that semantically close classes produce more similar representations,
while still separating distant branches of the tree.

## What I implemented

- A **TreeCLR loss** (see `SupTreeConLoss.py`) that extends supervised contrastive loss to
  hierarchical labels.
- Data loaders and utilities for **ImageNet** with child→parent label mappings
  (e.g., `child_to_parent_labels.txt`, `imgnet_parent_label.txt`). :contentReference[oaicite:1]{index=1}
- Training scripts with **LARS optimization** and standard contrastive-learning tricks.
- Evaluation via **k-NN classification** and **linear probing** on frozen embeddings.

## Highlights

- Shows how to plug a **label tree** into a standard supervised contrastive framework.
- Provides a template for experimenting with **hierarchy-aware representation learning**.
- Clean PyTorch implementation that can be adapted to other hierarchical datasets beyond ImageNet.
