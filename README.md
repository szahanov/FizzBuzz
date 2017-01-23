# Predicting image types using three different classification/regression algorithms #

This work is inspired by the idea of a [FizzBuzz program](https://imranontech.com/2007/01/24/using-fizzbuzz-to-find-developers-who-grok-coding/) used to find hirable developers, I was wondering what the data science equivalent would be and did this.

Data is taken from here: https://archive.ics.uci.edu/ml/datasets/Image+Segmentation  
That has data for images that fall into 7 categories: brickface, sky, foliage, cement, window, path, and grass

I take the data and use the Random Forest, K Nearest Neighbour, and Support Vector Machine algorithms to find out which class each image belongs to.

### End Results ###

* Quick summary
* Version
* [Learn Markdown](https://bitbucket.org/tutorials/markdowndemo)


* From the R code:

> # test the model
> predictions <- predict(fit.rf, validation)
> confusionMatrix(predictions, validation$ImageBackground)
Confusion Matrix and Statistics

           Reference
Prediction  BRICKFACE CEMENT FOLIAGE GRASS PATH SKY WINDOW
  BRICKFACE         5      1       0     0    0   0      1
  CEMENT            0      4       0     0    0   0      0
  FOLIAGE           0      0       6     0    0   0      0
  GRASS             0      0       0     6    0   0      0
  PATH              0      0       0     0    6   0      0
  SKY               0      0       0     0    0   6      0
  WINDOW            0      1       0     0    0   0      5

Overall Statistics
                                          
               Accuracy : 0.9268          
                 95% CI : (0.8008, 0.9846)
    No Information Rate : 0.1463          
    P-Value [Acc > NIR] : < 2.2e-16       
                                          
                  Kappa : 0.9147          
 Mcnemar's Test P-Value : NA              

Statistics by Class:

                     Class: BRICKFACE Class: CEMENT Class: FOLIAGE
Sensitivity                    1.0000       0.66667         1.0000
Specificity                    0.9444       1.00000         1.0000
Pos Pred Value                 0.7143       1.00000         1.0000
Neg Pred Value                 1.0000       0.94595         1.0000
Prevalence                     0.1220       0.14634         0.1463
Detection Rate                 0.1220       0.09756         0.1463
Detection Prevalence           0.1707       0.09756         0.1463
Balanced Accuracy              0.9722       0.83333         1.0000
                     Class: GRASS Class: PATH Class: SKY Class: WINDOW
Sensitivity                1.0000      1.0000     1.0000        0.8333
Specificity                1.0000      1.0000     1.0000        0.9714
Pos Pred Value             1.0000      1.0000     1.0000        0.8333
Neg Pred Value             1.0000      1.0000     1.0000        0.9714
Prevalence                 0.1463      0.1463     0.1463        0.1463
Detection Rate             0.1463      0.1463     0.1463        0.1220
Detection Prevalence       0.1463      0.1463     0.1463        0.1463
Balanced Accuracy          1.0000      1.0000     1.0000        0.9024

### Steps ###

* Summary of set up
* Configuration
* Dependencies
* Database configuration
* How to run tests
* Deployment instructions

### Links ###

[R code](https://bitbucket.org/tutorials/markdowndemo)
[data](https://bitbucket.org/tutorials/markdowndemo)
