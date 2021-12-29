# Neural Network Development Framework for Oceanographic Applications

*Disclaimer: This GitHub page is currently being updated. Code is still to be added.*

## Description
The objective of this project is to extend on the work of Bitting et al (2018) which developed a neural network to estimate parameters of the marine carbonate system from date, location, temperature, pressure, salinity, and oxygen. We sought to develop a framework that allowed us to train a neural network to estimate these parameters with less error than the global algorithm produced by Bittig et al. Here we've developed a framework that any researcher to develop a neural network that estimates a specified target variable from specified target inputs given data from standardized data files. The overall motivation is to make the benefits of machine learning accessible to researchers studying ocean chemistry. 

## Files in the Repository
- NN_Development_Framework.ipynb
  - This is the main file of the repository. This file reads in training data, trains a model with specified inputs and outputs, and evaluates the model on given testing data.
  - More thorough README given with development_README.md
- directory_setup.ipynb
  - The framework requires a specific directory structure to store data, models, and figures. This notebook sets up that directory structure at a specified location in your Google Drive.
- data_quality_control.ipynb
  - This notebook will perform quality control checks on certain parameters as specified in the data_qc_README.md. This file performs quality checks on data placed in the quality_check directory and the output files can be placed in the training or testing directories to be used in developing a new model.
- Segmented Files Directory
  - This directory contains the individual Google Colab notebooks that were combined to make the larger notebook - NN_Development_Framework.ipynb.   
