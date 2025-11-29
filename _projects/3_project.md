---
layout: page
title: "NER-Ebay-2023: Large-Scale E-commerce NER"
description: "Named entity recognition on noisy product titles using BiLSTM and BiLSTM-CRF models."
date: 2023-05-10
image: /assets/img/projects/ner-ebay-2023.png
tags: ["NLP", "NER", "sequence labeling", "BiLSTM", "CRF"]
links:
  github: https://github.com/manhbeo/NER-Ebay-2023
---

NER-Ebay-2023 is a practical pipeline for **named entity recognition on e-commerce product titles**,
built for a competition setting with millions of short, noisy text entries.

---

## 🔍 Summary

The project focuses on building sequence labeling models that can reliably extract entities from
real-world marketplace data where:

- Product titles are noisy and inconsistent.
- Entities often span multiple words.
- The label space mixes brands, attributes, and product categories.

---

## 🛠️ Modeling approach

- BiLSTM and BiLSTM-CRF architectures for sequence tagging.
- A **BI tagging scheme** for multi-word entities, balancing accuracy with memory usage.
- Scripts and notebooks for:
  - Preprocessing titles.
  - Training / evaluation.
  - Efficient batched inference for large prediction sets.

---

## 📂 GitHub repository

- Full code, notebooks, and pipeline:  
  **[github.com/manhbeo/NER-Ebay-2023](https://github.com/manhbeo/NER-Ebay-2023)**
