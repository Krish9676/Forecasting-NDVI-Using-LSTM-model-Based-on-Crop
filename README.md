# Forecasting-NDVI-Using-LSTM-model-Based-on-Crop
Forecasting NDVI for Multiple crops Using LSTM model
This repository contains code for training a Long Short-Term Memory (LSTM) model to predict Normalized Difference Vegetation Index (NDVI) values based on historical NDVI sequences and crop information.

# Dataset
The dataset used for training the model is available in the file LSTM_Model_all_crops.csv. It contains NDVI values along with corresponding crop information for different fields and areas.

# Preprocessing
Shuffling Data: The dataset is shuffled to ensure randomness in the order of samples.
Interpolation: Missing NDVI values less than 0.1 are interpolated using neighboring values.
One-Hot Encoding: Crop names are one-hot encoded to represent categorical data numerically.
Input-Output Pair Generation: Sliding window approach is used to generate input-output pairs for training the model.
# Model Architecture
The model architecture consists of two branches:

# NDVI Sequence Processing Branch:

Multiple LSTM layers with dropout regularization for processing the historical NDVI sequence.
# Crop Information Processing Branch:

Dense layer for processing the one-hot encoded crop names.
These branches are merged and further processed with additional dense layers to predict future NDVI values.

# Training
The model is trained using Adam optimizer with Mean Squared Error (MSE) loss. Training is performed for 80 epochs with a batch size of 30.

# Evaluation
The trained model is evaluated on a validation set to assess its performance. Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE) are calculated to measure the prediction accuracy.
