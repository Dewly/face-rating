###Predicting Attractiveness using Computer Vision
This is the companion code of my blog [post](http://www.learnopencv.com/computer-vision-for-predicting-facial-attractiveness/).

![alt tag](http://www.learnopencv.com/wp-content/uploads/2015/07/2_det_0.jpg)


### Feature Generation
The features computation part of the pipeline requires the location of facial landmars of the input images. These landmarks can be generated by the [CLM-framework](https://github.com/TadasBaltrusaitis/CLM-framework). I have already included the landmarks localized using this framework in the data directory of this repo, and you can directly work with them. 

### What's included

```
face-rating/
├── data/
│   ├── ratings.txt
│   ├── landmarks.txt
│   ├── features_ALL.txt
├── source/
│   ├── generateFeatures.py
│   └── trainModel.py
│   └── cross_validation.py
└── results/
    ├── cross_valid_predictions_knn.txt
    ├── cross_valid_predictions_gpr.txt
    ├── cross_valid_predictions_linear.txt
    ├── cross_valid_predictions_rf.txt
    └── cross_valid_predictions_svm.txt
```

###Example Usage
```shell
python trainModel -model linear_model -featuredim 20
```
The `-featuredim` argument specifies the number of components chosen by PCA. Other supported models are Support Vector Machines (svm), Random Forests (rf), and Gaussian Process Regression (gpr). Checkout the source to change hyperparameters and other options. 

###Requirements
1. Python 2.7
2. Numpy
3. scikit-learn

###Installing scikit-learn
Visit the official [installation page](http://scikit-learn.org/stable/install.html) for instructions.

###Dataset
The [SCUT-FBP](http://www.hcii-lab.net/data/SCUT-FBP/EN/introduce.html) dataset has been used. Please cite their research if you happen to use this dataset. The facial landmarks computer on this particular dataset are available in the `data/` directory. 

###License
MIT
