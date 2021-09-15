---
layout: post
title: "GraphGym & PyG Integration"
date: 2021-09-14 23:00:00 +0800
post_image: "/assets/images/posts/graphgym_pipeline.png"
slider_post: true
---

**GraphGym** is a platform for **designing and evaluating Graph Neural
Networks (GNNs)**, as originally proposed in the ["Design Space for
Graph Neural Networks"](https://arxiv.org/abs/2011.08843) paper. **We now
officially support GraphGym as part of of PyG.**

We are continuously working on better and deeper GraphGym integration with PyG. We highly welcome any contribution or feedback!

## Highlights

1.  **Highly modularized pipeline for GNN:**
    -   **Data:** Data loading and data splitting
    -   **Model:** Modularized GNN implementations
    -   **Tasks:** Node-level, edge-level and graph-level tasks
    -   **Evaluation:** Accuracy, ROC AUC, ...

2.  **Reproducible experiment configuration:**
    -   Each experiment is *fully described by a configuration file*

3.  **Scalable experiment management:**
    -   Easily launch *thousands of GNN experiments in parallel*
    -   *Auto-generate* experiment analyses and figures across random
        seeds and experiments

4.  **Flexible user customization:**
    -   Easily *register your own modules*, such as data loaders, GNN
        layers, loss functions, etc

## Why GraphGym?

**TL;DR:** GraphGym is great for GNN beginners, domain experts and GNN
researchers.

**Scenario 1:** You are a beginner to graph representation learning and
want to understand how GNNs work:

You probably have read many exciting papers on GNNs, and try to write
your own GNN implementation. Even if using raw PyG, you still have to
code up the essential pipeline on your own. GraphGym is a perfect place
for your to start learning about *standardized GNN implementation and
evaluation*.


<div align="center">
  <img align="center" src="https://pytorch-geometric.readthedocs.io/en/latest/_images/graphgym_design_space.png" width="400px" />
  <b><br>Figure 1: Modularized GNN implementation.</b> 
</div>
<br>

**Scenario 2:** You want to apply GNNs to your exciting application:

You probably know that there are hundreds of possible GNN models, and
selecting the best model is notoriously hard. Even worse, the [GraphGym
paper](https://arxiv.org/abs/2011.08843) shows that the best GNN designs
for different tasks differ drastically. GraphGym provides a *simple
interface to try out thousands of GNNs in parallel* and understand the
best designs for your specific task. GraphGym also recommends a "go-to"
GNN design space, after investigating 10 million GNN model-task
combinations.

<div align="center">
  <img align="center" src="https://github.com/snap-stanford/GraphGym/raw/master/docs/rank.png" width="1000px" />
  <b><br>Figure 2: A guideline for desirable GNN design choices.</b> <br>(Sampling from 10 million GNN model-task combinations.) 
</div>
<br>

**Scenario 3:** You are a GNN researcher, who wants to innovate new GNN
models or propose new GNN tasks:

Say you have proposed a new GNN layer `ExampleConv`. GraphGym can help you
convincingly argue that `ExampleConv` is better than, *e.g.*,
`GCNConv`: When randomly sampling from 10
million possible model-task combinations, how often will `ExampleConv` outperform `GCNConv` when everything else
is fixed (including computational costs)? Moreover, GraphGym can help
you easily do hyper-parameter search, and *visualize* what design
choices are better. In sum, GraphGym can greatly facilitate your GNN
research.

<div align="center">
  <img align="center" src="https://github.com/snap-stanford/GraphGym/raw/master/docs/evaluation.png" width="1000px" />
  <b><br>Figure 3: Evaluation of a given GNN design dimension</b>, e.g., BatchNorm 
</div>
<br>


## GraphGym Quick start

After properly [installing](#installation) PyG, you can try out our GraphGym API to easily manage and launch GNN experiments. 

```bash
conda install pyg -c pyg -c conda-forge  # Install PyG
git clone https://github.com/pyg-team/pytorch_geometric.git  # Get GraphGym pipeline
cd pytorch_geometric/graphgym
bash run_single.sh  # run a single GNN experiment (node/edge/graph-level)
bash run_batch.sh  # run a batch of GNN experiments, with differnt GNN designs/datasets/tasks
```
Please find detailed documentation in our PyG [documentation](https://pytorch-geometric.readthedocs.io/en/latest/notes/graphgym.html#basic-usage).


