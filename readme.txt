Run command "pip3 install -r requirements.txt" in your virtual environment and working directory to replicate the environments used in this experiment.


All the working scripts are presented in a Jupiter notebook file format.

"DATA_UCI.ipynb" and "DATA_REALWORLD_SPLITSUB.ipynb" are respectively used to prepare the UCI and REALWORLD dataset for training. Simply run all cells in a Jupyter notebook. The formatted dataset will be placed in a new directory "datasetStand"

The FedAvg and FedPer implementations are found in the file "FedAvg_FedPer_GPU_CPU.ipynb". You must specify which algorithm you which to run in the second cell of the notebook by changing the "algorithm" variable to either "FEDAVG" or "FEDPER"

FedDist is found in "FedDist_CPU.ipynb" and can only trained on CPU otherwise will run to a memory allocation problem when on GPU.


FedMA is found in the "FedMA_GPU_CPU.ipynb" file.

For all the federated algorithms, the second cell gives a variety of options and testing environment to choose from. We recommend leaving the configuration in default other than changing the "algorithm" variable and specifying the GPU/CPU to use. Simply run all cells to start training. 

If preferred to run as a python script, convert the files to a .py format VIA Jupiter notebook. Simply specify the wanted parameters in the second cell beforehand.