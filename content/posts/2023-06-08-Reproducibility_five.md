+++
author = "Jesse Lima"
title = "MLOps Tooling and reproducibility"
date = "2023-06-12"
tags = ["SoR", "UCSC", "reproducibility", "Data Science", "Machine Learning"]
category = ["blog", "reproducibility", "SoR"]
+++


__A market overview.__


As we discussed in the previous post [link here](/content/posts/2023-06-08-Reproducibility_four.md), the Data Science experiments and Machine Learning pipelines are composed of layers or stages that have some resemblance across projects. With the emergence of IA, organizations have been looking for solutions that encompass these steps making MLOps workflow no longer complicated.


![Experiments](/images/pipeline5.png)


Many projects have been initiated to meet the challenges of MLOps. They vary from point solutions to attend just one step in the process to broad scopes, aiming for end-to-end management. Some are available as software packages, others as SaaS. 

Curiously, most of these tools end up offering features in different layers we have discussed (i.e. data, feature, scoring, and evaluation), which is evidence of a market in an exploratory process. This lack of standards makes any assessment difficult. Some projects try to incorporate any low-hanging fruit feature into their core functionality. Then, they come up with a tool with elements of all layers.

Keeping in mind the division into data, feature, scoring, and evaluation from here, there are two groups of tools oriented to the initial phases of the discovery/research process. They are:

**Data and Pipeline Versioning**: Platforms dealing with ingestion, processing, and exposing of features for model training and inference. They also enable collaboration and discoverability of already existing Feature Sets throughout the organization. Provide provenance and lineage for data in different levels of complexity.

**Metadata Stores/Experiment Trackers**: they are specifically built to store metadata about ML experiments and expose it to stakeholders. They help the debugging, comparing, and collaborating on experiments. It is possible to divide in Experiment Tracker and a Model Registry.

On the other hand, there are projects offering reproducibility elements like hyperparameter search, experiment versioning, etc. However, they are better suited for projects in the production/monitoring phases. They are:

**Pipeline frameworks**: They operate within the realm of production, similar to Data Engineering workflows. Their usual goal is to allow any ML/AI products to be served across a wide range of architectures and integrate all the low-hanging fruits along the way. For instance, pipelines adding hyperparameter optimization tasks, experiment tracking integrations, boilerplate containerized deployment, etc.

**Deployment and Observability**: They focus on deploying models for real-time inference and monitoring model quality once they are deployed in production. Their aim is to facilitate post-deployment control tasks such as monitoring feature drift, conducting A/B testing, and more.

With real world examples, we can mention some interesting cases:

The only tool offering coverage for all aforementioned layers is Weights & Biases. It is a paid SaaS solution.

In the data pipeline versioning DVC and  Pachyderm are two candidates there shows some resemblance. DVC appears to work jointly with Git and with a Git-based approach. Pachyderm seems more complex and oriented to Kubernetes clusters and cloud solutions.

There exist specific tools exclusively for feature management like Hopsworks, and Featureform.

The pipeline framework candidates are Kubeflow, ZenML, Dagster, or Polyaxon. The Kubeflow is the more emblematic case here. It is an initiative from the Kubernetes community to deploy and manage an ML stack on Kubernetes. 

The Metadata Stores/Experiment Trackers examples are MLFlow and Neptune. 

As deployment and observability examples we can mention H2O, DataRobot, or Seldon. All of them are specialized in makes easier the deployment monitoring of ML products in production. As commented earlier, they touch on reproducibility but while in production, not in experimental phases. 

As final comments, there are as many tools as there are approaches to implementing machine learning operations. There exist solutions attending the common cloud machine learning engineer in their preferred stack. Other solutions aim to attend to the typical data scientist craving to deploy their models in any architecture available. Other approaches are "automation oriented",  trying to allow the citizen data scientist to deploy as smoothly as possible or the experimental teams. All of them touch on reproducibility in some ways. None of them seems a one-stop-shop solution that encompasses all needs.