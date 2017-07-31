# Digit-Recognizer
In this project I have implemented a deep convolutioal neural network for recognizing hand written digits using the MNIST dataset provided on Kaggle.This model has been implemented using TensorFlow, an open source software library for numerical computation using data flow graphs.

To train the model run the file Digit_Recognizer_train.ipynb, this will train the model and create a trained_params folder in the directory which can be used later to restore the wieghts.

To find the accuracy of the model on the local validation data run the file Digit_Recognizer_test.ipynb.

Running Digit_Recognizer_submission.ipynb will create a file 'submission.csv' which contains the prediction of the test data set provided on kaggle.This model scores 0.994 on the public leaderboard.

Run Digit_Recognizer_Visualize.ipynb to visualize output of filters across various layers.

Note-  These .ipynb files are are jupyter notebooks. To run them install jupyter.

# Requirements
* Python 3
* Tensorflow
* numpy
* scipy
* matplotlib
* pandas

# Dataset

The file train.csv contains pixel intensity values as flattened vectors for 42000 images and their corresponding labels. Similarly, test.csv has pixel intensity values for 28000 unlabelled images.

# Model
Model architecture has been explained in the code. To feed data in the graph queue runners have been used instead of placeholders. Reading data from queues increases the speed sinificatly since the GPU does not have to wait for data to be loaded by the CPU.Using queues increased the GPU utilization by ~7%, thus the CNN trained significatly faster. 

# TODO
* Set up an input pipeline: Instead of diretly loading the .csv file in as pandas dataframe, set up a a queue which directly reads from the file
* Data Augmentation: Create more training data from the existing by roating, cropping images.
