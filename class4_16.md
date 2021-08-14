# Machine Learning ≠ Algorithms

First, we must clear up one of the biggest misconceptions about machine learning:

Machine learning is not about algorithms.

When you open a textbook or a university syllabus, you'll often be greeted by a grocery list of algorithms.

## What makes machine learning so special?



Machine learning is the practice of teaching computers how to learn patterns from data, often for making decisions or predictions.

For true machine learning, the computer must be able to learn patterns that it's not explicitly programmed to identify.


### Machine Learning Tasks

Academic machine learning starts with and focuses on individual algorithms. However, in applied machine learning, you should first pick the right machine learning *task for the job.

* A task is a specific objective for your algorithms.
* Algorithms can be swapped in and out, as long as you pick the right task.
* In fact, you should always try multiple algorithms because you most likely won't know which one will perform best for your dataset.


# Exploratory Analysis

## Why explore your dataset upfront?



The purpose of exploratory analysis is to "get to know" the dataset. Doing so upfront will make the rest of the project much smoother, in 3 main ways:

1. You’ll gain valuable hints for Data Cleaning (which can make or break your models).
2. You’ll think of ideas for Feature Engineering (which can take your models from good to great).
3. You’ll get a "feel" for the dataset, which will help you communicate results and deliver greater impact.

### Start with Basics

First, you'll want to answer a set of basic questions about the dataset:

* How many observations do I have?
* How many features?
* What are the data types of my features? Are they numeric? Categorical?
*  Do I have a target variable?

![](https://elitedatascience.com/wp-content/uploads/2017/06/Organic-Detector.png)


# Data Cleaning

## Better Data > Fancier Algorithms

Data cleaning is one those things that everyone does but no one really talks about. Sure, it’s not the "sexiest" part of machine learning. And no, there aren’t hidden tricks and secrets to uncover.

However, proper data cleaning can make or break your project. Professional data scientists usually spend a very large portion of their time on this step.

### Remove Unwanted observations

The first step to data cleaning is removing unwanted observations from your dataset.

This includes duplicate or irrelevant observations.

__Duplicate observations__

Duplicate observations most frequently arise during data collection, such as when you:
* Combine datasets from multiple places
* Scrape data
* Receive data from clients/other departments


__Irrelevant observations__

Irrelevant observations are those that don’t actually fit the specific problem that you’re trying to solve.
* For example, if you were building a model for Single-Family homes only, you wouldn't want observations for Apartments in there.
* This is also a great time to review your charts from Exploratory Analysis. You can look at the distribution charts for categorical features to see if there are any classes that shouldn’t be there.
* Checking for irrelevant observations before engineering features can save you many headaches down the road.