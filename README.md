# Predicting image types using three different classification/regression algorithms #

This work is inspired by the idea of a [FizzBuzz program](https://imranontech.com/2007/01/24/using-fizzbuzz-to-find-developers-who-grok-coding/) used to find hirable developers, I was wondering what the data science equivalent of a Fizz Buzz program would be and did this.

Data is taken from here: https://archive.ics.uci.edu/ml/datasets/Image+Segmentation  
That has data for images that fall into 7 categories: brickface, sky, foliage, cement, window, path, and grass

I take the data and use the Random Forest, K Nearest Neighbour, and Support Vector Machine algorithms to find out which class each image belongs to.

# Quick Results #

### End result ###

* After making the three models, these are the results. The random forest model was the most useful, with high accuracy and a high kappa coefficient:  
* rf = Random Forest, knn = K Nearest Nieghbour algorithm, SVM = Supporting Vector algorithm
![results chart](https://bytebucket.org/szahanov/fizzbuzz/raw/master/charts/dotplot1.png "Results for each model")

* After cleaning the data and running each of a Random Forest, a K Nearest Neighbour, and a Support Vector Machine algorithm on it, I was able to correctly classify the data with decent accuracy and sensitivity.

* These are the results of the Random Forest model. This shows the predictions vs. the test data, with very good results. With a larger training data set I think the three misclassifications would go away.

> # test the model
> predictions <- predict(fit.rf, validation)
> confusionMatrix(predictions, validation$ImageBackground)
> Confusion Matrix and Statistics

>            Reference
> Prediction  BRICKFACE CEMENT FOLIAGE GRASS PATH SKY WINDOW  
>   BRICKFACE         5      1       0     0    0   0      1  
>   CEMENT            0      4       0     0    0   0      0  
>   FOLIAGE           0      0       6     0    0   0      0  
>   GRASS             0      0       0     6    0   0      0  
>   PATH              0      0       0     0    6   0      0  
>   SKY               0      0       0     0    0   6      0  
>   WINDOW            0      1       0     0    0   0      5  

> Overall Statistics
                                          
>                Accuracy : 0.9268          
>                  95% CI : (0.8008, 0.9846)  
>     No Information Rate : 0.1463          
>     P-Value [Acc > NIR] : < 2.2e-16       
                                          
>                   Kappa : 0.9147          
>  Mcnemar's Test P-Value : NA              

> Statistics by Class:

>                      Class: BRICKFACE Class: CEMENT Class: FOLIAGE  
> Sensitivity                    1.0000       0.66667         1.0000  
> Specificity                    0.9444       1.00000         1.0000  
> Pos Pred Value                 0.7143       1.00000         1.0000  
> Neg Pred Value                 1.0000       0.94595         1.0000  
> Prevalence                     0.1220       0.14634         0.1463  
> Detection Rate                 0.1220       0.09756         0.1463  
> Detection Prevalence           0.1707       0.09756         0.1463  
> Balanced Accuracy              0.9722       0.83333         1.0000  
>                      Class: GRASS Class: PATH Class: SKY Class: WINDOW  
> Sensitivity                1.0000      1.0000     1.0000        0.8333  
> Specificity                1.0000      1.0000     1.0000        0.9714  
> Pos Pred Value             1.0000      1.0000     1.0000        0.8333  
> Neg Pred Value             1.0000      1.0000     1.0000        0.9714  
> Prevalence                 0.1463      0.1463     0.1463        0.1463  
> Detection Rate             0.1463      0.1463     0.1463        0.1220  
> Detection Prevalence       0.1463      0.1463     0.1463        0.1463  
> Balanced Accuracy          1.0000      1.0000     1.0000        0.9024  

# Steps #

* See the full code to see each step, it is commented pretty well.
https://bitbucket.org/szahanov/fizzbuzz/src/master/image_classification.R

### Visualizing the data ###

* These are the plots that were created to visualize the diffrent image classes before creating the prediction models:  
* Each coloured group of points is a different category (e.g. brickface, sky, foliage, etc). Since they don't always overlap I get the impression that I can work with this.  

* Box and whisker plots to show that the variables I'm using vary depending on the image type  
![boxplot chart](https://bytebucket.org/szahanov/fizzbuzz/raw/master/charts/boxplot3.png "Box plot")

* This density plot shows basically the same thing but it's easier to see how much the image classes overlap with each other:  
![density plot](https://bytebucket.org/szahanov/fizzbuzz/raw/master/charts/densityplot1.png "Density plot")

* This scatter plot shows more dimensions, here we can see that there are cases where there is little overlap between image types when looking at the colour variables:  
![scatterplot chart](https://bytebucket.org/szahanov/fizzbuzz/raw/master/charts/scatterplot1.png)

* At first glance it looks like I should be able to work with this data and successfully classify the images.

# Links #

* [R code](https://bitbucket.org/szahanov/fizzbuzz/src/master/image_classification.R)

* [data](https://bitbucket.org/szahanov/fizzbuzz/src/master/segmentation_modified.data?at=master&fileviewer=file-view-default)

* [charts](https://bitbucket.org/szahanov/fizzbuzz/src/master/charts/)
