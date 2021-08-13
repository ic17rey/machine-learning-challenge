# Machine Learning Challenge - Exoplanet Exploration

### Challenge Details

Machine learning models are explored for classifying candidate exoplanets from a dataset available on Kaggle, [Exoplanet Data Source](https://www.kaggle.com/nasa/kepler-exoplanet-search-results). The challenge involves preprocessing the data, and training and tuning the models. The models being compared are created with Logistic Regression and with Support Vector Machines (SVM). Feature selection was complicated by the number of columns available. The [Exoplanet Data Dictionary](https://exoplanetarchive.ipac.caltech.edu/docs/API_kepcandidate_columns.html) was helpful but also there was some trial and error involved. Ultimately it was using nearly all the columns where the model achieved the greatest success. 

* The data was separated into training and testing data using `sklearn`. 
* Following the split of data for training and testing, the MinMaxScaler is used to scale the numerical data (for X only).
* Tuning of the model parameters is done with `GridSearch`, again, with some trial and error, evaluting the warnings to exclude use of certain parameters.

### Summary of results and analysis

#### Logistic Regression Model Results
Prior to parameter tuning:  
Training Data Score 0.8464619492656876
Testing Data Score  0.8638443935926774

Following parameter tuning the model "grid" improves to 0.8678214075200664 accuracy.

The classification report reads:
                  precision    recall  f1-score   support  
     FALSE POSITIVE       0.84      0.65      0.73       404
     CONFIRMED       0.73      0.87      0.79       435
     CANDIDATE       0.99      1.00      0.99       909

      accuracy                           0.89      1748
     macro avg       0.85      0.84      0.84      1748
  weighted avg       0.89      0.89      0.88      1748

#### SVM Results

Training Data Score: 0.8371161548731643
Testing Data Score: 0.8564073226544623

Following parameter tuning the model "grid" improves to 0.8701093007517156 accuracy.


The classification report reads:
                  precision    recall  f1-score   support  
     FALSE POSITIVE       0.89      0.61      0.72       404
     CONFIRMED       0.72      0.91      0.80       435
     CANDIDATE       0.99      1.00      0.99       909

      accuracy                           0.89      1748
     macro avg       0.86      0.84      0.84      1748
  weighted avg       0.90      0.89      0.88      1748




* Create a README that reports a comparison of each model's performance as well as a summary about your findings and any assumptions you can make based on your model (is your model good enough to predict new exoplanets? Why or why not? What would make your model be better at predicting new exoplanets?).

- - -


✓ README compares each of the models’ performances and predictions
✓ README summarizes the findings and makes assumptions based on the data and their models.
✓ README discusses the predictions of the possible exoplanets with their models.

