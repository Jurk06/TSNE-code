# PCA (Principal Component Analysis)
# https://sebastianraschka.com/Articles/2015_pca_in_3_steps.html
# https://www.kaggle.com/arthurtok/interactive-intro-to-dimensionality-reduction/comments
# https://distill.pub/2016/misread-tsne/
# Introduction
There already exists a plethora of notebooks discussing the merits of dimensionality reduction methods, in particular the Big 3 of PCA (Principal Component Analysis), LDA ( Linear Discriminant Analysis) and TSNE ( T-Distributed Stochastic Neighbour Embedding). Quite a handful of these have compared one to the other but few have gathered all 3 in one go. Therefore this notebook will aim to provide an introductory exposition on these 3 methods as well as to portray their visualisations interactively and hopefully more intuitively via the Plotly visualisation library. The chapters are structuredas follows:

*  Principal Component Analysis ( PCA ) - Unsupervised, linear method
*  Linear Discriminant Analysis (LDA) - Supervised, linear method
*  t-distributed Stochastic Neighbour Embedding (t-SNE) - Nonlinear, probabilistic method
# Curse of Dimensionality & Dimensionality Reduction
The term "Curse of Dimensionality" has been oft been thrown about, especially when PCA, LDA and TSNE is thrown into the mix. This phrase refers to how our perfectly good and reliable Machine Learning methods may suddenly perform badly when we are dealing in a very high-dimensional space. But what exactly do all these 3 acronyms do? They are essentially transformation methods used for dimensionality reduction. Therefore, if we are able to project our data from a higher-dimensional space to a lower one while keeping most of the relevant information, that would make life a lot easier for our learning methods.

# Pearson Correlation Plot
Since we are still having the problem that our dataset consists of a relatively large number of features (columns), it is perfect time to introduce Dimensionality Reduction methods. Before we start off, let's conduct some cleaning of the train data by saving the label feature and then removing it from the dataframe

# 1. Principal Component Analysis (PCA)
In a nutshell, PCA is a linear transformation algorithm that seeks to project the original features of our data onto a smaller set of features ( or subspace ) while still retaining most of the information. To do this the algorithm tries to find the most appropriate directions/angles ( which are the principal components ) that maximise the variance in the new subspace. Why maximise the variance though?

To answer the question, more context has to be given about the PCA method. One has to understand that the principal components are orthogonal to each other ( think right angle ). As such when generating the covariance matrix ( measure of how related 2 variables are to each other ) in our new subspace, the off-diagonal values of the covariance matrix will be zero and only the diagonals ( or eigenvalues) will be non-zero. It is these diagonal values that represent the variances of the principal components that we are talking about or information about the variability of our features.

Therefore when PCA seeks to maximise this variance, the method is trying to find directions ( principal components ) that contain the largest spread/subset of data points or information ( variance ) relative to all the data points present. For a brilliant and detailed description on this, check out this stackexchange thread

    *  Reduction from higher to lower dimension.
    *  Reducing the niose i.e. variance of the data
    *  Example
    *  reduction from 2d to 1d
    *  Mathematical Objective Function
    *  Finding the direction of spread of the data
    *  FInd the unit vector along the direction
    *  Find the projection of the dataset along the axis which we ll keep
    *  Replace the projection by their variance . {u^Txi}- variance formula
   
 # 2. Limitations of PCA
    There are following limitation of PCA
      * PCA is a linear algorithm. It will not be able to interpret complex polynomial relationship between features.
      * It is unable to retain the circular cluster. 
      * Any shape it converts that into a linear shape.
 # 3 what is tSNE?
     * t-Distributed Stochastic Neighbor Embedding (t-SNE) is an unsupervised, non-linear technique primarily used for data exploration and visualizing high-dimensional data. 
     * It helps to give a feel of how data are arranged in higher dimension to the lower dimesnion.
     * it preserves the local orientation of the data.
     * it is based on probability distributions with random walk on neighborhood graphs to find the structure within the data.
 
 # 4 Algorithm of tSNE
     * converting the high-dimensional Euclidean distances between data points into conditional probabilities that represent similarities.
     * In simple terms step 1 and step2 calculate the conditional probability of similarity between a pair of points in

         1 High dimensional space
         2 In low dimensional space
     * Process like this
  
 # 5 What does t-SNE actually do?
     * It’s quite simple actually, t-SNE a non-linear dimensionality reduction algorithm
     * It finds patterns in the data by identifying observed clusters based on similarity of data points with multiple features
     * But it is not a clustering algorithm it is a dimensionality reduction algorithm.
     * This is because it maps the multi-dimensional data to a lower dimensional space, the input features are no longer identifiable. 
     * Thus you cannot make any inference based only on the output of t-SNE. So essentially it is mainly a data exploration and visualization technique.
 
 
 
 
 
 
 
