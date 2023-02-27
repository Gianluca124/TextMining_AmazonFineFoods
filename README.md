# Text classification and Text clustering on Amazon Fine Food Reviews dataset

## Table of contents
* [Abstract](#abstract)
* [Report](https://www.slideshare.net/GianlucaCavallaro3/text-mining-on-amazon-fine-foods-reviews)
* [Requirements](#requirements)
* [Pre-processing](#pre-processing)
* [Classification](#classification)
* [Clustering](#clustering)

## Abstract

In this project, different text mining techniques are applied to the Amazon Fine Food Reviews dataset. In particular, the tasks of text classification and text clustering are addressed. The main questions that are being investigated are:

1) Is it possible to classify the reviews as "good" or "bad"?
2) Is it possible to predict the score assigned to the review from the text of the review itself?
3) Is it possible to group similar reviews into the same cluster?

## Requirements

- python==3.8
- ipython
- ipykernel
- matplotlib
- pandas
- nltk
- gensim
- scikit-learn==1.2.0
- textblob
- yellowbrick


## Pre-processing

### Step 1. Download and extract the dataset

Download the dataset from the [official Kaggle Folder](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews).

### Step 2. Perform class splitting of the dataset
Perform all the necessary pre-processing steps using `Preprocessing.ipynb` notebook.


## Classification

In the `Classification.ipynb` notebook both binary and multi-class classification are performed. For both tasks several algorithm are proposed.


## Clustering

In the `Clustering.ipynb` notebook the clustering task is proposed via K-Means clustering and Agglomerative Clustering.


## Status

 Project is: ![##c5f015](https://via.placeholder.com/15/c5f015/000000?text=+)  _Done_


# Contributors

* [Gianluca Cavallaro](https://github.com/Gianluca124)  
* [Remo Marconzini](https://github.com/rmarconzini)
