Project Overview
This repository contains code and data for simulating classification datasets and analyzing predictive uncertainty using ensemble models in R.
Folder Structure
Data/
This folder contains all the simulated datasets. The data are generated using the Python function sklearn.datasets.make_classification.

File names follow this convention: Data_sep<sep_value>_feature<n_features>_flip<flip_y>[optional_suffix].csv
Examples:
Data_sep01_feature4_flip001.csv:
sep (class separation) = 0.1
n_features (number of features) = 4
flip_y (label noise) = 0.01

Data_sep01_feature4_flip001_imbalanced.csv:
Same as above, but the dataset is imbalanced — one class contains 90% of the data points.
If the filename does not end in _imbalanced.csv, the data are balanced between the two classes.

Running the R Code
The file Define and train - Ensemble - synthetic copy.Rmd contains the complete workflow for training ensemble models and calculating uncertainty.

Instructions
Choose a dataset from the Data/ folder.

In .RMD:
  Set FILE_PATH as the name of .csv file.
  Set n_features based on the number of features in the file name (e.g., n_features = 4 for feature4).
  Set OUTPUT_FILE_NAME as the name of output file (In our project, if input = data.csv, output is name data_test_pred_50ensemble.csv)
Run the R Markdown file to compute uncertainties and p-values.
