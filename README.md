# Neural Network Development Framework for Oceanographic Applications

*Disclaimer: This GitHub page is currently being updated. Code is still to be added.*

## Description
The objective of this project is to extend on the work of Bitting et al (2018) which developed a neural network to estimate parameters of the marine carbonate system from date, location, temperature, pressure, salinity, and oxygen. We sought to develop a framework that allowed us to train a neural network to estimate these parameters with less error than the global algorithm produced by Bittig et al. Here we've developed a framework that any researcher to develop a neural network that estimates a specified target variable from specified target inputs given data from standardized data files. The overall motivation is to make the benefits of machine learning accessible to researchers studying ocean chemistry. 

## Table of Contents
1. [Files in the Repository](#files-in-the-repository)
2. [Data](#data)
3. [Getting Started - Setting Up](#getting-started---setting-up)
4. [Quick Start - Training](#quick-start---training)
5. [Quick Start - Making Estimations](#quick-start---making-estimations)

## Files in the Repository
- **NN_development_framework.ipynb**
  - This is the main file of the repository. This file reads in training data, trains a model with specified inputs and outputs, and evaluates the model on given testing data.
  - More thorough README given with development_README.md
- **model_estimations.ipynb**
  - This file uses an already trained neural network (specified by the user) to add estimations to existing data files. The notebook will add a column to the existing data files with estimations for the specified output variable and save the new data file as a different file.  
- **directory_setup.ipynb**
  - The framework requires a specific directory structure to store data, models, and figures. This notebook sets up that directory structure at a specified location in your Google Drive.
- **data_quality_control.ipynb**
  - This notebook will perform quality control checks on certain parameters as specified in the data_qc_README.md. This file performs quality checks on data placed in the quality_check directory and the output files can be placed in the training or testing directories to be used in developing a new model.
- **Segmented Files Directory**
  - This directory contains the individual Google Colab notebooks that were combined to make the larger notebook - NN_Development_Framework.ipynb.   


## Getting Started - Setting Up
To run these notebooks a specific file structure is necessary. The directory_setup.ipynb notebook can be run to set up the exact structure necessary in your Google Drive to run the rest of the files. 

#### Instructions
These following steps will help you set up the necessary directory structure to train your own neural network using our framework. This notebook can be run as it is written when downloaded off GitHub with an example location presently hardcoded in. Also see this [example](#example) on how to use this notebook.
1. Go to your Google Drive and decide where you want all the files to be stored
2. Store the path to that folder location in the variable **root_dir_path**.
  * This path begins from the My Drive section of your Google Drive. **root_dir_path** gets appended to the end 'content/drive/My Drive/' 
  * Do not include leading and traing "/". For example, '/example/test/' will throw an error, but 'example/test' is acceptable
3. Run this notebook by navigating to the toolbar and selecting `Runtime -> Run all` or using `ctrl+F9`
4. When prompted, allow access to your Google Drive account by selecting **Connect to Google Drive**, then clicking on the Google Drive account you wish to use, and finally selecting **Continue** to finalize access.
  * This allows only this specific Google Colab notebook to access your Google Drive files and will disconnect when the notebook is closed or a certain amount of idle time has passed.
5. The directory structure should be set up. Check your Google Drive to confirm. If the notebook does not work or throws an error, see the [Troubleshooting](#troubleshooting---directory-setup) section for help.

#### Troubleshooting - Directory Setup
If any error occurs, first try restarting the runtime by navigating to the toolbar and selecting `Runtime -> Factory reset runtime`. If this does not work, make sure you properly typed in the path to the desired directory location in `root_dir_path`. If neither of these helps, then manually create the file structure using the picture below as reference.  

#### Example
For example, if you have an existing directory **Research** and want a subdirectory named **pH Estimation Framework** to store your files in, then in  you will define 
```
root_dir_path = 'Research/pH Estimation Framework'
``` 
and then run the notebook by navigating to the toolbar and selecting `Runtime -> Run all` or using `ctrl+F9`.


## Data


## Quick Start - Training 
To train a neural for a desired estimation task, the [NN_development_framework.ipynb](https://github.com/adamggibbs/marine-carbonate-system-ml-prediction/blob/master/NN_development_framework.ipynb) notebook is used. This notebook contains a framework to train and test a neural network to estimate any ocean parameter from other specified ocean parameters given a data file in a standard oceanographic format referenced throughout these instructions (see the [data section](https://github.com/adamggibbs/marine-carbonate-system-ml-prediction/blob/master/README.md#data) for more info). The data used must be in the specified format and quality checked prior to using this notebook. Quick start intructions are below and more detailed instructions can be found in the development_README.md file within the [GitHub repository](https://github.com/adamggibbs/marine-carbonate-system-ml-prediction). 

## Instructions
**Before using this notebook:**

1. Choose a location within your Google Drive to store all data and models
2. Run the [directory_setup.ipynb](https://github.com/adamggibbs/marine-carbonate-system-ml-prediction/blob/master/directory_setup.ipynb) Colab notebook to create the necessary directory structure for this notebook to run.
3. Place all training files you want to use for training in the `training` directory found under your `root` directory.
```
/My Drive/root_dir/data/training/
```
4. Place all training files you want to use for training in the `testing` directory found under your `root` directory.
```
/My Drive/root_dir/data/testing/
```
> **Note:** Training and testing files should be independent such that any data in the testing files should not be in the training files. 

**Before running this notebook:**

5.   Define all necessary user defined variables.
> **Note:** More details on the necessary user defined variables are in the cell below in this notebook and in [development_README.md](https://github.com/adamggibbs/marine-carbonate-system-ml-prediction/blob/master/development_README.md) in the [GitHub repository](https://github.com/adamggibbs/marine-carbonate-system-ml-prediction).
6.   Define any optional user defined variables.
> **Note:** More details on optional user defined variables in [development_README.md](https://github.com/adamggibbs/marine-carbonate-system-ml-prediction/blob/master/development_README.md) in the [GitHub repository](https://github.com/adamggibbs/marine-carbonate-system-ml-prediction).

**Running this notebook:**

> **Note:** Ensure all necessary user defined variables are properly defined and data files in the proper format are uploaded in the training and testing directories

7. Run this notebook by navigating to the toolbar and selecting `Runtime -> Run all` or using `ctrl+F9`
8. When prompted, allow access to your Google Drive account by selecting **Connect to Google Drive**, then clicking on the Google Drive account you wish to use, and finally selecting **Continue** to finalize access.
> This allows only this specific Google Colab notebook to access your Google Drive files and will disconnect when the notebook is closed or a certain amount of idle time has passed.
9. The model should be trained and saved in the `models` directory under two different file formats: the standard tensorflow data format (which should be a non-empty directory) and HDF5 format (`.h5` file extension). 
```
#tensorflow data format
/My Drive/root_dir/models/model_name_Layers(...)/ 
# HDF5 data format
/My Drive/root_dir/models/model_name_Layers(...).h5
```
Check your Google Drive to confirm. If the notebook does not work or throws an error, see the [Troubleshooting](#troubleshooting---training) section for help.
> **Note:** Depending on the size of training and testing files and size of the neural network, this notebook can take over **1 hour to run and fully complete**. You can ensure progress is being made by following the logs produced by each cell in the notebook and the status bar at the bottom of the notebook. 
10. Check the performance of the neural network by analyzing the error metrics and figures in the notebook. Reference the [development_README.md](https://github.com/adamggibbs/marine-carbonate-system-ml-prediction/blob/master/development_README.md) file for mroe information on training a good model. Repeat preceding steps until you have a model with satisfactory performance before proceeding to step 11. 
11. Your model is now ready to use. To use the model to make estimations for your output variable with any data file file, use the [model_estimations.ipynb](https://github.com/adamggibbs/marine-carbonate-system-ml-prediction/blob/master/model_estimations.ipynb) notebook. This notebook will allow you to make estimations using any model you've trained on any data file in the specified format and add those estimations as a column to the data file. 

#### Troubleshooting-Training
If any error occurs, first try restarting the runtime by navigating to the toolbar and selecting `Runtime -> Factory reset runtime`. More info to be added...

## Quick Start - Making Estimations

