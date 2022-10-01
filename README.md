# Solution by Connor Delaplane and Jea-Woo Park to the 2022 ACM/IEEE TinyML Contest

## Contents

model_final
- Directory containing model_1.onnx, the final trained model.

py_scripts
- Directory containing code used to train and test the model.

STM_code
- Directory containing STM project for final evaluation.
- NOTE: This has a custom main.c file that does data transformations; don't overwrite it!

requirements.txt
- Required python dependencies.

## How to train a new model

Run training_save_deep_models.py with the following arguments:

--epoch (int, default=10)
The number of epochs to run for.

--lr (float, default=0.001)
The learning rate to use.

--batchsz (int, default=16)
The batch size to use.

--size (int, default=1250)
The number of features per sample.

--path_data (str, default='./training_data/') 
Path to the training data.

--path_indices (str, default='./data_indices/') 
Path to the training data indices.

--path_net (str, default='./saved_models/')
Path to which the new model will be saved.

--acc_min (float, default=0.95)
If the final model does not achieve the desired accuracy on the test data, training will restart.

## How to test a newly-trained model

Run testing_performances.py with the following arguments:

--size (int, default=1250)
The number of features per sample.

--path_data (str, default='./training_data/') 
Path to the training data.

--path_indices (str, default='./data_indices/') 
Path to the training data indices.

--path_net (str, default='./saved_models/')
Path to the model to load.

--path_record (str, default='./records/') 
Path to save the output seg_stat.txt file.

## Validation

Our CubeMX project is included in STM_cube/test_eval.  We have a custom main.c file in the Src directory that performs the necessary data transformation for our model to work properly.  It should not be overwritten!

