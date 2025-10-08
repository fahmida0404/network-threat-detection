# Network Threat Detection with Optimized Machine Learning

## Overview

In the contemporary era of technology, the prevalence of cyber threats has increased significantly over time. Traditional Intrusion Detection Systems (IDS) are constrained to detect the evolving and sophisticated network attacks. Machine learning techniques ensure better predictive power by identifying deviation from established normal behavior instead of depending on known attack patterns. However, there are some limitations of the existing studies.

* Relying on outdated datasets that lack attack diversity.
* High false alarms due to the use of weak models and the presence of irrelevant features.
* Less reliable because of limited evaluation and potential for bias.

This threat detection system,

* Used a high-dimensional recent dataset (CSE-CIC-IDS2018) containing novel attacks compatible with the current threat situation.
* Applied the Information Gain feature selection technique.
* Cross-validated with hyperparameter tuning using machine learning models (Decision Tree, Naive Bayes, Logistic Regression, Random Forest and XGBoost).

The XGBoost model achieved an accuracy of 99.88%, 99.38% detection rate and only 0.02% of false alarms rate. Since it was the best one, the XGBoost model was evaluated on two popoular network datasets, the NSL-KDD and UNSW-NB15. ROC Curve is also plotted to show the relationship between the detection rate (TPR) and false alarms (FPR).

## Datasets

All the datasets are available in the [Google Drive Link](https://drive.google.com/drive/folders/1YmsZaMj-tOuJxUDM5kpVZFh8FftUt4SI?usp=sharing)

- **CIC-IDS-2018-Dataset.zip** 👉👉 It is the [CSE-CIC-IDS2018 on AWS](https://www.unb.ca/cic/datasets/ids-2018.html) dataset containing ten network data files of ten different days with seven distinct attacks (Brute-force, Heartbleed, Botnet, DoS, DDoS, Web attacks, and Infiltration).

- **CIC-IDS-2018.csv** 👉👉 Three files with DoS and DDoS attacks combined for the project.

- **CIC-IDS-2018(Preprocessed).csv** 👉👉 Cleaned & Preprocessed version of the selected dataset.

- **NSL-KDD.zip** 👉👉 Popular [NSL-KDD](https://www.unb.ca/cic/datasets/nsl.html) dataset having seperate train and test sets. kdd_train set was used in the project.

- **UNSW-NB15.zip** 👉👉 Testing set of another popular dataset, [UNSW-NB15](https://research.unsw.edu.au/projects/unsw-nb15-dataset) was used in the project.

## Notebooks 

The notebook directory contains the necessary google colab notebooks.

- **CSE_CIC_IDS_2018(Exploration).ipynb** 👉👉 Explored all the csv files of the _CIC-IDS-2018-Dataset.zip_ file except for the _Tuesday-20-02-2018_TrafficForML_CICFlowMeter.csv_ since it was too large and exceeded colab memory limit. Concatanated three files with comparatively more balanced attacks (DoS & DDoS).

- **CSE_CIC_IDS_2018(Preprocessing).ipynb** 👉👉 Preprocessed the selected dataset with cleaning, missing value handling etc. Attacks were combined as 'Malicious' for the binary classification task.

- **CSE_CIC_IDS_2018(FS+Classification).ipynb** 👉👉 Prepared data with label encoding, scaling and train-test splitting. Applied the Information Gain feature selection method and trained machine learning models on train set. Cross-validated the train set with hyperparameter tuning and evaluated the test set with the final model.

- **NSL-KDD.ipynb** 👉👉 Preprocessed, applied the IG feature selection and trained the XGBoost model on the _kdd_train.csv_ file of the NSL-KDD dataset.

- **UNSW-NB15.ipynb** 👉👉 Preprocessed, applied the IG feature selection and trained the XGBoost model on the _UNSW_NB15_testing-set.csv_ file.
