# Machine Learning Challenge - Exoplanet Exploration

### Challenge Details

Machine learning models are explored for classifying candidate exoplanets from a dataset available on Kaggle, [Exoplanet Data Source](https://www.kaggle.com/nasa/kepler-exoplanet-search-results). The challenge involves preprocessing the data, and training and tuning the models. The models being compared are created with Logistic Regression and with Support Vector Machines Linear Classifier. Feature selection was complicated by the number of columns available. The [Exoplanet Data Dictionary](https://exoplanetarchive.ipac.caltech.edu/docs/API_kepcandidate_columns.html) was helpful but also there was some trial and error involved. Ultimately it was using nearly all the columns where the model achieved the greatest success. 

* The data was separated into training and testing data using `sklearn`. 
* Following the split of data for training and testing, the `MinMaxScaler` is used to scale the numerical data (for X only).
* Tuning of the model parameters is done with `GridSearch`, again, with some trial and error, evaluting the warnings to exclude use of certain parameters.

#### Logistic Regression Model Results (jupyter notebook model_1)
Prior to parameter tuning:  
Training Data Score 0.8464619492656876  
Testing Data Score  0.8638443935926774

Following parameter tuning the model identified as "grid" improves to 0.8678214075200664 accuracy.

The classification report reads:
category        | precision | recall | f1-score | support 
--------------- | --------- | ------- | ------- | --------
FALSE POSITIVE  |    0.84   |   0.65  |   0.73  |   404
CONFIRMED       |    0.73   |   0.87  |   0.79  |   435
CANDIDATE       |    0.99   |   1.00  |   0.99  |   909
accuracy        |           |         |   0.89  |  1748
macro avg       |    0.85   |   0.84  |   0.84  |  1748
weighted avg    |    0.89   |   0.89  |   0.88  |  1748

#### Logistic Regression Model_2 (jupyter notebook model_2)
Exploration of how dropping additional features would affect the Logistic Regression - due to inferior accuracy analysis in this notebook was not completed.


#### Support Vector Machines Linear Classifier Results (jupyter notebook model_3)
Prior to parameter tuning:
Training Data Score: 0.8371161548731643  
Testing Data Score: 0.8564073226544623

Following parameter tuning the model identified as "grid" improves to 0.8701093007517156 accuracy.

The classification report reads:
category        | precision | recall | f1-score | support 
--------------- | --------- | ------- | ------- | --------
FALSE POSITIVE  |    0.89   |   0.61  |   0.72  |   404
CONFIRMED       |    0.72   |   0.91  |   0.80  |   435
CANDIDATE       |    0.99   |   1.00  |   0.99  |   909
accuracy        |           |         |   0.89  |  1748
macro avg       |    0.86   |   0.84  |   0.84  |  1748
weighted avg    |    0.90   |   0.89  |   0.88  |  1748


#### Comparison of the two models
The models are saved as logistic_regression.sav and SVC.sav.

Prior to parameter tuning, the Logistic Regression model's scores for both Training and Testing Data were slightly higher than with the Support Vector Machines model. Following parameter tuning, though, both models are very comparable, with accuracy above 85%. After parameter tuning, the Support Vector model shows a slight edge in accuracy as compared to Logistic Regression. The SVM's edge primarily comes in ability to predict the false positives, which are predicted at 89% accuracy as compared to only 84% accuracy with Logistic Regression. Confirmed and Candidate results are predicted at comparable accuracy between the two models. 

Overall both models seem to be good predictors of new exoplanets, although better understanding of what features carry the most weight and which other features could be dropped from the analysis would help the models make better predictions.
