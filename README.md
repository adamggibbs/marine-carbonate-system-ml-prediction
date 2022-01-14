# Neural Network Development Framework for Oceanographic Applications

*Disclaimer: This GitHub page is currently being updated. Code is still to be added.*

## Description
The objective of this project is to extend on the work of Bitting et al (2018) which developed a neural network to estimate parameters of the marine carbonate system from date, location, temperature, pressure, salinity, and oxygen. We sought to develop a framework that allowed us to train a neural network to estimate these parameters with less error than the global algorithm produced by Bittig et al. Here we've developed a framework that any researcher to develop a neural network that estimates a specified target variable from specified target inputs given data from standardized data files. The overall motivation is to make the benefits of machine learning accessible to researchers studying ocean chemistry. 

## Table of Contents
1. [Files in the Repository](#files-in-the-repository)
2. [Getting Started - Setting Up](#getting-started---setting-up)
3. [Quick Start - Training](#quick-start---training)
4. [Quick Start - Making Estimations](#quick-start---making-estimations)

## Files in the Repository
- **NN_Development_Framework.ipynb**
  - This is the main file of the repository. This file reads in training data, trains a model with specified inputs and outputs, and evaluates the model on given testing data.
  - More thorough README given with development_README.md
- **Model_Estimations.ipynb**
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
5. The directory structure should be set up. Check your Google Drive to confirm. If the notebook does not work or throws an error, see the [Troubleshooting](#troubleshooting) section for help.

#### Troubleshooting  
If any error occurs, first try restarting the runtime by navigating to the toolbar and selecting `Runtime -> Factory reset runtime`. If this does not work, make sure you properly typed in the path to the desired directory location in `root_dir_path`. If neither of these helps, then manually create the file structure using the picture below as reference.  

#### Example
For example, if you have an existing directory **Research** and want a subdirectory named **pH Estimation Framework** to store your files in, then in  you will define 
```
root_dir_path = 'Research/pH Estimation Framework'
``` 
and then run the notebook by navigating to the toolbar and selecting `Runtime -> Run all` or using `ctrl+F9`.

## Quick Start - Training

## Quick Start - Making Estimations
