Data Description: 

Dataset contains images of letters in devanagari script with train and test, a total of 46 Classes including digits in devanagari script (0,1,2,…9) 

Train-size: 78200 images with each 32x32x3 Pixels

Test-size: 13800 images with each 32x32x3 Pixels

Test and Train data are in two different folders, each containing 46 different folders with Class Names as their folder names.

Data preprocessing:
OpenCV (image processing library) was used to read the images and for writing them into dataset.hdf5 along with their appropriate labels.

Two HDF5 files dataset.hdf5 and datasettest.hdf5 are created for Train and Test data along with their respective labels in PC.

Using HDF5 file over numpy arrays for loading the training data into the model has performance benefits as HDF5 is stored in ROM and as such has performance benefits and can avoid memory problems.

Hence, all the images are converted and stored in .HDF5 format. Since HDF5 compresses the data while converting, it is easy to handle and upload for any cloud processing platform.  Model was trained in Google colab by calling this file from Google drive.

Git-Hub: https://github.com/bharath000/devanagri12/blob/master/Devanagari_pre.ipynb

Building the Model:

The two HDF5 files created in data preprocessing are uploaded into Google-drive. From here we can extract the images by reading the above file into numpy arrays in Google-colab. 

Model description and accuracy scores:

Created a CNN model using Keras with 4 CNN layers with increasing number of filters and kernel of size 3x3,

Down-sampling for every 2 every layers, activation LeakyReLu, and a dense layer with 256 neurons, 10 neurons before the softmax activation in final layer, Adding Dropout after down-sampling (2x2).

This model was trained using AdamMax optimizer with exponentially decreasing learning rate (alpha) over different epochs. Accuracy score was used as performance metric. Cross-Entropy was used as loss function.

Gti-hub: https://github.com/bharath000/devanagri12/blob/master/devnagari%20(1).ipynb

