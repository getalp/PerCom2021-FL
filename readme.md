
## Federated Distance (FedDist)
This is the code accompanying the Percom2021 paper "A Federated Learning Aggregation Algorithm for Pervasive Computing: Evaluation and Comparison"

### Overview
---
The FedDist algorithm incorporates a pair-wise distance scheme for identifying outlier-like neurons/filters.  These outlier-like neurons/filter may be in fact features learned from sparse data and so it is directly added to the server model for the next round of training.

### Core Dependencies (tested and stable)
---
* Tensorflow 2.1.0
* PyTorch 1.1
* scikit-learn 0.22.1

All the working scripts are presented in a Jupiter notebook file format.

There is an array of 3rd party packages that is necessary for the entirety of the scripts to run. It is recommended to run command "pip3 install -r requirements.txt" in your virtual environment and working directory to replicate the environments used in this experiment.

### Data Preparation
---
"DATA_UCI.ipynb" and "DATA_REALWORLD_SPLITSUB.ipynb" are respectively used to prepare the UCI and REALWORLD dataset for training. Simply run all cells in a Jupyter notebook. The formatted dataset will be placed in a new directory "datasetStand"

### FL script implementations

The FedAvg and FedPer implementations are found in the file "FedAvg_FedPer_GPU_CPU.ipynb". You must specify which algorithm you which to run in the second cell of the notebook by changing the "algorithm" variable to either "FEDAVG" or "FEDPER"

FedDist is found in "FedDist_CPU.ipynb" and can only trained on CPU otherwise will run to a memory allocation problem when on GPU.


FedMA is found in the "FedMA_GPU_CPU.ipynb" file.

For all the federated algorithms, the second cell gives a variety of options and testing environment to choose from. We recommend leaving the configuration in default other than changing the "algorithm" variable and specifying the GPU/CPU to use. Simply run all cells to start training. 

If preferred to run as a python script, convert the files to a .py format VIA Jupiter notebook. Simply specify the wanted parameters in the second cell beforehand.

### Results Interpretability
All results of each experiments shall generated the "savedModels" folder. Within this folder will contain subfolders with the name of the chosen configuration and model architecture of the experiment. Additionally, within each model architecture folder will contain the another subfolder with the name of the dataset used for the experiment. E.g a directory should appear somethings as:
```
./savedModels/FED_5C_10LE_50CR_400D_100D_BALANCED/UCI
```

Now within this folder:

The  final  server  model  is  saved  in  a .h5format.  The  recorded  training  statistics  foreach  communication  round,  such  as  the  accuracy  and  loss of  the  clients  model  and  server  model,  are  stored  in  the trainingStats folder. The  results  regarding  the Global accuracy and  the  detail of  the  server  model  can  be  found  on  the  generated Server-Measure.csv file.  Results  for  the Personalization accuracy can   be   found   in   the indivualClients Measure.csv file   and finally  the Generalization accuracy can  be  found  at  the AllClientsMeasure.csv file.

### Sample script sequence
```
1.DATA_UCI.ipynb
2.DATA_REALWORLD_SPLITSUB.ipynb
3.FedAvg_FedPer_GPU_CPU.ipynb/FedDist_CPU.ipynb/FedMA_GPU_CPU.ipynb

```
### Citing FedDist:
---
```
Sannara Ek, François Portet, Philippe Lalanda, and German Vega. A federated learning ag-gregation algorithm for pervasive computing:  Evaluation and comparison.  In2021 IEEEInternational Conference on Pervasive Computing and Communications (PerCom) (Per-Com 2021), Kassel, Germany, March 2021.
```
