
## Federated Distance (FedDist)
This is the code accompanying the Percom2021 paper "A Federated Learning Aggregation Algorithm for Pervasive Computing: Evaluation and Comparison" and the code of federated learning experiments by Sannara Ek during his master thesis.

### Overview
---
This experiments compares 3 federated learning algorithms along with a new one, FedDist.
The FedDist algorithm incorporates a pair-wise distance scheme for identifying outlier-like neurons/filters.  These outlier-like neurons/filter may be in fact features learned from sparse data and so it is directly added to the server model for the next round of training.

### Core Dependencies (tested and stable)
---
* Tensorflow 2.2.2
* PyTorch 1.1
* scikit-learn 0.22.1

All the working scripts are presented in a Jupiter notebook file format.

There is an array of 3rd party packages that is necessary for the entirety of the scripts to run. It is recommended to run command "pip3 install -r requirements.txt" in your virtual environment and working directory to replicate the environments used in this experiment.

### Data Preparation
---
"DATA_UCI.ipynb" and "DATA_REALWORLD_SPLITSUB.ipynb" are respectively used to prepare the UCI and REALWORLD dataset for training. Simply run all cells in a Jupyter notebook. The formatted dataset will be placed in a new directory "datasetStand"

### FL script implementations
---
The FedAvg and FedPer implementations are found in the file "FedAvg_FedPer.ipynb". You must specify which algorithm you which to run in the third cell of the notebook by changing the "algorithm" variable to either "FEDAVG" or "FEDPER"

FedDist is found in the "FedDist.ipynb" file.

FedMA is found in the "FedMA.ipynb" file.

For all the federated algorithms, the third cell gives a variety of options and testing environment to choose from. We recommend leaving the configuration in default other than changing the "algorithm" variable and specifying the GPU/CPU to use. Simply run all cells to start training. 

If preferred to run as a python script, convert the files to a .py format VIA Jupiter notebook (FILES -> Download as -> Python (.py)). 

Additionally with the command below from a console achieves the same result:
```
jupyter nbconvert --to script '[ScriptName].ipynb'

```
Simply specify the wanted parameters in the third cell beforehand. 

### Results Interpretability
---
All results of each experiments shall generate the "savedModels" folder. Within this folder will contain subfolders with the name of the chosen configuration and model architecture of the experiment. Additionally, within each model architecture folder will contain the another subfolder with the name of the dataset used for the experiment. E.g a directory should appear like:
```
./savedModels/FED_5C_10LE_50CR_400D_100D_BALANCED/UCI
```

Now within this folder:

The  final  server  model  is  saved  in  a .h5 format.  The  recorded  training  statistics  foreach  communication  round,  such  as  the  accuracy  and  loss of  the  clients  model  and  server  model,  are  stored  in  the trainingStats folder. The  results  regarding  the Global accuracy and  the  detail of  the  server  model  can  be  found  on  the  generated Server-Measure.csv file.  Results  for  the Personalization accuracy can   be   found   in   the indivualClients Measure.csv file   and finally  the Generalization accuracy can  be  found  at  the AllClientsMeasure.csv file.

### Sample script sequence:
---
An example of execution would be to first download and format the dataset (UCI and REALWORLD) then execute one of the FL algorithms (requires several days on CPU). 


```
1.DATA_UCI.ipynb
2.DATA_REALWORLD_SPLITSUB.ipynb
3.FedAvg_FedPer.ipynb/FedDist.ipynb/FedMA.ipynb

```
### Citing this work:
---
```
@INPROCEEDINGS{Lala2103:Federated,
AUTHOR="Sannara Ek and François Portet and Philippe Lalanda and German Vega",
TITLE="A Federated Learning Aggregation Algorithm for Pervasive Computing:
Evaluation and Comparison",
BOOKTITLE="2021 IEEE International Conference on Pervasive Computing and
Communications (PerCom) (PerCom 2021)",
ADDRESS="Kassel, Germany",
DAYS=21,
MONTH=mar,
YEAR=2021,
KEYWORDS="Federated Learning; Edge Computing; Human activity recognition"
}
```

### Contact:
---
Please contact the authors by [firstname].[lastname]@univ-grenoble-alpes.fr if you have issues with the code.

To contact Sannara Ek, Please use [firstname].[lastname]@gmail.com
