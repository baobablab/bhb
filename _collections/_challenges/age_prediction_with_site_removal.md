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

|   rank | submission         |   submission ID | team     | private challenge_metric   | private mae_age    | private rmse_age   | private bacc_site   | private ext_mae_age   |   train time [s] |   validation time [s] |   test time [s] |
|-------:|:-------------------|----------------:|:---------|:---------------------------|:-------------------|:-------------------|:--------------------|:----------------------|-----------------:|----------------------:|----------------:|
|      1 | VBM-ResNet18       |           13165 | dufumier | 0.323 &#177; 0.005         | 2.672 &#177; 0.005 | 3.782 &#177; 0.006 | 0.067 &#177; 0.001  | 4.182 &#177; 0.013    |         4526.6   |              2903.9   |        1512.07  |
|      2 | VBM-AlexNet-ComBat |           13166 | dufumier | 0.407 &#177; 0.008         | 3.371 &#177; 0.013 | 4.757 &#177; 0.017 | 0.068 &#177; 0.003  | 5.226 &#177; 0.123    |         3232.82  |              2651.88  |        1412.39  |
|      3 | VBM-AlexNet        |           13162 | dufumier | 0.427 &#177; 0.009         | 2.721 &#177; 0.014 | 3.938 &#177; 0.034 | 0.083 &#177; 0.002  | 4.664 &#177; 0.051    |         3303.52  |              2638.55  |        1460.07  |
|      4 | starting_kit_aws01 |           13031 | frcaud   | 0.612 &#177; 0.066         | 2.549 &#177; 0.009 | 3.632 &#177; 0.010 | 0.080 &#177; 0.009  | 7.132 &#177; 0.050    |         6084.69  |              3149.87  |        1548.43  |
|      5 | FSL-Destrieux-MLP  |           13161 | dufumier | 0.622 &#177; 0.024         | 3.118 &#177; 0.005 | 4.675 &#177; 0.008 | 0.128 &#177; 0.005  | 4.476 &#177; 0.017    |          867.162 |               162.107 |         166.278 |
|      6 | FSL-Desikan-MLP    |           13167 | dufumier | 0.690 &#177; 0.021         | 3.370 &#177; 0.003 | 5.266 &#177; 0.006 | 0.112 &#177; 0.005  | 5.704 &#177; 0.092    |          955.707 |               189.201 |         192.269 |

</div><br/>

Most up-to-date results on the public leaderboard are available [here](https://ramp.studio/events/brain_age_with_site_removal_open_2022/leaderboard).

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


