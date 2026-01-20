Spark MLlib - the component for ML/Data mining algorithms
Data Types:
* Local vector
* Labeled point
* Local matrix
* Distributed matrix
* new: extensions for CUDA GPU
* ..

Local vector:
dense or sparse (nulls or 0's not represented)
dense format: {1.0,0.0,3.0}
sparse: {3, (0,2),(1.0,3.0)}
Vector denseVec = Vectors.dense(1.0, 0.0, 2.0); 
Vectors.sparse(5, new int[] {0, 4}, new double[] {1.0, 3.5});

Labeled point:
c'tor:
LabelPoint LabeledPoint(double label, Vector features)

Main concepts:
MLLib uses DataFrames. columns are usually comprised of the label, the features and text. 

Transformer: an object that transforms a Dataset into another Dataset. 
Estimator: represents the model itself. has fit() method which accepts a Dataset and produces a model of type Transformer (for example the weights)

Pipeline: 
chains multiple Transformers and Estimators together to specify a ML/Data Mining workflow. 

Parameter: 
all Transformers and Estimators share the same API (they all have fit())
*use this in HW2*. 

Classification algorithms:
Logistic regression
Decision trees
SVM
Naive bayes

all models have two phases:
Model generation (Training)
Prediction (inference)

