# ThresholdFunctionLearning

A library to learn threshold functions for multi-label classifiers, as discussed in: 

Min-Ling Zhang and Zhi-Hua Zhou.  Multilabel neural networks withapplications to functional genomics and text categorization.IEEETransactions on Knowledge and Data Engineering, 18(10):1338–1351,2006.  doi:doi:10.1109/TKDE.2006.162.

---

## Important Files for Use

1. **threshold_learning.py:** the library for threshold function learning, as described in Zhang \& Zhou (2014)
2. **threshold_learning_demo.ipynb:** a Jupyter notebook written to demonstrate the use and usefulness of the threshold_learning library. Using a multilabel example from functional genomics, a comparison of two methods using both constant and learned threshold functions is explored.
---

## Description of Methods

* `mistake_size(Y_train_pred, Y_train, t)`: computes the size of <img src="https://render.githubusercontent.com/render/math?math=\widehat{Y}_i \Delta Y_i"> (where <img src="https://render.githubusercontent.com/render/math?math=\Delta"> indicates symmetric difference).    
    Arguments: 
    - Y_train_pred: a vector of predicted label propensities for training instance "i"
    - Y_train: true binary labels for training instance "i"
    - t: a threshold value to be used for predicting binary labels from Y_train_pred vector

* `target_value_single(Y_train_pred, Y_train, t_range)`: computes <img src="https://render.githubusercontent.com/render/math?math=\textrm{argmin}_t (\widehat{Y}_i \Delta Y_i)">.     
    Arguments:
    - Y_train_pred: a vector of predicted label propensities for training instance "i"
    - Y_train: true binary labels for training instance "i"
    - t_range: a tuple, defining the lower and upper bound of values of "t" to use in <img src="https://render.githubusercontent.com/render/math?math=\textrm{argmin}_t">

* `get_target_values(Y_train_pred, Y_train, t_range)`: computes <img src="https://render.githubusercontent.com/render/math?math=\textrm{argmin}_t (\widehat{Y}_i \Delta Y_i)"> for all "i" (entire data set).    
    Arguments:
    - Y_train_pred: a matrix of predicted label propensities where each row corresponds to a single training instance
    - Y_train: true binary labels for training instances (each row corresponds to a single instance)
    - t_range: a tuple, defining the lower and upper bound of values of "t" to use in <img src="https://render.githubusercontent.com/render/math?math=\textrm{argmin}_t">

* `threshold_function_learn(Y_train_pred, Y_train, t_range)`: learns threshold function parameters. Returns a "LinearRegression()" object from sklearn.    
    Arguments:
    - Y_train_pred: a matrix of predicted label propensities where each row corresponds to a single training instance
    - Y_train: true binary labels for training instances (each row corresponds to a single instance)
    - t_range: a tuple, defining the lower and upper bound of values of "t" to use in <img src="https://render.githubusercontent.com/render/math?math=\textrm{argmin}_t">

* `predict_labels_binary(Y_pred, threshold_function)`: returns the binary labels associated with predicted label propensities and a given threshold function.    
    Arguments:
    - Y_pred: a matrix of predicted label propensities. Each row corresponds to a single instance
    - threshold_function: a learned threshold function with a "predict()" method. 

* `predict_test_labels_binary(Y_train_pred, Y_train, Y_test_pred, t_range)`: learns a threshold function, using training data, and uses said function to compute binary labels for instances in a test set.     
    Arguments:
    - Y_train_pred: a matrix of predicted label propensities where each row corresponds to a single training instance
    - Y_train: true binary labels for training instances (each row corresponds to a single instance)
    - Y_test_pred: a matrix of predicted label propensities where each row corresponds to a single test instance
    - t_range: a tuple, defining the lower and upper bound of values of "t" to use in <img src="https://render.githubusercontent.com/render/math?math=\textrm{argmin}_t">


