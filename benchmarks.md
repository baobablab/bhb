---
layout: page
title: BHB-10K benchmarks
cat: benchmarks
subcat: overview
---

### Contents

1. [CNN models](#cnn-models)
2. [Bench 1: age & sex prediction](#bench-1-age--sex-prediction) \\
    a. [Learning curves](#learning-curves) \\
    b. [Linear model baseline](#linear-model-baseline) \\
    c. [CNN models](#cnn-models) \\
    d. [Test on BSNIP](#test-on-bsnip)


### CNN models

You can find some documentation on the CNN models currently used for the different benchmarks:

* [tiny-VGG](https://www.sciencedirect.com/science/article/pii/S1053811917306407) initially built for age prediction, it remains a competitive network
* [ResNet](https://arxiv.org/abs/1512.03385)
* [VGG](https://arxiv.org/abs/1409.1556)
* tiny-DenseNet
* [DenseNet](https://arxiv.org/abs/1608.06993)
* [ResNeXt](https://arxiv.org/abs/1611.05431)
* [SFCN](https://www.sciencedirect.com/science/article/pii/S1361841520302358) state-of-the-art for age and sex prediction on UKBioBank


### Bench 1: age & sex prediction

The objective of this benchmark is to predict age & sex from the BHB-10K dataset.
We reported the results for 3 (resp. 5) runs on 3 (resp. 5) Stratified Shuffle Splits at N=10K (resp. N=500).
We stratified according to the label to predict. The hyperparameters for the linear models are tuned using grid search. 

#### Learning curves

**VBM**
![Alt text](images/resources/benchmarks_age_sex_vbm.png)

**Quasi-Raw**
![Alt text](images/resources/benchmarks_age_sex_raw.png)

**Note:**  linear models give results no better than chance with quasi-raw data.

#### Linear model baseline

**Task** | **Model** | **# Training Samples**| **Pre-Processing** | **AUC**(%) | **MAE**
|:---: | :---: |:---: | :---: | :---: | :---: |
Age | Ridge | 10K |  VBM | N/A | 4.65±0.02 
Sex | Logistic | 10K | VBM  | 97.05±0.03   | N/A
SCZ vs HC | Logistic | 500 | VBM | 78.71±0.76 | N/A

#### CNN models

The models are trained for 300 epochs at N=10K and for 100 epochs at N=500. We use Deep Ensemble with T=5
CNN to have accurate and better calibrated models. 

**Task** | **Model** | **# Training Samples**|  **Deep Ensemble (x5)** | **Pre-Processing** |**Weights**
|:---: | :---: | :---: | :---: | :---: | :---: |
Age | DenseNet121 | 10K |  ❌ |  VBM | [download]()
Age | ResNet34 | 10K |  ❌ |  Quasi-Raw | [download]()
Sex | DenseNet121 | 10K |  ❌️ | VBM | [download]()
Sex | DenseNet121 | 10K |  ❌️ | Quasi-Raw  | [download]()
SCZ vs HC | tiny-DenseNet | 500 |  ✔️ | VBM |  [download]()
SCZ vs HC | DenseNet121 |500 |  ✔️ | Quasi-Raw | [download]()

#### Test on BSNIP

**Task** | **Model** | **Pre-Processing** | **AUC** | **MAE**
|:---: | :---: | :---: | :---: | :---: |
Age | DenseNet121 | VBM | N/A | **4.03±0.13** 
Age | ResNet34 |  Quasi-Raw | N/A | 4.84±0.26 
Sex | DenseNet121 | VBM | **97.69±0.21** | N/A
Sex | DenseNet121 | Quasi-Raw | 96.58±0.21 | N/A
SCZ vs HC | tiny-DenseNet ️ | VBM | **80.92±0.47**| N/A
SCZ vs HC | DenseNet121 | Quasi-Raw | 71.98±1.49 | N/A
