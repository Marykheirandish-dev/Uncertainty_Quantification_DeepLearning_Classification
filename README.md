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

Replace all occurrences of "data.csv" in the R Markdown file with the actual dataset name (e.g., "Data_sep01_feature4_flip001.csv").

Set n_features based on the number of features in the file name (e.g., n_features = 4 for feature4).

Run the R Markdown file to compute uncertainties.

Example Code Replacement
Replace:

set.seed(1369)
n_features = 4
data <- read.csv("data.csv", header = FALSE)
if(n_features == 4) {
  colnames(data) <- c("X1", "X2", "X3", "X4", "y")
} else if(n_features == 5) {
  colnames(data) <- c("X1", "X2", "X3", "X4", "X5", "y")
} else if(n_features == 7) {
  colnames(data) <- c("X1", "X2", "X3", "X4", "X5", "X6", "X7", "y")
} else if(n_features == 10) {
  colnames(data) <- c("X1", "X2", "X3", "X4", "X5", "X6", "X7", "X8", "X9", "X10", "y")
}

With:


set.seed(1369)
n_features = 4
data <- read.csv("Data_sep01_feature4_flip001.csv", header = FALSE)
if(n_features == 4) {
  colnames(data) <- c("X1", "X2", "X3", "X4", "y")
} else if(n_features == 5) {
  colnames(data) <- c("X1", "X2", "X3", "X4", "X5", "y")
} else if(n_features == 7) {
  colnames(data) <- c("X1", "X2", "X3", "X4", "X5", "X6", "X7", "y")
} else if(n_features == 10) {
  colnames(data) <- c("X1", "X2", "X3", "X4", "X5", "X6", "X7", "X8", "X9", "X10", "y")
}
