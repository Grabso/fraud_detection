# Fraud detection
Detecting Fraud Transactions by numerous Machine Learning technics in Python.

About this project:

The whole point of this notebook is to try catch up autoencoder representation of fraud transaction and compared the result of models which was learned on this prepared data by this algorithm with models fed by original data. We expect dimensionality reduction with the same or with the better results. The notebook consist:

* Data analysis
* Undersampling
* PCA and TSNE
* Two Autoencoders Architectures
* Supervised algorithm: Logistic Regression, Random Forrest, SVM and XGBoost

Since this is a complex dataset, the following analyzes will be performed in the future:

* Outlier detection
* Oversampling

**We will measure the performance mainly by AUROC and AUPRC**

# Data Information:
https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

The dataset contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-sensitive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

# Summary of results:

There are almost no diffrences in performence between Undersampled Machine Learning and data prepared by Sparse Autoencoder.

What is more, there is signifant change in features which comes into model: 30 against 16. We could try to make features selection for original Data Frame. However the strongest part of Autoencoder is that, it will do it for us with respect of the all valuable information from each features will be saved by it for the best performance.

Even though we doesn't aquiare better result for it, we obtain quicker algorith which could be beneficial for bigger Data Frame (milions of bank transactions per year) and to tune algorithm, which is fed by data prepared by Autoencoder - as we obtain a lot of copmutational power. For instance, evaluation of Cross Validation is on average 2 times quicker for Autoencoder dataset.
