# cbop-rebuttal

This repository contains the performance comparison of EDAC and CBOP based on [RLiable](https://github.com/google-research/rliable).

RLiable provides a reliable comparison between different RL algorithms when there are multiple tasks in each of which a limited number of experiments are conducted.

The methods that are compared here include:

1. Reproduced EDAC following the author provided code.
2. (CBOP-EDAC) CBOP trained starting from a policy and a value function pre-trained by EDAC.
3. (CBOP-BC+PE) CBOP trained with the initialization given by policy evaluation and behavior cloning of the given offline data in a supervised manner.

Here are the results:

1. When we compare EDAC vs. CBOP (w. EDAC pretraining)

<img src="https://github.com/neurips-cbop/cbop-rebuttal/blob/main/locomotion_aggregates_all_tasks.png" width="1000">

2. When we compare EDAC, CBOP (w. EDAC pretraining), and CBOP (w/o EDAC pretraining)

<img src="https://github.com/neurips-cbop/cbop-rebuttal/blob/main/locomotion_aggregates_9tasks.png" width="1000">

* Notice that CBOP performance (regardless of pretraining) is consistently better than that of EDAC in all the metrics used to evaluate the algorithms. 
* For the first three metrics (Median, IQM, Mean), the higher the better; whereas for Optimality Gap, the lower the better. 
* Notice also that the confidence intervals of CBOP do not overlap with those of EDAC, indicating statistically significant improvement over the baseline.
* Interestingly, CBOP with EDAC pretraining turns out to underperform CBOP w/o pretraining (we selected 9 tasks for this evaluation due to limited resources we have until the rebuttal deadline). 
