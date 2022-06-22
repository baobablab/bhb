---
layout: page
title: Age prediction with site-effect removal
cat: regression
subcat: age
headline: 
teasing: A challenge on the openBHB dataset that aims to i) predict age from derived 3D T1w anatomical MRI data while ii) removing site/scanner information from the learned representation.
challenge_url: https://ramp.studio/events/brain_age_with_site_removal_open_2022
icon: age_prediction_with_site_removal.jpg
image: age_prediction_with_site_removal.jpg
added: 2021
---

### Link to the challenge

The challenge is available here: [RAMP.studio](https://ramp.studio/events/brain_age_with_site_removal_open_2022).
The code of the challenge is available here: [RAMP.kits](https://github.com/ramp-kits/brain_age_with_site_removal).

### Contents

1. [Challenge description](#challenge-description)
2. [Ranking of the best models](#ranking-of-the-best-models)
3. [Metrics](#metrics)
4. [Baselines](#baselines)


### Challenge description

The challenge uses the openBHB dataset and aims to i) predict age from derived data from 3D T1 anatomical MRI while ii) removing site information from the learned representation. Thus, we aim to compare the capacity of proposed models to encode a relevant representation of the data (feature extraction and dimensionality reduction) that preserve the biological variability associated with age while removing the site-specific information. The algorithms submitted must output a low-dimension features vector (p < 10000). Derived data are composed of Quasi-Raw, VBM, and SBM.


### Ranking of the best models

Last update: 22/06/2022

<div style="overflow-x:scroll" markdown="1">

|   rank |   move | team     | submission         |   challenge_metric |   train time [s] |   validation time [s] |   test time [s] | submitted at (UTC)   |
|-------:|-------:|:---------|:-------------------|-------------------:|-----------------:|----------------------:|----------------:|:---------------------|
|      1 |      1 | frcaud   | starting_kit_aws01 |              0.573 |          6084.69 |               3149.87 |         1548.43 | 2022-05-04 08:05:51  |
|      2 |     -1 | dufumier | VBM-AlexNet-ComBat |              0.398 |          3232.82 |               2651.88 |         1412.39 | 2022-06-17 17:34:21  |

</div><br/>

<div style="overflow-x:scroll" markdown="1">

|   submission ID | team     | submission         |   bag public challenge_metric |   mean public challenge_metric |   std public challenge_metric |   bag public mae_age |   mean public mae_age |   std public mae_age |   bag public rmse_age |   mean public rmse_age |   std public rmse_age |   bag public bacc_site |   mean public bacc_site |   std public bacc_site |   bag public ext_mae_age |   mean public ext_mae_age |   std public ext_mae_age |   bag private challenge_metric |   mean private challenge_metric |   std private challenge_metric |   bag private mae_age |   mean private mae_age |   std private mae_age |   bag private rmse_age |   mean private rmse_age |   std private rmse_age |   bag private bacc_site |   mean private bacc_site |   std private bacc_site |   bag private ext_mae_age |   mean private ext_mae_age |   std private ext_mae_age |   train time [s] |   validation time [s] |   test time [s] |   max RAM [MB] | submitted at (UTC)   |
|----------------:|:---------|:-------------------|------------------------------:|-------------------------------:|------------------------------:|---------------------:|----------------------:|---------------------:|----------------------:|-----------------------:|----------------------:|-----------------------:|------------------------:|-----------------------:|-------------------------:|--------------------------:|-------------------------:|-------------------------------:|--------------------------------:|-------------------------------:|----------------------:|-----------------------:|----------------------:|-----------------------:|------------------------:|-----------------------:|------------------------:|-------------------------:|------------------------:|--------------------------:|---------------------------:|--------------------------:|-----------------:|----------------------:|----------------:|---------------:|:---------------------|
|           13167 | dufumier | FSL-Desikan-MLP    |                         0.125 |                       0.148333 |                      0.021127 |                0.868 |              0.902333 |             0.079198 |                 1.662 |                1.776   |              0.239858 |                  0.127 |                0.143667 |               0.020841 |                    0.882 |                  0.932333 |                 0.009609 |                          0.666 |                        0.689667 |                       0.020551 |                 3.37  |                3.37033 |              0.002517 |                  5.266 |                 5.26633 |               0.005508 |                   0.106 |                 0.111667 |                0.005132 |                     5.77  |                    5.704   |                  0.091929 |          955.707 |               189.201 |         192.269 |              0 | 2022-06-20 17:10:22  |
|           13161 | dufumier | FSL-Destrieux-MLP  |                         0.187 |                       0.135667 |                      0.006028 |                0.807 |              0.861333 |             0.104309 |                 1.573 |                1.88333 |              0.314207 |                  0.204 |                0.142333 |               0.012097 |                    0.857 |                  0.863333 |                 0.031533 |                          0.643 |                        0.622    |                       0.023896 |                 3.113 |                3.11833 |              0.004726 |                  4.667 |                 4.67533 |               0.008021 |                   0.132 |                 0.128    |                0.004583 |                     4.496 |                    4.47633 |                  0.017214 |          867.162 |               162.107 |         166.278 |              0 | 2022-06-20 17:21:57  |
|           13031 | frcaud   | starting_kit_aws01 |                         0.095 |                       0.111667 |                      0.016166 |                0.785 |              0.887667 |             0.038501 |                 1.243 |                1.49167 |              0.25971  |                  0.1   |                0.122    |               0.021656 |                    0.825 |                  0.805    |                 0.035384 |                          0.573 |                        0.612333 |                       0.065546 |                 2.544 |                2.549   |              0.00866  |                  3.621 |                 3.632   |               0.009644 |                   0.075 |                 0.08     |                0.00866  |                     7.106 |                    7.132   |                  0.050319 |         6084.69  |              3149.87  |        1548.43  |              0 | 2022-05-04 08:05:51  |
|           13162 | dufumier | VBM-AlexNet        |                         0.098 |                       0.124333 |                      0.007506 |                0.933 |              0.886333 |             0.071557 |                 1.43  |                1.49567 |              0.222028 |                  0.099 |                0.110333 |               0.004726 |                    0.845 |                  1.00033  |                 0.041102 |                          0.432 |                        0.427333 |                       0.008963 |                 2.721 |                2.721   |              0.014    |                  3.947 |                 3.93833 |               0.033843 |                   0.084 |                 0.082667 |                0.001528 |                     4.633 |                    4.66367 |                  0.05054  |         3303.52  |              2638.55  |        1460.07  |              0 | 2022-05-30 16:32:23  |
|           13166 | dufumier | VBM-AlexNet-ComBat |                         0.268 |                       0.211    |                      0.016703 |                1.93  |              2.104    |             0.04015  |                 2.916 |                3.08467 |              0.085489 |                  0.104 |                0.086333 |               0.008145 |                    2.29  |                  2.05933  |                 0.096417 |                          0.398 |                        0.407333 |                       0.008145 |                 3.386 |                3.37067 |              0.013279 |                  4.773 |                 4.75667 |               0.017039 |                   0.065 |                 0.068    |                0.003    |                     5.294 |                    5.22633 |                  0.123314 |         3232.82  |              2651.88  |        1412.39  |              0 | 2022-06-17 17:34:21  |
|           13165 | dufumier | VBM-ResNet18       |                         0.069 |                       0.068333 |                      0.001528 |                0.738 |              0.734    |             0.058207 |                 1.178 |                1.31367 |              0.226588 |                  0.078 |                0.073667 |               0.003512 |                    0.744 |                  0.775667 |                 0.007572 |                          0.318 |                        0.323333 |                       0.004726 |                 2.669 |                2.67167 |              0.004619 |                  3.778 |                 3.78167 |               0.006351 |                   0.066 |                 0.067333 |                0.001155 |                     4.169 |                    4.18233 |                  0.012583 |         4526.6   |              2903.9   |        1512.07  |              0 | 2022-06-17 11:07:31  |

</div><br/>

### Metrics

A logistic regression is used to evaluate the representation quality on site prediction using the openBHB training set encoded with the submitted model. As for age prediction, a ridge regression is used on the same features.

To rank submissions, we have developed a novel metric that jointly evaluates 2 key properties of the learnt representation: its robustness w.r.t sites and the quantity of information preserved w.r.t chronological age. This metric is based on 2 reference metrics: Mean Absolute Error for age prediction (MAE, to be  minimized), and Balanced Accuracy for site prediction (BAcc, it should be equal to random chance). BAcc is privileged instead of accuracy since some sites are over-represented in openBHB. The openBHB and privateBHB private test sets are derived to compute them: one containing the same sites as the training set and the other completely independent sites. Both will be used to compute MAE for age prediction. Only the first one is used to derive BAcc for site prediction. All metrics will be displayed during the challenge.


### Baselines
        
We performed baseline experiments,a nd trained CNNs with various architectures on whole-brain measures (VBM and Quasi-Raw). The objective function is a simple l1-loss on age prediction for all models. 
We tested ComBat data-based debiasing models, that correponds to classical harmonization of the training set (test sets are left unharmonized since age and site labels are not available). We reported the 3 metrics used in the challenge: MAE on the openBHB and privateBHB test sets and Bacc for site prediction. The latent space dimension varied across CNN architectures and it is always reported.

<div style="overflow-x:scroll" markdown="1">

**De-biasing method** | **Model (latent dims)**  | | **VBM** | | | **Quasi-Raw** | |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| | openBHB MAE | privateBHB MAE | Site pred BAcc | openBHB MAE | privateBHB MAE | Site pred BAcc |
❌ | DenseNet(1024) | 2.55 | 6.35 | 10.2 | 2.42 | 2.78 | 20.4
❌ | ResNet(512) | 2.75 | 4.03 | 6.88 | 2.58 | 2.77 | 8.40
❌ | AlexNet(128 | 2.76 | 5.01 | 8.60 | 2.85 | 3.21 | 19.30
ComBat | DenseNet(1024) | 8.32 | 8.91 | 2.10 | ❌ | ❌ | ❌
ComBat | ResNet(512) | 4.07 | 3.80 | 3.86  | ❌ | ❌ | ❌
ComBat | AlexNet(128 | 5.40 | 6.47 | 4.09 | ❌ | ❌ | ❌

</div><br/>

We can notice that all models retain site information without any debiasing strategy. Overall, Quasi-Raw data are more biased than VBM, and CNN preserve this bias to some extent. The ResNet seems to be the best trade-off as it is robust to site and it generalizes well on the privateBHB test set. 
Interesingly, ComBat harmonization does remove most of site bias in CNN representation space (with site prediction Bacc almost matching the one obtained using only age as input). However, it also heavily degrades CNN performance on age prediction for all testing sets (in particular for DenseNet). ComBat is not fitted for Quasi-Raw data as it mainly relies on voxel-wise statistics, and raw data are not properly registrated voxel-wise across images. Consequently, we did not evaluated this approach on Quasi-Raw images. 


