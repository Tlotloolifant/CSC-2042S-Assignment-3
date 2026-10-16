CSC2042S Assignment 3: Neural Networks

Optimisation of a neural network for image classification on Fashion MNIST data set .


Purpose:

Loads Fashion-MNIST and splits the 60,000 training images into 50,000 for training and 10,000 for validation.
Builds a baseline MLP 784 into 128 ReLU into 64 ReLU outputting 10 and trains it with SGD (lr 0.01) for 10 epochs.
Runs a grid experiment over three hyperparameters (12 runs):
learning rate: 0.001, 0.01, 0.1
optimiser: SGD, Adam
dropout: 0.0, 0.3
Analyses the results with a table, a bar chart, loss curves (baseline vs best model), a confusion matrix, and written answers.


Files

CSC2042S_Assignment3_NeuralNetworks_2026.ipynb	notebook with code and plots
data/FashionMNIST/raw/	relevant data files
README.md	This file

Requirements
Python 3.9 or newer
torch, torchvision, numpy, pandas, matplotlib, jupyter
adequate laptop to be honest (took 35 min to run 12 epochs on mine)


Note on data

The notebook loads the data with datasets.FashionMNIST(root="./data", download=True).

If data/FashionMNIST/raw/ is present next to the notebook, the local files are used and nothing is downloaded.
If it is missing, torchvision downloads the dataset automatically .

Run the notebook from the folder that contains it, so that ./data points to the right place.

Results summary
Model	Settings	Validation accuracy
Baseline	SGD, lr 0.01, dropout 0.0	0.8586
Best model	Adam, lr 0.001, dropout 0.0	0.8870

The best model improves on the baseline by 2.84 percentage points. The most common errors are between visually similar classes (Shirt vs T-shirt/top, Pullover vs Coat). The full table, plots and written analysis are in NN report.

Notes
All random seeds are fixed (seed 42), so results should be repeatable on the same setup. 
