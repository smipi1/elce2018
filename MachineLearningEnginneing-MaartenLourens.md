# A Pragmatic introduction to Machine Learning for Engineers - Maarten Lourens

## Introduction

### Talk takeaways

Talk takeaways:

1. Anyone can take ML for a spin
1. Deep math knowledge not required

Frameworks hide the underlying maths

Article that opened ML up for him:

> The Unreasonable Effectiveness of Recurrent Neural Networks - Andrej Karpathy

AlphaGo & Deepmind - Beginning of the Hype Cycle

Classical Machine Learning vs **Deep Learning**

What is Machine Learning?

> Learning from data

World hapiness report:

* Correlation between food availability and hapiness
* 85% correlation
* Different data sources
* Not causality

Was this machine learning?

* *Data science* produces *insights*
* *Machine learning* produces *predictions*
* *Artifical intelligence* produces *actions*

## The Problem

Logs:

* System log
* Wifi log

Example grepping a line from the log with small variations

This is a good example where machine learning can help

*Classification* is a *Supervised Machine Learning* problem

Supervising the process when it is learning by helping the learning system categorize

Training:

    [ Data ] --> [ Train ] --> [ Model ]

## The Solution

Python & Scikit-Learn

* Scikit is related to SciPy
** Organization allows dealing with API in predicatble manner
** Why not Tensorflow? These are for deep learning and leveraging GPUs

Code example,,,

* Imports
* Copy data to prevent dynamic updates of logs while you are processing (repeatablity)
* Read the data
** Panadas: Helps to standardize your data
** `read_csv`
** Plugging data into `data` column
** Reserving `type` column for learning output
* Train
** Split data into training and testing data
** `train_test_split`: In example chose test size = 0.2
** Conventions: x: input, y: training outputs
** CountVectorizer(): Generates tokens (vocabulary) for training
** TfidfTransformer(): Indicates importance of tokens (vocabulary) in data
** Data prep
** Uses method `fit()`
** `for algorithm in algorithms`: Use a list of algorithms to find best fit
* Report

Metrics used in predicting:
* True & False Positives
* True & False Negatives
* Accuracy, Recall, Precision, F1 Score

What have I learned:

1. Get to know your **data**
1. Understand your **algorithm**

https://github.com/automationlogic/log-analyzer

