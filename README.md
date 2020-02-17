# Code for the paper "Exposing Backdoors in Robust Machine Learning Models"

The introduction of robust optimisation has pushed the state-of-the-art in defending against adversarial attacks. 
However, the behaviour of such optimisation has not been studied in the light of a fundamentally different class of attacks 
called backdoors. In this work, we demonstrate that adversarially robust models are susceptible to backdoor attacks.

Subsequently, we observe that backdoors are reflected in the feature representation of such models. 
Then, this is leveraged to detect backdoor-infected models. Specifically, we use feature clustering to effectively detect 
backdoor-infected robust Deep Neural Networks (DNNs). 
In our evaluation of major classification tasks, our approach effectively detects robust DNNs infected with backdoors. 
Our investigation reveals that salient features of adversarially robust DNNs break the stealthy nature of backdoor attacks.

### Dependencies
* Python 3
* Keras
* Pytorch
* Random
* Pickle
* Math
* Matplotlib
* OpenCV
* h5py
* ipython
* numpy
* robustness package
* cox

In case of any unforseen dependencies, a detailed ```pip freeze``` of the system used to develop this code can be found 
[here](https://docs.google.com/document/d/1Cbcfiv3Y7Fz3jKcwv-h2EWLBY37orPuwbflp_C8P2ok/edit?usp=sharing) 

### Repository Organisation
In our evaluation, we examine three types of robust models corresponding to three datasets, namely CIFAR-10, Fashion-MNIST and 
MNIST digit. For each dataset, we train three types of models(one clean and two backdoored). The two backdoored models have 
different triggers. 

Inside each repository we have the following main files
* Training: This file trains the dataset for the particular type of robust model (clean, localised backdoor 
or distributed bacdoor)
* Sanity Check: This file verifies the accuracy and attack success rate of the generated model
* Translate-Images: This file will pick random images from the dataset and translate (using first order methods) 
them for each label present in the dataset. These files will be then saved for further processing
* Feature-Rep-Extract: This file extracts the feature representation for the translated images and clean images 
for all labels in the dataset. 
* TSNE-Feature-Rep-Analysis: This file performs t-SNE on the feature representations to reveal the clusters in the
translated images, if any
* Mean Shift Images - All: This file tries to predict the actual number of clusers. Clusters more than three are considered
suspicious. We can then check images in the  to find if the trigger exists in the translated images.

Additionally, we also have the following folders: 
* models: This folder contains the models under test
* saved_pickles: This folder contains pickled files for the translated images, feature representations for clean and translated
images and the output of t-SNE on these feature representations.  

### Models
All the robust ML models can be found [here](https://drive.google.com/open?id=1-poTNo9cSmr_KPWfZvuGRbhmGh-SXZ87). These are 
divided into three folders representing three datasets, namely CIFAR10, Fashion-MNIST and MNIST. Each folder has a Clean, 
Distributed Backdoor and Localised Backdoor. The MD5 sum for these files can be found [here](https://docs.google.com/document/d/1y5-xWEh4WyDFYlNzI5naB2tUFnjHOXMwqYmV5hz3Ux4/edit?usp=sharing)



