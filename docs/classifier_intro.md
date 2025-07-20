# Classifier Introduction

This classifier is created and trained by RandomForestClassifier. This section is split into 2 separate files:

## [create_model.ipynb](../living-dead/classifier/create_model.ipynb)
This file creates and trains a classifier model that you can later use on any video of similar data to the training data. To use this file, first create a separate .xlsx file that includes a data table with the columns 'particle' and 'dead/alive (0/1)' to use in this program. The program will generate a Pandas dataframe with calculated values for the diagonal size of a trajectory ('diagonal size'), the scaling exponent of the mean squared displacement ('msd power'), and the straightness of the trajectory, which is calculated with the diagonal size divided by the path length of the trajectory ('straightness').  These values and the trajectories are all  calculated from trackpy. The program then combines this dataframe with the imported .xlsx file of the labelled training data. From here, the classifier can then be trained according to this dataset. There are several other parameters that can control how the data is used in the training process. The model can then be saved to a name of your choosing. Some already created models are located in the models section of this repo.

## [classify.ipynb](../living-dead/classifier/classify.ipynb)
This file imports a classifier model and uses it to predict whether particles are alive or dead. A plot is created with the living trajectories in blue and the dead trajectories in red. There are options to save this into separate csv files for living and dead trajectories.
