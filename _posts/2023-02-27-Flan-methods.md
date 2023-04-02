---
layout: post
title:  "The Flan Collection [AI - NLP]"
---

# The Flan Collection: Designing Data and Methods for Effective Instruction Tuning

This study is about analyzes the design decisions of instruction tuning methods, specifically focusing on Flan 2022. The authors conduct ablation studies to understand the impact of various design decisions on Flan-T5's performance on a collection of tasks. They find that task balancing and enrichment techniques are crucial to effective instruction tuning, and training with mixed prompt settings yields better performance. Additionally, they show that Flan-T5 requires less finetuning to achieve better performance than T5 on single downstream tasks, which suggests that instruction-tuned models could be more computationally efficient starting checkpoints for new tasks. Overall, this study aims to understand the factors that contribute to the success of instruction tuning methods and identify ways to improve their effectiveness.

Along with the paper, researchers also open source the Flan 2022 collection of datasets, templates, and methods.

Paper: https://arxiv.org/abs/2301.13688

Dataset: https://github.com/google-research/FLAN/tree/main/flan/v2

![flanpaper](/assets/flanm.jpeg]
