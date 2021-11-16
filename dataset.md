---
layout: page
title: BHB-10K dataset
cat: dataset
subcat: overview
image: preproc.png
---


### Contents

1. [Healthy controls datasets](#healthy-controls-datasets)
2. [Clinical datasets](#clinical-datasets)
3. [Pre-processed datasets](#pre-processed-datasets)
4. [Training/test split](#trainingtest-split)


### Healthy controls datasets

BHB-10K is an aggregation of 13 pubicly available brain MRI datasets of healthy controls (HC).

<div style="overflow-x:scroll" markdown="1">

**Available** | **Source**  | **# Subjects**  | **# Sessions** | **Age** | **Sex (\%F)** | **# Sites**
|:---:|:---: | :---: | :---: | :---: | :---: | :---: | 
❌ | [HCP](https://www.humanconnectome.org/study/hcp-young-adult)  | 1113 | 1113 | 29 ± 4 | 45 | 1
❌ | [IXI](http://brain-development.org/ixi-dataset) | 559 | 559 | 48 ± 16 | 55 | 3 
❌ | [CoRR](https://www.nitrc.org/projects/fcon_1000) | 1371 | 2897 | 26 ± 16 | 50 | 19
❌ | [NPC](https://openneuro.org/datasets/ds002330/versions/1.1.0) | 65 | 65 | 26 ± 4 | 55 | 1
❌ | [NAR](https://openneuro.org/datasets/ds002345/versions/1.0.1) | 303 | 323 | 22 ± 5 | 58 | 1
❌ | [RBP](https://openneuro.org/datasets/ds002247/versions/1.0.0) | 40 | 40 | 23 ± 5 | 52 | 1
❌ | [OASIS 3](https://www.oasis-brains.org) | 597 | 1262 | 67 ± 9 | 62 | 3
❌ | [GSP](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/25833) | 1570 | 1639 | 21 ± 3 | 58 | 1
❌ | [ICBM](https://ida.loni.usc.edu) | 622 | 977 | 30 ± 12 | 45 | 3
❌ | [ABIDE 1](http://fcon_1000.projects.nitrc.org/indi/abide) | 567 | 567 | 17 ± 8 | 17 | 20
❌ | [ABIDE 2](http://fcon_1000.projects.nitrc.org/indi/abide) | 559 | 580 | 15 ± 9 | 30 | 17
❌ | [Localizer](http://brainomics.cea.fr/localizer/localizer) | 82 | 82 | 25 ± 7 | 56 | 2
❌ | [MPI-Leipzig](https://openneuro.org/datasets/ds000221/versions/00002) | 316 | 316 | 37 ± 19 | 40 | 2
**Total** | | 7764 | **10420** | 32 ± 19 | 50 | 74 
**Currently** | | 0 | 0 | 0 | 0 | 0

</div>

### Clinical datasets

BHB-10K contains also clinical datasets composed of only schizophrenia data for the moment.

<div style="overflow-x:scroll" markdown="1">

**Available** | **Source**  | **# Subjects** | **Diagnosis** | **Age** | **Sex (\%F)** | **# Sites**
:---: | :---: | :---: | :---: | :---: | :---: | :---: | 
❌| [BSNIP](https://academic.oup.com/schizophreniabulletin/article/40/Suppl_2/S131/1933599)  | 394 | Schizophrenia<br>Control | 34 ± 12<br>38 ± 13  | 44<br>58  | 5 
❌| [SCHIZCONNECT-VIP](http://schizconnect.org) | 605 | Schizophrenia<br>Control | 34 ± 12<br>32 ± 12  | 27<br>47  | 4 

</div>

### Pre-processed datasets

All the dataset has been preprocessed with the [brainprep](https://brainprep.readthedocs.io) using container technologies in order to ease reproducable research over time.
Only T1w pre-processed data are avaible for the moment, more specifically VBM, Quasi-Raw, and FreeSurfer.

**Quasi-Raw**: it consists essentially in brain extraction with [BET2](http://poc.vl-e.nl/distribution/manual/fsl-3.2/bet2) 
and a linear registration to the MNI template with [FLIRT](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FLIRT) for a final 
isotropic spatial resolution of 1.5mm.

**Voxel-Based Morphometry (VBM)**: this is an extensive pre-processing performed with [CAT12](http://www.neuro.uni-jena.de/cat/). 
The brain is segmented into 3 tissues: Gray Matter (GM), White Matter (WM) and Cerebrospinal Fluid (CSF) and it is then re-aligned 
non-linearly to the MNI template with [DARTEL](https://pubmed.ncbi.nlm.nih.gov/17761438) resampled at 1.5mm isotropic.
 We used only the T1-weighted modulated GM modality.  

<div style="overflow-x:scroll" markdown="1">

**Dataset** | **Pre-Processing** | **# Images** | **Target**|  **Link** 
|:---:|:---:|:---:|:---:|:---:|
BHB-10K |  Quasi-Raw | ?  | Age + Sex | ? |
BHB-10K | VBM | ? | Age + Sex | ? | 
SCHIZCONNECT-VIP | Quasi-Raw | 605 | SCZ vs CTL | *Pending* |
SCHIZCONNECT-VIP | VBM | 605 | SCZ vs CTL | *Pending*|

</div>

### Training/test split

We aim at giving results in the real clinical setting where the model is evaluated on new data arriving from
different hospitals (different acquisition protocols). 

<div style="overflow-x:scroll" markdown="1">

Task | Training Set | Test Sets | 
|:---: | :---: | :---: |
Age | BHB-10K | BSNIP (**only HC**)
Sex | BHB-10K | BSNIP (**only HC**)
SCZ vs HC | SCHIZCONNECT-VIP | BSNIP 

</div>

