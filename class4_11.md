# JupyterLab
__**Overview**__

![](https://jupyterlab.readthedocs.io/en/stable/_images/interface_jupyterlab.png)

__JupyterLab enables you to work with documents and activities such as Jupyter notebooks, text editors, terminals, and custom components in a flexible, integrated, and extensible manner. For a demonstration of JupyterLab and its features,.__

## Three components of Jupyter Notebook

* The web application: This provides an interactive interface to write and run the program as well as to authorize documents.
* Notebook documents: There are various documents which restrain a demonstration of a range of content that is perceptible through the notebook web application, and each of these documents get managed by their kernel.
* 

    Kernels: It can run different processes as well as execute different codes written in a given language and returns the compiled result to notebook web-application. It also manages the handling of computations of data related to widgets and graphs that are interactive.

## Data Analysis with Python

**NumPy**

NumPy is a commonly used Python data analysis package. By using NumPy, you can speed up your workflow, and interface with other packages in the Python ecosystem, like scikit-learn, that use NumPy under the hood. NumPy was originally developed in the mid 2000s, and arose from an even older package called Numeric. This longevity means that almost every data analysis or machine learning package for Python leverages NumPy in some way.

__The data was downloaded from the UCI Machine Learning Repository, and is available here. Here are the first few rows of the winequality-red.csv file, which we’ll be using throughout this tutorial:__

    "fixed acidity";"volatile acidity";"citric acid";"residual sugar";"chlorides";"free sulfur dioxide";"total sulfur dioxide";"density";"pH";"sulphates";"alcohol";"quality"
    7.4;0.7;0;1.9;0.076;11;34;0.9978;3.51;0.56;9.4;5
    7.8;0.88;0;2.6;0.098;25;67;0.9968;3.2;0.68;9.8;5

### Lists Of Lists for CSV Data

Before using NumPy, we’ll first try to work with the data using Python and the csv package. We can read in the file using the csv.reader object, which will allow us to read in and split up all the content from the ssv file.

**In the below code, we:**

* Import the csv library.
* Open the winequality-red.csv file. 
    * With the file open, create a new csv.reader object. 
        * 
    Pass in the keyword argument delimiter=”;” to make sure that the records are split up on the semicolon character instead of the default comma character.

    * Call the list type to get all the rows from the file.
    * Assign the result to wines.

### Numpy 2-Dimensional Arrays

With NumPy, we work with multidimensional arrays. We’ll dive into all of the possible types of multidimensional arrays later on, but for now, we’ll focus on 2-dimensional arrays. A 

Now that you understand the basics of matrices, let’s see how we can get from our list of lists to a NumPy array.

### Alternative NumPy Array Creation Methods

There are a variety of methods that you can use to create NumPy arrays. To start with, you can create an array where every element is zero. The below code will create an array with 3 rows and 4 columns, where every element is 0, using numpy.zeros:

    import numpy as np
    empty_array = np.zeros((3,4))

    empty_array
### Using NumPy To Read In Files

It’s possible to use NumPy to directly read csv or other files into arrays. We can do this using the numpy.genfromtxt function. We can use it to read in our initial data on red wines.