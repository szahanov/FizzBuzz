# Predicting image types using three different classification/regression algorithms #

This is a [FizzBuzz](https://imranontech.com/2007/01/24/using-fizzbuzz-to-find-developers-who-grok-coding/)-like project but for data science.

Data is taken from here: https://archive.ics.uci.edu/ml/datasets/Image+Segmentation  
That has data for images that fall into 7 categories: brickface, sky, foliage, cement, window, path, and grass

I take the data and use the Random Forest, K Nearest Neighbour, and Support Vector Machine algorithms to find out which class each image belongs to.

# End Results #

* After cleaning the data and running each of Random Forest, K Nearest Neighbour, and Support Vector algorithms on it, I was able to correctly classify the images with good accuracy and sensitivity.

* These are the results for the three models. The random forest model was the most useful, with high accuracy and a high kappa coefficient:  
* rf = Random Forest, knn = K Nearest Neighbour algorithm, SVM = Supporting Vector algorithm  

![results chart](https://raw.githubusercontent.com/szahanov/FizzBuzz/master/charts/dotplot1.png "Results for each model")

* These are the results of the Random Forest model. This shows the predictions vs. the test data, with very good results.

Results Matrix|Reference|. |. |. |. |. |.
-----------|----------|-------|--------|------|-----|----|-------
Prediction |BRICKFACE |CEMENT |FOLIAGE |GRASS |PATH |SKY |WINDOW
  BRICKFACE        |29      |0       |0     |0    |0   |0      |0
  CEMENT            |0     |30       |0     |0    |0   |0      |0
  FOLIAGE           |0      |0      |30     |0    |0   |0      |0
  GRASS             |0      |0       |0    |30    |0   |0      |0
  PATH              |0      |0       |0     |0   |30   |0      |0
  SKY               |0      |0       |0     |0    |0  |30      |0
  WINDOW            |0      |0       |0     |0    |0   |0     |30

> Overall Statistics
         
>                Accuracy : 1          
>                  95% CI : (0.9825, 1)
>     No Information Rate : 0.1435     
>     P-Value [Acc > NIR] : < 2.2e-16  
        
>                   Kappa : 1          
>  Mcnemar's Test P-Value : NA         

> Statistics by Class:

|Class: BRICKFACE |Class: CEMENT |Class: FOLIAGE |.
--------------------|------------------|--------------|-------------
Sensitivity                    |1.0000        |1.0000         |1.0000       |1.0000
Specificity                    |1.0000        |1.0000         |1.0000       |1.0000
Pos Pred Value                 |1.0000        |1.0000         |1.0000       |1.0000
Neg Pred Value                 |1.0000        |1.0000         |1.0000       |1.0000
Prevalence                     |0.1388        |0.1435         |0.1435       |0.1435
Detection Rate                 |0.1388        |0.1435         |0.1435       |0.1435
Detection Prevalence           |0.1388        |0.1435         |0.1435       |0.1435
Balanced Accuracy              |1.0000        |1.0000         |1.0000       |1.0000

|Class: GRASS |Class: PATH |Class: SKY |Class: WINDOW |.
---------------------|-------------|------------|-----------|-------
Sensitivity               |1.0000     |1.0000        |1.0000
Specificity               |1.0000     |1.0000        |1.0000
Pos Pred Value            |1.0000     |1.0000        |1.0000
Neg Pred Value            |1.0000     |1.0000        |1.0000
Prevalence                |0.1435     |0.1435        |0.1435
Detection Rate            |0.1435     |0.1435        |0.1435
Detection Prevalence      |0.1435     |0.1435        |0.1435
Balanced Accuracy         |1.0000     |1.0000        |1.0000

# Steps #

* See the full code if you want to see each step, it is commented pretty well.
https://github.com/szahanov/FizzBuzz/blob/master/image_classification.R

# Visualizing the data - before modelling #

* These are the plots that were created to visualize the different image classes before creating the prediction models:  
* Each coloured group of points is a different category (e.g. brickface, sky, foliage, etc). Since they don't always overlap I get the impression that I can work with this.  

* Box and whisker plots to show that the variables I'm using vary depending on the image type  
![boxplot chart](https://raw.githubusercontent.com/szahanov/FizzBuzz/master/charts/boxplot3.png "Box plot")

* This density plot shows basically the same thing but it's easier to see how much the image classes overlap with each other:  
![density plot](https://raw.githubusercontent.com/szahanov/FizzBuzz/master/charts/densityplot1.png "Density plot")

* This scatter plot shows more dimensions, here we can see that there are cases where there is little overlap between image types when looking at the colour variables:  
![scatterplot chart](https://raw.githubusercontent.com/szahanov/FizzBuzz/master/charts/scatterplot1.png)

* At first glance it looks like I should be able to work with this data and successfully classify the images.

# Links #

* [R code](https://github.com/szahanov/FizzBuzz/blob/master/image_classification.R)

* [Training Data](https://github.com/szahanov/FizzBuzz/blob/master/segmentation_modified.data?at=master&fileviewer=file-view-default)

* [Test Data](https://github.com/szahanov/FizzBuzz/blob/master/segmentation_modified.test?at=master&fileviewer=file-view-default)

* [Charts](https://github.com/szahanov/FizzBuzz/blob/master/charts/)

* [Original data source](https://archive.ics.uci.edu/ml/datasets/Image+Segmentation)
