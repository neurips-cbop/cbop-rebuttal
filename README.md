# cbop-rebuttal

This repository contains the performance comparison of EDAC and CBOP based on [RLiable](https://github.com/google-research/rliable).

RLiable provides a reliable comparison between different RL algorithms when there are multiple tasks in each of which a limited number of experiments are conducted.

The methods that are compared here include:

1. Reproduced EDAC following the author-provided code.
2. (CBOP-EDAC) CBOP is trained starting from a policy and a value function pre-trained by EDAC.
3. (CBOP-BC+PE) CBOP trained with the initialization given by policy evaluation (PE) and behavior cloning (BC) of the given offline data in a supervised manner. 

Here are the results:

1. When we compare EDAC vs. CBOP-EDAC (w. EDAC pretraining). Results are evaluated on all locomotion configurations (3 x 6 = 18 tasks).

<img src="https://github.com/neurips-cbop/cbop-rebuttal/blob/main/locomotion_aggregates_all_tasks.png" width="1000">

<img src="https://github.com/neurips-cbop/cbop-rebuttal/blob/main/probability_of_improvement_full.png" width="300">

2. When we compare EDAC, CBOP-EDAC (w. EDAC pretraining), and CBOP-BC+PE (w/o EDAC pretraining). Results are evaluated on 9 locomotion configurations (3 tasks per environment).

<img src="https://github.com/neurips-cbop/cbop-rebuttal/blob/main/locomotion_aggregates_9tasks.png" width="1000">

<img src="https://github.com/neurips-cbop/cbop-rebuttal/blob/main/probability_of_improvement_9_tasks.png" width="300">

* Notice that CBOP performance (regardless of pretraining) is consistently better than that of EDAC in all the metrics used to evaluate the algorithms. 
* For the first three metrics (Median, IQM, Mean), the higher the better; whereas for Optimality Gap, the lower the better. 
* Notice also that the confidence intervals of CBOP do not overlap with those of EDAC, indicating statistically significant improvement over the baseline.
* Interestingly, CBOP with EDAC pretraining turns out to underperform CBOP w/o pretraining (we selected 9 tasks for this evaluation due to limited resources we have until the rebuttal deadline). 
* The results of EDAC and CBOP-EDAC are consistent with the ones reported in the initial submission. Since we only had a single number for the reproduced EDAC per task, we ran the algorithm for 2 more runs per task to create these comparison results.

[Additional notes]

* We used fitted Q-evaluation (FQE) for PE following [Le et al. (2019)](https://arxiv.org/abs/1903.08738).
