# ThresholdFunctionLearning

A library to learn threshold functions for multi-label classifiers, as discussed in: 

Min-Ling Zhang and Zhi-Hua Zhou.  Multilabel neural networks withapplications to functional genomics and text categorization.IEEETransactions on Knowledge and Data Engineering, 18(10):1338–1351,2006.  doi:doi:10.1109/TKDE.2006.162.

---

## Description of Methods

* `mistake_size(Y_train_pred, Y_train, t)`: computes to size of <img src="https://render.githubusercontent.com/render/math?math=\widehat{Y}_i \Delta Y_i"> (where <img src="https://render.githubusercontent.com/render/math?math=\Delta"> indicates symmetric difference).    
    Arguments: 
    - Y_train_pred: a vector of predicted label propensities for training instance "i"
    - Y_train: true binary labels for training instance "i"
    - t: a threshold value to be used for predicting binary labels from Y_train_pred vector

* `target_value_single(Y_train_pred, Y_train, t_range)`: computes <img src="https://render.githubusercontent.com/render/math?math=\textrm{argmin}_t (\widehat{Y}_i \Delta Y_i)">.     
    Arguments:
    - Y_train_pred
    - Y_train
    - t_range: a tuple, defining the lower and upper bound of values of "t" to use in <img src="https://render.githubusercontent.com/render/math?math=\textrm{argmin}_t">


---

**NOTE:** 'Description of Methods' section is still be completed.