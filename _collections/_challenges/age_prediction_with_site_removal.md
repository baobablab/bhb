---
layout: page
title: Age prediction with site-effect removal
cat: regression
subcat: age
headline: 
teasing: A challenge on the openBHB dataset that aims to i) predict age from derived 3D T1w anatomical MRI data while ii) removing site/scanner information from the learned representation.
challenge_url: https://ramp.studio/problems/brain_age_with_site_removal
icon: age_prediction_with_site_removal.jpg
image: age_prediction_with_site_removal.jpg
added: 2021
---

### Link to the challenge

The challenge is available on [RAMP.studio](https://ramp.studio/problems/brain_age_with_site_removal).
The code of the challenge is available on GitHub [RAMP.kits](https://github.com/ramp-kits/brain_age_with_site_removal).

### Contents

1. [Challenge description](#challenge-description)
2. [Ranking of the best models](#ranking-of-the-best-models)
3. [Metrics](#metrics)
4. [Baselines](#baselines)


### Challenge description

The challenge uses the openBHB dataset and aims to i) predict age from derived
data from 3D T1 anatomical MRI while ii) removing site information from the
learned representation. Thus, we aim to compare the capacity of proposed
models to encode a relevant representation of the data (feature extraction
and dimensionality reduction) that preserve the biological variability
associated with age while removing the site-specific information. The
algorithms submitted must output a low-dimension features vector (p < 10000).
Derived data are composed of Quasi-Raw, VBM, and SBM.


### Ranking of the best models

A public leaderboard with up-to-date results is available
[here](https://ramp.studio/events/brain_age_with_site_removal_open_2022/leaderboard)

**Warning:** This public leaderboard contains the **metrics computed on the public validation set**.
It may be biased by models trained on all public data. To access to this
leaderboard, you must be registered to the challenge.

Last update: 28/07/2022

<div style="overflow-x:scroll" markdown="1">

|   rank | submission          |   submission ID | team                | private challenge_metric   | private mae_age     | private rmse_age       | private bacc_site   | private ext_mae_age   |   train time [s] |   validation time [s] |   test time [s] |
|-------:|:--------------------|----------------:|:--------------------|:---------------------------|:--------------------|:-----------------------|:--------------------|:----------------------|-----------------:|----------------------:|----------------:|
|      1 | Raw-ResNet18Fixed   |           13186 | dufumier            | 0.257 &#177; 0.003         | 2.605 &#177; 0.003  | 3.784 &#177; 0.009     | 0.076 &#177; 0.001  | 2.849 &#177; 0.004    |         5277.2   |              5382.19  |        1934.13  |
|      2 | VBM-ResNet18-Combat |           13181 | dufumier            | 0.278 &#177; 0.001         | 4.152 &#177; 0.010  | 5.661 &#177; 0.001     | 0.045 &#177; 0.000  | 4.765 &#177; 0.026    |         4159.28  |              2460.55  |        1355.03  |
|      3 | VBM-ResNet18        |           13165 | dufumier            | 0.323 &#177; 0.005         | 2.672 &#177; 0.005  | 3.782 &#177; 0.006     | 0.067 &#177; 0.001  | 4.182 &#177; 0.013    |         4526.6   |              2903.9   |        1512.07  |
|      4 | VBM-DenseNet-Combat |           13182 | dufumier            | 0.326 &#177; 0.005         | 5.924 &#177; 0.016  | 8.285 &#177; 0.024     | 0.022 &#177; 0.001  | 10.479 &#177; 0.175   |         5299.13  |              2730.91  |        1373.32  |
|      5 | test_resnet18_plz   |           13177 | carloalbertobarbano | 0.348 &#177; 0.009         | 7.153 &#177; 0.024  | 9.931 &#177; 0.017     | 0.026 &#177; 0.001  | 8.997 &#177; 0.094    |         3629.25  |              2428.9   |        1408.31  |
|      6 | VBM-AlexNet-ComBat  |           13166 | dufumier            | 0.407 &#177; 0.008         | 3.371 &#177; 0.013  | 4.757 &#177; 0.017     | 0.068 &#177; 0.003  | 5.226 &#177; 0.123    |         3232.82  |              2651.88  |        1412.39  |
|      7 | VBM-AlexNet         |           13162 | dufumier            | 0.427 &#177; 0.009         | 2.721 &#177; 0.014  | 3.938 &#177; 0.034     | 0.083 &#177; 0.002  | 4.664 &#177; 0.051    |         3303.52  |              2638.55  |        1460.07  |
|      8 | Raw-DenseNetFixed   |           13188 | dufumier            | 0.480 &#177; 0.026         | 2.480 &#177; 0.028  | 3.555 &#177; 0.015     | 0.152 &#177; 0.006  | 2.917 &#177; 0.069    |        23515     |             27156.4   |       10750     |
|      9 | FSL-Desikan-ComBat  |           13184 | dufumier            | 0.513 &#177; 0.007         | 4.609 &#177; 0.032  | 6.970 &#177; 0.032     | 0.083 &#177; 0.003  | 5.304 &#177; 0.243    |          858.845 |               175.855 |         174.825 |
|     10 | VBMDenseNetComBat2  |           13189 | dufumier            | 0.561 &#177; 0.002         | 3.143 &#177; 0.018  | 4.499 &#177; 0.021     | 0.091 &#177; 0.001  | 5.652 &#177; 0.076    |         6327.54  |              3214.8   |        1634.09  |
|     11 | starting_kit_aws01  |           13031 | frcaud              | 0.612 &#177; 0.066         | 2.549 &#177; 0.009  | 3.632 &#177; 0.010     | 0.080 &#177; 0.009  | 7.132 &#177; 0.050    |         6084.69  |              3149.87  |        1548.43  |
|     12 | FSL-Destrieux-MLP   |           13161 | dufumier            | 0.622 &#177; 0.024         | 3.118 &#177; 0.005  | 4.675 &#177; 0.008     | 0.128 &#177; 0.005  | 4.476 &#177; 0.017    |          867.162 |               162.107 |         166.278 |
|     13 | Raw-AlexNetFixed    |           13187 | dufumier            | 0.637 &#177; 0.019         | 2.966 &#177; 0.005  | 4.219 &#177; 0.010     | 0.162 &#177; 0.005  | 3.653 &#177; 0.010    |         4477.48  |              5631.27  |        2248.19  |
|     14 | FSL-Desikan-MLP     |           13167 | dufumier            | 0.690 &#177; 0.021         | 3.370 &#177; 0.003  | 5.266 &#177; 0.006     | 0.112 &#177; 0.005  | 5.704 &#177; 0.092    |          955.707 |               189.201 |         192.269 |
|     15 | FSL-Xhemi-MLP       |           13183 | dufumier            | 0.755 &#177; 0.056         | 3.486 &#177; 0.010  | 5.225 &#177; 0.019     | 0.144 &#177; 0.011  | 4.849 &#177; 0.025    |         3308.46  |              1450.24  |        1417.52  |
|     16 | Raw-AlexNet         |           13178 | dufumier            | 0.771 &#177; 0.072         | 25.781 &#177; 4.621 | 201.736 &#177; 64.595  | 0.030 &#177; 0.000  | 12.105 &#177; 0.194   |        21039.4   |             26687.6   |       10584.8   |
|     17 | Raw-DenseNet121     |           13180 | dufumier            | 1.067 &#177; 0.109         | 49.928 &#177; 8.501 | 477.521 &#177; 137.401 | 0.016 &#177; 0.000  | 18.346 &#177; 1.543   |        22371.9   |             26164.5   |       10033.8   |
|     18 | FSLDestrieux-ComBat |           13185 | dufumier            | 1.177 &#177; 0.091         | 4.565 &#177; 0.108  | 6.415 &#177; 0.116     | 0.169 &#177; 0.020  | 6.547 &#177; 0.409    |          731.527 |               155.31  |         155.983 |
|     19 | Raw-ResNet18        |           13179 | dufumier            | 1.400 &#177; 0.063         | 73.693 &#177; 3.555 | 735.751 &#177; 43.062  | 0.016 &#177; 0.000  | 15.891 &#177; 0.529   |        20976.5   |             26187.9   |       10497     |

</div><br/>


### Metrics

Models submitted are evaluated with the standard linear evaluation protocol
(see Figure below) to predict age and site from the data encoded by the
submitted models.


![Evaluation protocol]({{site.url}}{{site.baseurl}}/images/resources/model-evaluation-workflow.jpg){:class="center"}

**Legend:** model evaluation workflow of a new submission. When a new trained
model is submitted to [RAMP](https://ramp.studio/problems/brain_age_with_site_removal),
a linear probe (regressor for age prediction and classifier for site
classification) is trained on top of the public embedded data (i.e. public
data encoded by the submitted model). Once trained, this linear probe predicts
the downstream targets (age and site) on the private embedded data (age is
predicted from both private internal and external tests while site is
predicted from private internal test only). 3 metrics are then derived: Mean
Absolute Error (MAE) for age prediction on internal and external test; Balanced
Accuracy (BAcc) for site prediction on internal test.  These 3 metrics are
combined to derive the final challenge metric Lc.

Three metrics are computed on encoded data (a.k.a model representation):

- **MAE{int}** :arrow_down: Mean Absolute Error (MAE) for age prediction on
  internal test (images acquired from same scanners/sites as training images);
- **MAE{ext}** :arrow_down: MAE for age prediction on external test
  (cross-scanners/sites images);
- **Bacc** :arrow_down Balanced Accuracy for site prediction on internal test.

The overall challenge metrics is computed as follows:


> Lc = **BAcc**(sites)^0.3 . **MAE{ext}**(age) + (1/Nsites)^0.3  **MAE{int}**(age)

As a result, the model representation should be invariant to noise induced
during acquisition (low Bacc) but should retain biological variability
associated to age (low MAE).


### Baselines

**Implementation:** you can find the PyTorch implementation of the previous
models in the GitHub repository:
[https://github.com/Duplums/brain_age_with_site_removal](https://github.com/Duplums/brain_age_with_site_removal).
        
We performed baseline experiments,a nd trained CNNs with various architectures
on whole-brain measures (VBM and Quasi-Raw). The objective function is a
simple l1-loss on age prediction for all models. 
We tested ComBat data-based debiasing models, that correponds to classical
harmonization of the training set (test sets are left unharmonized since
age and site labels are not available). We reported the 3 metrics used in
the challenge: MAE on the openBHB and privateBHB test sets and Bacc for
site prediction. The latent space dimension varied across CNN architectures
and it is always reported.

<div style="overflow-x:scroll" markdown="1">

**De-biasing method** | **Model (latent dims)**  | | | **VBM** | | | **Quasi-Raw** | | |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |  :---: |  :---: |
| | Int. Test MAE | Ext. Test MAE | Site Pred. BAcc | Lc | Int. Test MAE | Ext. Test MAE | Site Pred. BAcc | Lc
❌ | DenseNet(1024) | 2.55 ± 0.009  | 7.13 ± 0.05 | 8.0 ± 0.9 | 3.34 | 2.48 ± 0.03 | 2.92 ± 0.07 | 15.2 ± 0.6 | 1.66
❌ | ResNet(512) | 2.67 ± 0.05 | 4.18 ± 0.01 | 6.7 ± 0.1 | 1.86 | 2.60 ± 0.003 | 2.85 ± 0.004 | 7.6 ± 0.1 | 1.31
❌ | AlexNet(128 | 2.72 ± 0.01 | 4.66 ± 0.05 | 8.3 ± 0.2 | 2.21 | 2.96 ± 0.005 | 3.65 ± 0.009 | 16.2 ± 0.5 | 2.11
ComBat | DenseNet(1024) | 5.92 ± 0.01 | 10.48 ± 0.17 | 2.23 ± 0.06 | 5.08 | ❌ | ❌ | ❌ | ❌
ComBat | ResNet(512) | 4.15 ± 0.009 | 4.76 ± 0.03 | 4.5 ± 0.0 | 1.88  | ❌ | ❌ | ❌ | ❌
ComBat | AlexNet(128 | 3.37 ± 0.01 | 5.23 ± 0.12 | 6.8 ± 0.3 | 2.33 | ❌ | ❌ | ❌ | ❌

</div><br/>


**Legend:** baselines obtained with 1) no de-biasing strategy (first 3 rows) and
2) ComBat residualization on training data (last 3 rows) with VBM and Quasi-Raw
data for 3 representative CNN families.

We can notice that all models retain site information without any debiasing
strategy. Overall, Quasi-Raw data are more biased than VBM, and CNN preserve
this bias to some extent. The ResNet seems to be the best trade-off as it
is robust to site and it generalizes well on the privateBHB test set.
Interesingly, ComBat harmonization does remove most of site bias in CNN
representation space (with site prediction Bacc almost matching the one
obtained using only age as input). However, it also heavily degrades CNN
performance on age prediction for all testing sets (in particular for DenseNet).
ComBat is not fitted for Quasi-Raw data as it mainly relies on voxel-wise
statistics, and raw data are not properly registrated voxel-wise across images.
Consequently, we did not evaluated this approach on Quasi-Raw images.

