# wikipedia_analysis

This repository contains my code to predict quality class of Wikipedia articles.

You should find the code in R file in **analysis** directory.

## Data set

The data is stored in *all_data.tsv* file.

The data set contains information of ~ 20 000 Wikipedia articles, collected through Wikipedia projects.

# Running the code

You should have [R](https://www.r-project.org) installed. I suggest that you should also use [RStudio](https://www.rstudio.com) as the IDE, but it is optional.

Please note that the code is tested with R 3.2.3

These following packages are required:

- caTools
- rpart
- class
- h2o


First, you should load the code


```r
setwd ("path to AnalyzeData.R file")
source ("AnalyzeData.R")
```

Then you can run the following analysis.

## Linear regression

The linear regression is done by calling the function *runRegression*. 

## CART

The CART model is done by calling the function *runCART*. 

## kNN

The function for kNN model is *runKNNModel*.

## Multinominal logistic regression

The predictor using multinominal logistic regression could be called with the function *runMultinominalLogisticRegression*

The function requires packages *caret* and *nnet*.

## SVM

Packages required: *caret* and *e1071*

Function name: *runSVM*

## random forest

We provided two functions for *randomForest* model.

The first function is ``runRFModel``, which will load and run the data with readability scores using k-fold (with k = 5)

The second function is ``runRFModel_withoutReadabilityScore``, which will run without using readability scores, as in [1].

We applied 5-folds cross validation.

You should observe that the first function provide a better prediction.

## Utilities

We provided some other utility functions such as calculate RMSE or NDCG.

[1] Warncke-Wang, M., Ayukaev, V.R., Hecht, B. and Terveen, L.G., 2015, February. The Success and Failure of Quality Improvement Projects in Peer Production Communities. In Proceedings of the 18th ACM Conference on Computer Supported Cooperative Work & Social Computing (pp. 743-756). ACM.


