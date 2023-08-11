+++
author = "Jesse Lima"
title = "noWorkflow as provenance capture tool"
date = "2023-06-08"
tags = ["SoR", "UCSC", "reproducibility", "Data Science", "Machine Learning"]
category = ["blog", "reproducibility", "SoR"]
+++

__MLOps tools, Jupyter Notebooks and noWorkflow__

We briefly discussed some MLOps tools that offer provenance in this previous post. We encountered a rich and diverse ecosystem with multiple tools allowing different levels of reproducibility. By levels, we consider i) tools allowing provenance at different stages of a typical experiment and ii) tools that are more suitable for the experimental phases of a project, while others fit better for post-deployment phases.

We are specifically interested in tools that capture provenance in Machine Learning and Data Science typical experiments. These tools should capture provenance in feature, score, and evaluation layers (as discussed in this post). Furthermore, our focus is primarily on the experimental phases experiment’s lifecycle rather than the deployment phases.

![Experiments](/images/pipeline6.png)

In this scenario, i'm particularly enthusiastic about the noWorkflow project. According to the authors in Pimentel (2017), noWorkflow is an open-source tool designed to systematically and transparently collect provenance from Python scripts. Noworkflow captures data about the script execution and tracks the evolution of the script over time. In recent versions, the tool has evolved to enable provenance capture of experiments through Jupyter Notebooks.

Based on our review, I believe that noWorkflow shares the most resemblance to data and pipeline versioning tools. It is lightweight in its setup and config needs, is strongly based on the command line, and serves as a metadata store and experiment tracker. Among the tools examined, the most similar ones to noWorkflow are Pachyderm and DVC.

**The Jupyter Notebooks as literate programming enablers**

Donald Knuth (Knuth, D. E. (1984)) introduced the concept of literate programming as an approach to software development that emphasizes the readability and understandability of code. Currently, a great tool allowing literate programming are the Jupyter Notebooks.

According to Pimentel (2021), Jupyter Notebooks established itself as the basis of scientific experimentation by supporting the creation of documents that combine code, text, and execution results with visualizations and other rich media. The self-documenting aspects and the ability to reproduce results have been touted as significant benefits of notebooks.

Nevertheless, notebooks are prone to induce bad practices in software development. All its flexibility facilitates bad practices that hinder the reasoning and reproducibility of notebooks as artifacts. It happens when cells are allowed to be executed out-of-order, non-executed, or even allowing hidden states. At this point, reproducibility emerges as an outstanding solution while provenance capture permits identifying the correct cell execution order and hidden states' presence.

In the next post, we will go further into the noWorkflow features related to Jupyter Notebooks’ provenance tracking and its possible uses of it.

**Bibliography:**

Pimentel, J. F., Murta, L., Braganholo, V., & Freire, J. (2017). noWorkflow: A tool for collecting, analyzing, and managing provenance from Python scripts. Proceedings of the VLDB Endowment, 10(12).

Pimentel, J. F., Murta, L., Braganholo, V., & Freire, J. (2021). Understanding and improving the quality and reproducibility of Jupyter notebooks. Empirical Software Engineering, 26(4), 65.