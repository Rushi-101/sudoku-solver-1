The updated problem statement for this assignment can be found at https://github.com/LS-Computer-Vision/sudoku-solver-1

# Sudoku Solver - 1

We will use a combination of OpenCV and Deep Learning to build a Sudoku generator and solver

This is the first part of the assignment, where we will explore how to build the ML model required for the next part

## Resources to get you started

There are several resources to get started with Machine Learning

* [Linear Regression](https://towardsdatascience.com/linear-regression-from-scratch-cd0dee067f72)
* [Series on Neural Networks & Deep Learning](http://neuralnetworksanddeeplearning.com/index.html) (best introduction to ML you can have)
	* This series deals with how to build neural networks from scratch, but we will not be doing so. We will use an ML library to do the hard mathematics for us
* [Pytorch tutorials](https://pytorch.org/tutorials/)
* [Keras Tutorials](https://keras.io/guides/)
* [Tensorflow Tutorials](https://www.tensorflow.org/tutorials)

## Part 0: Setup

Open up your terminal and execute the following commands:

	pip install virtualenv
	python -m virtualenv venv
	venv/Scripts/activate      # For Windows Users
	source venv/bin/activate   # For OSX/Linux Users
	pip install -r requirements.txt
	
You will also need to install the corresponding ML library, the instructions for the same are present in the respective websites (look for the installation commands which use ```pip```)

I recommend ```PyTorch``` if you are starting out

Once you have installed the ML library of your choice, update your requirements.txt

	pip freeze > requirements.txt
	

## Part 1: Training the Model
We will be building a digit classifer which takes as input a ```28x28``` image of a handwritten digit, and outputs the predicted value of which digit it is

The dataset we will use is the **MNIST** dataset, a collection of ```60000``` training images (and labels) and ```10000``` test images (and labels). The training data is loaded as a ```numpy``` array of shape ```(60000,784)```, where each row is a vector of ```784``` elements, which is basically the ```28x28``` pixel values flattened out. The pixel values lie between ```0-255```, ```0``` being black and ```255``` being white

Take a note of the fact that you may have to preproces this dataset in order to feed it into your model, eg you may wish to divide by ```255``` to bring the values between ```0-1```, or normalize the data, or convert it into images (```28x28``` array instead of ```784``` array) if you are using a CNN

Now the ML library is yours to choose, and so is the model. For people starting out with ML I recommend the ```PyTorch``` library and a simple **Neural Network** as your model. For more advanced students, you can consider CNN's and other networks

```dataLoader.py``` contains the code to load the data, and ```model.py	``` is the file you will be editing, which will contain the code to train the model and make predictions

For beginners, much of the boilerplate has already been written out, and all you have to do is to edit the pieces of code between ```#Start Editing``` and ```#End Editing``` comments.

If you are familiar with ML libraries already, feel free to make edits to other parts of the code if it helps you build a better model. (Don't do stuff like make the ```test()``` function always return 100% accuracy 😁)

Regardless of whether you are familiar with ML or not, I recommend you to fiddle around with the hyperparameters like learning rate, batch size, number of epochs. You will find that there is a huge difference in accuracy between the optimal and sub-optimal hyperparameters.

You can even try setting up a grid search for the optimal hyperparameters if you feel courageous enough.

I also recommend that if you are already done with the exercise, you can try doing a simple **train-validation** split and find the validation error in each epoch. With this you can verify that overfitting is not happening, and you can also save only the model trained by the epoch which generated least validation error. You can also try [**k-fold cross validation**](https://machinelearningmastery.com/k-fold-cross-validation/) for better evaluation of your model

## Part 2: Analysis

Analyse the results that you get. Make some charts about how your test accuracy varies with hyperparameters chosen to train, how the train/validation loss varies with epochs etc.

This is where you apply the analytical part of your brain, and fiddle around with your model (you can even try different models and compare their results) in order to achieve the best results possible

Write down your conclusions (and include the charts/graphs) in ```explanation.pdf```

## Submission Instructions

Your assignment repository (https://github.com/LS-Computer-Vision/sudoku-solver-1-{username}) should have the following contents pushed to it.
You need a minimum of 90% accuracy to past the automated tests

	repository root
	├── assets
	│   ├── all the data files
	│   └── model
	├── .gitignore
	├── README.md
	├── requirements.txt
	├── dataLoader.py
	├── model.py
	├── test_model.py (don't touch this)
	└── (Not pushed, ignored by git) venv

## Deadline
The deadline for this assignment is kept at 29 July 11:59 PM