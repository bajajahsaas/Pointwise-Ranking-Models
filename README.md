# Ranking-Models

## Pointwise
Training learning-to-rank (LTR) using pointwise approaches. Using these approaches, the relativity in ranked list is not considered, which is very important as relative set of documents often decide the correct rank of a document. However, these pointwise models are fast to train and predict.

Models implemented - Logistic Regression, Linear Regression, Naive Bayes.

Logistic and Naive Bayes will train just like binary classification model on two classes as - 'user-liking' and 'not-liked'.  After training, these models directly predict the probability of classification for 'user-liking' class. Sorting by these probabilities for the data points produce the predicted ranking.

In case of Linear Regression, the implementation is a little different. The output variable is the relevance score (judgment score of ranking). After training, the model predict the relevance score and ranking output will be the sorted set based on these predictions.


## Pairwise
Pairwise ranking models incorporate the relativity in a ranked list which is very important for any ranking model. Since judgment depends on the set of data points available, pairwise models rightly learns this behavior while training using pairs of data points.

Most commonly used models are - SgdSVM, RankNet, LambdaRank and LambdaMart. SgdSVM is implemented using python wrapper (pysofia: https://github.com/rth/pysofia) over C++ library named sofia-ml (https://code.google.com/archive/p/sofia-ml).
Other models are implemented using RankLib module (https://github.com/jattenberg/RankLib)
