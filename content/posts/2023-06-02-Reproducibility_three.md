+++
author = "Jesse Lima"
title = "Irreproducibility sources in ML, reproducibility and provenance"
date = "2023-06-02"
tags = ["SoR", "UCSC", "reproducibility", "Data Science", "Machine Learning"]
category = ["blog", "reproducibility", "SoR"]
+++


__Reproducibility and provenance in Machine Learning.__


The paper by Gundersen et al. (2022) provides an interesting description of the sources of irreproducibility in Machine Learning. The authors have compiled an extensive list of factors that can lead to irreproducibility in machine learning experiments. According to them, irreproducibility can arise from the following causes:

Study factors: selective tuning, p-hacking, p-fishing, experiment initialization, unsuited experimental design.

Algorithm factors: related to algorithmic questions such as hyperparameter optimization, random weights initialization, batch ordering, etc.

Implementation factors: initialization seeds, software, parallel execution, rounding errors, compiler settings.

Observation factors: dataset bias, preprocessing, data splits, environment properties, data augmentation.

Evaluation factors: selective reporting, sampled metrics, error estimation, statistical analysis, over-claiming results, etc.

Documentation factors: readability, experiment design details, workflow, implementation details, stale URLs, access to data, and access to code.


![Experiments](/images/pipeline3.png)


Such sources appear at different stages during the experimental phase and may even persist in production environments, leading to the accumulation of technical debt (Sculley et al., 2015). The problem or irreproducibility is also discussed in the work of Sugimura et al. (2018), referring to the "delivery fast and break things" recent trend prevalent in software engineering. This culture holds true in the realm of data science and machine learning as well. The velocity of deliverables usually comes at the expense of reproducibility, among other victims.

In an intent to enable reproducibility in Machine Learning, Sigimura et al. (2018) presented a typification of provenance required in a typical experiment. They highlight three primary forms of provenance: data provenance, feature provenance, and model provenance. Additionally, they include the software environment and implementation errors in the topic.

In a more detailed description, the authors outline the following:

Data provenance refers to the historical record of how the data of interest was collected. This is the most difficult challenge to ensure full reproducibility. If the dataset used to train a model changes after the time of training, then it may be difficult or impossible to reproduce a model. This usually occurs in two different ways. The first is when part of the training dataset is deleted or made unavailable. The second is more subtle and occurs if the dataset is updated. It is exposed to Documentation, Observation, and Study factors.

Feature provenance: This refers to the historical record of how a feature is generated. Any changes to the feature generation process should be tracked and version controlled, including models if their predictions are used as features. Compared to data provenance, addressing feature provenance is relatively easier since the information required is usually smaller, allowing for the preservation of all feature values.

Model provenance: This refers to the record of how a model was trained, including the order of features, applied feature transformations (e.g., standardization), hyperparameters of the algorithm, and the trained model itself. If the model consists of an ensemble of submodels, the structure of the ensemble must be saved.

Software environment: For full reproducibility, the software versions should match exactly or be compatible. Even if a software package makes a bugfix after a model is trained, the original flawed version should be used to maintain reproducibility.

Implementation error: This refers to code mismatches introduced by different implementations between experiments, and even between experimental code and production code. It is common for researchers to develop a model in their preferred language and then pass it on to the engineering team for implementation in a separate language.

By considering and addressing these aspects of provenance we can better tackle the challenge of tracking reproducibility in ML experiments. In future posts, we will consider a specific experiment and tools to study reproducibility.

**Bibliography:**
Gundersen, O. E., et al. "Sources of Irreproducibility in Machine Learning." (2022)

Sculley, D., et al. "Hidden Technical Debt in Machine Learning Systems." (2015)

Sugimura, R., et al. "Building a reproducible machine learning pipeline." (2018)