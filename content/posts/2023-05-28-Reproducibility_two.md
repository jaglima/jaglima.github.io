+++
author = "Jesse Lima"
title = "Reproducibility concepts"
date = "2023-05-28"
tags = ["SoR", "UCSC", "reproducibility", "Data Science", "Machine Learning"]
category = ["blog", "reproducibility", "SoR"]
+++

In the literature, it is possible to find different references and conceptualizations about reproducibility. Usually, a newcomer tends to use the term "reproducibility" across different stages of a workflow with different meanings. In these cases, terms like repeatability and replicability come into play.

Lynnerup et al. (2020) disserted about what they called a "confused taxonomy" that creates "confusion on the meaning of repeatability, reproducibility, and replicability, which, in turn, negatively affects the overall development of science." Some works do not distinguish between reproducibility and replicability.

![Experiments](/images/pipeline2.png "Experiments")

One way to define the three concepts is:

- Repeatability (Same team, same experimental setup): The measurement can be obtained with stated precision by the same team using the same measurement procedure, the same measuring system, under the same operating conditions, and in the same location on multiple trials. For computational experiments, this means that a researcher can reliably repeat her own computation.

- Replicability (Different team, same experimental setup): The measurement can be obtained with stated precision by a different group using the same measurement procedure, the same measuring system, under the same operating conditions, in the same or a different location on multiple trials. For computational experiments, an independent group can obtain the same result using the author’s own artifacts.

- Reproducibility (Different team, different experimental setup): The measurement can be obtained with stated precision by a different team, a different measuring system, in a different location on multiple trials. For computational experiments, an independent group can obtain the same result using artifacts that they develop completely independently.

For a comprehensive discussion and historical aspects, a good summary is presented in the work of Lynnerup et al. (2020).

**Bibliography:**

Lynnerup, N. "A Survey on Reproducibility by Evaluating Deep Reinforcement Learning Algorithms on Real-World Robots." Proceedings of the Conference on Robot Learning (2020).