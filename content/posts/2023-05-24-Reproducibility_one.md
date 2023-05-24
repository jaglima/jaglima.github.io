+++
author = "Jesse Lima"
title = "Reproducibility on Data Experiments"
date = "2023-05-24"
tags = ["SoR", "UCSC", "reproducibility", "Data Science", "Machine Learning"]
category = ["blog", "reproducibility", "SoR"]
+++


This is my first post in a serie about my participation in the 1st Summer of Reproducibility at USCS, Summer 2023.

![games](/images/pipeline1.png).

## Reproducibility and Experiments Workflows

Since my early experiences in science craftship, reproducibility has been a thing. Scientific method requires that a scientific achievement be reproducible by anyone everywhere given the premises attended. This is a guarantee that there is a causal relationship between causes and consequences. If some implication remains consistenly true after being subject of experimentation it must be a scientific truth. 

Since my early experiences in the field of science, reproducibility has always been essential. The scientific method mandates that any scientific achievement should be replicable by anyone, anywhere, provided they adhere to the same premises. This requirement ensures that there exists a causal relationship between causes and consequences. If a certain implication consistently holds true after being repeatedly subjected to experimentation, it can be considered a scientific truth.

Although much can be said about what reproducibility means, the ability to replicate results in day-to-day Computer Science experiments can pose a significant challenge for indivuals, companies and labs. This challenge becomes even more pronouced with the emergence of analytics and IA, where scientific methodology are extensively applied on an industrial scale beyond the limits of academia. Reproducibility now assumes a key role in productivity and accountability expected from Data Scientists, Machine Learning Engineers and other roles engajed in ML/AI pro
jects. 

In the day to day, the pitfalls of non-reproducibility appear in different points of the experiment lifecycle. These challenges arise when multiple experiments needs to be managed for an individual scientist ou across a team of scientists. In a tipical experiment workflow, reproducibility appears in the needs of dataset's provenance, needs in managing changes on hipothesys tests, going throught managing hardware and operational system environmental attributes and dealing with outputs of model instances. In academic environments these issues can result in mistakes and innacuracies. In companies they can lead to inefficiences and technical debts that are difficult to address in the future. 

By feeling this pain in past experiences both, in industry and academia, the subject of reproducibility cought my attention. As reproducibility has being studied its concept is being amplified. This terminology usually support what a newcomer might mean by guaranteing that experiments are manageable and shows consistent results after a serie of trials. However, often in literature, terms like repeteability and replicability comes to play to amplify the coverage of our toolset. 
