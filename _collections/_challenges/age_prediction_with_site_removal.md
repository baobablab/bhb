---
layout: page
title: Age prediction with site-effect removal
cat: regression
subcat: age
headline: 
teasing: A challenge on the openBHB dataset that aims to i) predict age from derived 3D T1w anatomical MRI data while ii) removing site/scanner information from the learned representation.
challenge_url: https://ramp.studio
icon: age_prediction_with_site_removal.jpg
image: age_prediction_with_site_removal.jpg
added: 2021
---

### Link to the challenge

The challenge is available here: [RAMP.studio](https://ramp.studio/).


### Contents

1. [Challenge description](#challenge-description)
2. [Ranking of the best models](#ranking-of-the-best-models)
3. [Metrics](#metrics)
4. [Baselines](#baselines)


### Challenge description

The challenge uses the openBHB dataset and aims to i) predict age from derived data from 3D T1 anatomical MRI while ii) removing site information from the learned representation. Thus, we aim to compare the capacity of proposed models to encode a relevant representation of the data (feature extraction and dimensionality reduction) that preserve the biological variability associated with age while removing the site-specific information. The algorithms submitted must output a low-dimension features vector (p < 10000). Derived data are composed of Quasi-Raw, VBM, and SBM.


### Ranking of the best models


|   rank | team     | submission         |   challenge_metric |   train time [s] |   validation time [s] | submitted at (UTC)   |
|-------:|:---------|:-------------------|-------------------:|-----------------:|----------------------:|:---------------------|
|      1 | dufumier | VBM-AlexNet-ComBat |              0.268 |          3232.82 |               2651.88 | 2022-06-17 17:34:21  |
|      2 | frcaud   | starting_kit_aws01 |              0.095 |          6084.69 |               3149.87 | 2022-05-04 08:05:51  |


### Metrics

A logistic regression is used to evaluate the representation quality on site prediction using the openBHB training set encoded with the submitted model. As for age prediction, a ridge regression is used on the same features.

To rank submissions, we have developed a novel metric that jointly evaluates 2 key properties of the learnt representation: its robustness w.r.t sites and the quantity of information preserved w.r.t chronological age. This metric is based on 2 reference metrics: Mean Absolute Error for age prediction (MAE, to be  minimized), and Balanced Accuracy for site prediction (BAcc, it should be equal to random chance). BAcc is privileged instead of accuracy since some sites are over-represented in openBHB. The openBHB and privateBHB private test sets are derived to compute them: one containing the same sites as the training set and the other completely independent sites. Both will be used to compute MAE for age prediction. Only the first one is used to derive BAcc for site prediction. All metrics will be displayed during the challenge.


### Baselines
        
We performed baseline experiments,a nd trained CNNs with various architectures on whole-brain measures (VBM and Quasi-Raw). The objective function is a simple l1-loss on age prediction for all models. 
We tested ComBat data-based debiasing models,that correponds to classical harmonization of the training set (test sets are left unharmonized since age and site labels are not available). We reported the 3 metrics used in the challenge: MAE on the openBHB and privateBHB test sets and Bacc for site prediction. The latent space dimension varied across CNN architectures and it is always reported.

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


