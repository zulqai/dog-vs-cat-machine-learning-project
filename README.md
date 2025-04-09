# dog-vs-cat-machine-learning-project
Dog Vs Cat Prediction In Machine Learning
<br>
Author - Zulqarnain Jabbar (@zulqai)

Hi everyone, it is my first machine learning project, and i enjoy a lot while building it, heres what i have done step by step

import random
import numpy as np
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Conv2D, MaxPooling2D, Dense, Flatten
import matplotlib.pyplot as plt

random: Helps with randomness (like shuffling data).
numpy (as np): A library that makes working with numerical data easy.
Sequential from TensorFlow Keras: Allows stacking layers of a neural network in a simple sequence.
Conv2D, MaxPooling2D, Dense, Flatten: Building blocks of the neural network that help identify patterns in images.
Conv2D: Detects visual patterns (edges, shapes, textures).
MaxPooling2D: Reduces the size of images to focus on the important parts.
Dense: Fully-connected layer, makes predictions based on the extracted features.
Flatten: Converts the multidimensional data into a one-dimensional vector.
matplotlib.pyplot (as plt): Used to visualize results with graphs or images.


X_train = np.loadtxt('input.csv', delimiter = ',')
Y_train = np.loadtxt('labels.csv', delimiter = ',')

X_test = np.loadtxt('input_test.csv', delimiter = ',')
Y_test = np.loadtxt('labels_test.csv', delimiter = ',')


X_train and Y_train: Load training data (images) and labels (0 for cats, 1 for dogs) from CSV files.

X_test and Y_test: Load separate test data to evaluate how well your model learns from the training data.



X_train = X_train.reshape(len(X_train), 100, 100, 3)
Y_train = Y_train.reshape(len(Y_train), 1)

X_test = X_test.reshape(len(X_test), 100, 100, 3)
Y_test = Y_test.reshape(len(Y_test), 1)

# Normalizing our data set between 0 and 1
X_train = X_train/255
X_test = X_test/255


Reshaping data: Converts each flat array of pixels into a structured image (100x100 pixels, 3 color channels—Red, Green, Blue).

Reshaping labels (Y_train, Y_test): Ensures labels are in the correct shape for the model.

Normalization: Divides pixel values by 255 (maximum pixel value) to scale the data between 0 and 1, improving model efficiency.


print("Shape of X_train: ", X_train.shape )
print("Shape of Y_train: ", Y_train.shape)

print("Shape of X_test: ", X_test.shape)
print("Shape of Y_test: ", Y_test.shape)


Confirms data is reshaped correctly. The output should look like:

(number_of_images, 100, 100, 3) for images.

(number_of_images, 1) for labels.

X_train[1,:]

Displays raw numerical pixel values of the second training image, primarily used for a quick manual check or debugging.
