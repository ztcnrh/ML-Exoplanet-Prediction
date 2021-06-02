# ML Exoplanet Prediction

Penn Data Boot Camp Assignment 21 - Machine learning models capable of classifying candidate exoplanets from approximately 10,000 exoplanets examined by the Kepler Space Observatory.

### Original Data Source:
[Kepler Exoplanet Search Results - NASA](https://www.kaggle.com/nasa/kepler-exoplanet-search-results)<br>
[Data Catalog - Data Columns in Kepler Objects of Interest Table](https://exoplanetarchive.ipac.caltech.edu/docs/API_kepcandidate_columns.html)

## Models Summary

### Random Forests
                    precision    recall  f1-score   support

     CANDIDATE         0.84      0.79      0.81       411
     CONFIRMED         0.84      0.86      0.85       484
     FALSE POSITIVE    0.98      1.00      0.99       853

     accuracy                              0.91      1748
     macro avg         0.89      0.88      0.88      1748
     weighted avg      0.91      0.91      0.91      1748

* This model's best score is 0.909 when the number of trees = 200, and the weighted average score is 0.91
* It is best at predicting "False Positive"

### Logistic Regression
                    precision    recall  f1-score   support

     CANDIDATE         0.61      0.62      0.62       411
     CONFIRMED         0.68      0.65      0.66       484
     FALSE POSITIVE    0.98      1.00      0.99       853

     accuracy                              0.81      1748
     macro avg         0.76      0.76      0.76      1748
     weighted avg      0.81      0.81      0.81      1748

* This model's best score is 0.824 when 'C'=50 and the weighted average score is 0.81
* It is also best at predicting "False Positive".

### Deep Learning

**model.summary()**

*Model: "sequential"*
Layer (type)                 Output Shape              Param num   
dense (Dense)                (None, 100)               2100      
dense_1 (Dense)              (None, 100)               10100     
dense_2 (Dense)              (None, 3)                 303       

*Layers: 2; Nodes: 100; Inputs: 20; Outputs: 3*<br>
*Total params: 12,503; Trainable params: 12,503; Non-trainable params: 0*

* Loss: 0.33445, Accuracy: 0.84439

## Conclusion:

The Random Forests model has the highest F1-score along with the best precision and recall on individual classes. It would be the most ideal model to use to classify candidate exoplanets into desired categories based on the input features we selected.
