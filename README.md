# ThresholdFunctionLearning

A library to learn threshold functions for multi-label classifiers, as discussed in: 

Min-Ling Zhang and Zhi-Hua Zhou.  Multilabel neural networks withapplications to functional genomics and text categorization.IEEETransactions on Knowledge and Data Engineering, 18(10):1338–1351,2006.  doi:doi:10.1109/TKDE.2006.162.

---

## Description of Methods

* `mistake_size(Y_train_pred, Y_train, t)`: computes to size of <img src="https://render.githubusercontent.com/render/math?math=\widehat{Y}_i \Delta Y_i"> (where $\Delta$ indicates symmetric difference). 