+++
author = "Jesse Lima"
title = "Data, Features Scoring and Evaluation provenance"
date = "2023-06-08"
tags = ["SoR", "UCSC", "reproducibility", "Data Science", "Machine Learning"]
category = ["blog", "reproducibility", "SoR"]
+++


__Conceptual layers in Machine Learning pipelines.__


Going one step further into the real-life provenance questions, a good start is to adopt some terminology to prepare our way.


![Experiments](/images/pipeline4.png)


In Sugimura and Hartl (2018), a modular taxonomy is proposed to address the challenge of reproducible Machine Learning pipelines. According to the authors, a pipeline can be modularized into data, feature, scoring, and evaluation layers. Modularizing the pipeline in this way showed itself a natural mode to pose the problem. We will use the same approach in our posts defining each layer as follows:

Data layer: a data layer should provide access to all data sources to guarantee data provenance. It must guarantee the provenance of all data transformation related to data exploration actions performed by Data Scientists.

Feature layer: Although it shares some resemblance with data exploration, this layer is responsible for feature generation in a transparent, reusable, and scalable manner. Each feature must have its sources uniquely and clearly defined, and implementation and transformation details must be accessible through provenance.

Scoring Layer: The scoring layer transforms features into predictions. It should be compatible with multiple machine-learning libraries and allows workflows of more sophisticated approaches, for instance, an ensemble of models.

Evaluation Layer: The last step in the process of ensuring model reproducibility involves the evaluation layer. This layer can check the equivalence of two models as well as evaluate the relative performance of an arbitrary number of models. It must allow any model performance metrics the problem might need (AUC, RMSE, log-loss). Finally, it can be used to monitor production models, to check how closely the predictions on live traffic match the training predictions.

All that being said, we are ready to assess the overall space of Machine Learning solutions available in the current MLOPs market. It will be the subject of our next post.

**Bibliography:**

Sugimura, R., et al. "Building a reproducible machine learning pipeline." (2018)