---
title: CORAL:COde RepresentAtion Learning with Weakly-Supervised Transformers
date: 2020-02-16
description: How to automatically characterize data science process?
categories:
  - code representation learning
  - robust data science
  - graph neural networks
image:
    https://source.unsplash.com/collection/375719/2000x1322?a=.png
author_staff_member: Ge
---

Large scale analysis of computational notebooks holds the promise of better understanding the data science process, and providing insights to the builders of scientific toolkits. However, such notebooks have remained largely unanalyzed at scale, as labels are absent and require expert domain knowledge to generate. We present a new classification task for labeling computational notebook cells as stages in the data analysis process (i.e., data import, wrangling, exploration, modeling, and evaluation). For this task, we propose a novel weakly supervised transformer architecture (CORAL) for computing joint representations of data science code from both abstract syntax trees and natural language annotations. We show that our model, leveraging only easily-available weak supervision, achieves a 35% increase in accuracy over expert-supplied heuristics.

# Task

![Task](https://tva1.sinaimg.cn/large/0082zybply1gbybqmsa5ej30oo0c0abl.jpg)

We propose a new task and accompanying dataset for classifying code snippets as stages in the data science process. Above Figure shows two mock examples from this task. 

# Model 

![Model](https://tva1.sinaimg.cn/large/0082zybply1gbyb6luz08j30x80u0wlm.jpg)

CORAL is a model for learning neural representations of data science code snippets and classifying them as stages in the data analysis process.CORAL leverages both source code abstract syntax trees (ASTs) and associated natural language annotations in markdown text.It then learns a representation of code and markdown using the masked self-attention mechanism of [Transformers](http://papers.nips.cc/paper/7181-attention-is-all-you-need.pdf).To compensate for sparse labels, we combine weak supervision and unsupervised representation learning.For weak supervision, we use only five simple heuristics supplied by researchers, which provide weak labels to about 20\% of the cells in the training corpus. We also apply an unsupervised training objective akin to topic modeling, which seeks to reconstruct the cell embedding from the lower-dimensional cell topic distribution.

# Results

![Results](https://tva1.sinaimg.cn/large/0082zybply1gbyc20x84ej31gi0u0n9t.jpg)

Three predictions in this figure demonstrate CORAL's ability to capture data analysis semantics and inherent ambiguity. 
