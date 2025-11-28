---
layout: project
title: "NER-Ebay-2023: Named Entity Recognition at eBay Scale"
description: "Competing in the 2023 eBay NER challenge on 10M+ product titles using BiLSTM and BiLSTM-CRF models."
date: 2023-05-10
image: /assets/img/projects/ner-ebay.png
tags: ["NLP", "NER", "sequence labeling", "BiLSTM", "CRF"]
links:
  github: https://github.com/manhbeo/NER-Ebay-2023
  competition: https://eval.ai
---

## Overview

This repository contains my solution to the **2023 eBay Named Entity Recognition (NER) task** on
EvalAI, where the goal is to tag entities in **10,000,000+ product titles**. Because of competition
rules, the dataset cannot be shared, but the full modeling pipeline is available in notebooks and
scripts. :contentReference[oaicite:4]{index=4}

The main challenge is scaling NER models to very large, noisy e-commerce text while staying within
memory constraints.

## Approach

I explored several **sequence labeling** architectures:

- An initial setup with **two BiLSTM models**:
  - One model to detect multi-word tokens.
  - A second model to perform NER on those tokens.
- This approach produced an extremely large token list that was difficult to handle on a single
  machine. :contentReference[oaicite:5]{index=5}

To address this, I switched to a classic **BI tagging scheme**:

- For each word at the beginning of an entity span, I prepend `"B-"` to its tag.
- For subsequent words inside the span, I prepend `"I-"` to their tags.
- I then train BiLSTM / BiLSTM-CRF models directly at the **word level**, which is more memory-friendly. :contentReference[oaicite:6]{index=6}

Because the prediction set is very large, inference is parallelized to keep runtime manageable. :contentReference[oaicite:7]{index=7}

## Highlights

- Practical experience with **industrial-scale NER** (10M titles).
- Comparison of **token-level vs. word-level** tagging schemes under tight memory constraints.
- End-to-end pipeline mixing **Python (modeling)** and **R (data cleaning / preprocessing)** for a
  real-world competition environment.
