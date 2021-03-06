# Spark MLlib Data Types
## Local Vector
* Dense Vector 
  - NumPy Array and Python List are recognized as Dense Vectors. 
  - Generally, NumPy arrays are recommended over lists for efficiency. 
* Sparse Vector
  - A majority of the values in a sparse vector will be zeros. 
  - SciPy csc_matrix is recognized as Sparse Vector. 
  - Training data is commonly sparse. 

## Labeled Points

## Local Matrix
* Row Pointers/Column Pointers 
* Dense Matrix: Column-Major Ordering
* Sparse Matrix: Row-Major Ordering

## Distributed Matrix 
* RowMatrix
* IndexedRowMatrix
* CoordinateMatrix
* BlockMatrix
  - A MatrixBlock is a tuple with two inputs: `((blockRowIndex, BlockColIndex), Matrix)`

# Algorithms 
## Linear Regression: 
There are different evaluation methods that can be used
* Mean Absolute Error (MAE)
* Mean Square Error (MSE)
* Root Mean Squared Error (RMSE)

## Support Vector Machines (SVM)
![Support Vector Machine](mllib-SupportVectorMachine.png)

## Logistic Regression
![Logistic Regression](mllib-LogisticRegression.png)

## Decision Trees & Random Forests
### The Types of Decision Trees Spark MLlib Supports
* Binary Classification Tree
* Multi-class Classification Tree
* Regression Decision Tree

### Parameters involved in Decision Tree splitting features
* Continuous Features
* Categorical Features
  ![Categorical Features](mllib-CategoricalFeatures.png) 
* Stop Functions (Stopping Rule): Recursion stops if any of the following conditions are met. 
  - Node depth is equal to the maxDepth training parameter.
  - No split candidate leads to information gain greater than minInfoGain. 
  - No split candidate produces child nodes which have at least minInstancesPerNode training instances. 
  
### Parameters involved in creating Decision Trees
* Specifiable Parameters (without Tuning required)
  - numClasses
    * Number of classes for classification
    * Value depends on the dataset
  - categoricalFeaturesInfo
    * Which features are categorical 
    * Number of values each feature can take
    * Map from feature indices to number of categories
  - seed (Unique for random forest)
    * Random seed for bootstrapping, choosing feature subsets. 
    * Set as None (default): Generates seed based on system time. 
* Tunable Parameters
  - maxBins
  - impurity
    * Measure used to choose between candidate splits
    * Used in the information gain calculation
    * Must match type of Decision Tree
      - Classification: gini, entrogy
      - Regression: variance
  - numTree: Unique for random forest. 
  - featureSubsetStrategy: Unique for random forest. Number of features used as candidates for splitting at each tree node. 
* Stopping Parameters (Tunable)
  - maxDepth = Maximum depth of the tree
  - minInstancesPerNode
    * Number of instances required for node to split further
    * Commonly used in RandomForest  
  ![minInstancesPerNode](mllib-minInstancesPerNode.PNG)
  - minInfoGain
    * Node must provide at least this much information gain in order to split. 
    * Information Gain: Amount of variability decrease resulting from a node split. 

#### Parameter Comparision 
![Parameter Comparision](mllib-decision-tree-and-random-forest-parameter-comparision.PNG)

## K-Means Clustering: Unsupervised Learning
## Gaussian Mixture Clustering
![Gaussian Mixture Clustering](mllib-GaussianMixtureClustering.png)
