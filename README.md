# Cross Modality Knowledge Distillation forMulti modal Aerial View Object Classification
## Info
This repo is a implement of our team's solution on [NTIRE 2021 Multi-modal Aerial View Object Classification Challenge - Track 2 (SAR+EO)](https://competitions.codalab.org/competitions/28095)

Authors: [Lehan Yang](https://bio.lehanyang.info/); [Kele Xu](https://scholar.google.com/citations?user=sou7o2EAAAAJ&hl=zh-CN)

We proposed two KD method to do the aerial view object classification.

`Knowledge Distillation Method 1:`
<img src="https://github.com/Hansxsourse/Cross-Modality-Knowledge-Distillation-forMulti-modal-Aerial-View-Object-Classification/blob/main/imgs/eo-method1.jpg" data-canonical-src="https://github.com/Hansxsourse/Cross-Modality-Knowledge-Distillation-forMulti-modal-Aerial-View-Object-Classification/blob/main/imgs/eo-method1.jpg" width="1025" height="576" />

`Iteration Knowledge Distillation (Method 2)`
<img src="https://github.com/Hansxsourse/Cross-Modality-Knowledge-Distillation-forMulti-modal-Aerial-View-Object-Classification/blob/main/imgs/eo-method2.jpg" data-canonical-src="https://github.com/Hansxsourse/Cross-Modality-Knowledge-Distillation-forMulti-modal-Aerial-View-Object-Classification/blob/main/imgs/eo-method2.jpg" width="600" height="825" />

They are getting significant performance on NTIRE21 SAR+EO dataset:

|         | Top-1 Accuracy           |
| ------------- |:-------------:|
| Baseline     | 0.22337662 |
| KD (method 1)     | **0.31168831**   |
|KD (method 1) with Post-Processing|**0.36363636**|
| Iteration KD (method 2)| 0.23376623  |


## Env Requirement
`python 3.6 or later`

`pytorch 1.4.0 or later`

`CUDA`

## Usages
`Attentions:` Please make sure you have changed all the path in the code into your own path, include but not only `pretrain weight path` / `data path` / `saving path`

All these experiment folder are included a ready to run `ipython notebook file` and the `best weight` after training.

Training `log` include in the output of notebook training block.

`Training` `Prediction` method both include in each notenook file.
### Baseline
Use the Jupyter Notebook in `baseline` folder. 

For the training data structure in baseline, we used pytorch built in `ImageFolder` method, so you need to arrange the data into each folder which named with the label name.

We also did arrange the data to training data folder to train and valid data folder to evaluate.

Arranged data folder can be downloaded from [One Drive](https://unisydneyedu-my.sharepoint.com/:u:/g/personal/lyan3310_uni_sydney_edu_au/EefPAUWlmI9BjsJrZEiOM_QBICfvofKl75_AQxIMUA6Iig?e=qxEbzk)

### Knowledge Distillation Method 1
For the training data structure in both KD method 1 and 2, in order to make sure the data loader output is corresponding to SAR and EO, we built two csv files seperately for SAR and EO image, which is located in the `data` folder(you also need to change the file path of it in the notebook).

The notebook for this part is called `KD1.ipynb`, in `KD1` folder


### Knowledge Distillation Method 1 with Post Processing Step for Submission
The notebook for this part is called `KD1-pp.ipynb`, in `KD1` folder



### Iteration Knowledge Distillation (Method 2)
The notebook for this part is called `KD2.ipynb`, in `KD2` folder

Training on this notebook will saving both SAR part and EO part model in each iteration.
