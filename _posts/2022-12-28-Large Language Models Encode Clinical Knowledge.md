---
layout: post
title:  "Large Language Models Encode Clinical Knowledge"
---

# LLMs & Health 

[Large Language Models Encode Clinical Knowledge](https://arxiv.org/pdf/2212.13138.pdf)

The advent of foundation AI models and large language models present a significant opportunity to develop medical AI and make it easier, safer and more equitable to use. At the same time, medicine is a complex domain for applications of large language models. 

This paper discusses the potential for large language models (LLMs) in the field of medicine and healthcare. LLMs can be repurposed for a variety of tasks, and have the ability to learn from large amounts of medical data. The authors present the potential of using LLMs for tasks such as knowledge retrieval, clinical decision support, and summarization of key findings. 

The safety-critical nature of the medical field requires careful evaluation of LLMs to ensure that they are aligning with clinical and societal values and not producing misinformation or biases. To address this, the authors have curated the MultiMedQA benchmark, a collection of seven datasets for evaluating medical questions answered by LLMs. 

![MultimedQA](/assets/MiltimedQA.jpeg)

The paper also discusses PaLM and its instructed-tuned variant Flan-PaLM, which they evaluate on the MultiMedQA benchmark and shows strong performance on several of the medical questions datasets. Finally, they propose instruction prompt tuning as a method for further aligning LLMs with the medical domain, and demonstrate its effectiveness through the creation of a model called Med-PaLM. 

![LLM Compared](/assets/llmcompare.jpeg)
