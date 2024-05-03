# Model Card

This study considered a collection of models to predict treatment outcomes (fatalities) for people with HIV. From the group of candidate models the **Random forest** and the **Naive Bayes** classifiers came out as the two best. This model card provides details about these two models.

## Model Description

**Input:** Biometric, demographic data, immune cell counts at week 0 and week 20, treatment information (the full list of input variable is given in the [data sheet](data_sheet.md) ).
 
**Output:** Prediction of fatality/survival of AIDS.

**Model Architecture:** 

1. Random forest classifier

sklearn RandomForestClassifier

| Parameter | Value |
|-----------|-------|
| Number of estimators |1000|
| Split quality measure | Gini index |
| Max depth | None |
| The minimum number of samples required to split an internal node | 2 |
|The minimum number of samples required to be at a leaf node| 1 |
|The minimum weighted fraction of the sum total of weights (of all the input samples) required to be at a leaf node| 0 |
|The number of features to consider when looking for the best split| sqrt(n_features) |
| Maximum number of leaf nodes | Unlimited |
| Minimum impurity decrease | 0.0 |
| Bootstrap | True |
| Whether to use out-of-bag samples to estimate the generalization score | False |
| Random state | False |
| verbose | 0 |
| warm_start | False |
| Class weighting | None |
| Complexity parameter used for Minimal Cost-Complexity Pruning | 0.0 |
| Max samples | X.shape[0] |

[https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)



2. Naive Bayes classifier

sklearn.naive_bayes.GaussianNB

| Parameter | Value |
|-----------|-------|
| Prior probabilities of the classes. | None |
| Portion of the largest variance of all features that is added to variances for calculation stability. | 1e-9 |

[https://scikit-learn.org/stable/modules/generated/sklearn.naive_bayes.GaussianNB.html](https://scikit-learn.org/stable/modules/generated/sklearn.naive_bayes.GaussianNB.html)

## Performance

The model was trained and tested on the [dataset](https://archive.ics.uci.edu/dataset/890/aids+clinical+trials+group+study+175). This was split to a training and test dataset in 75-25% ratio.

Model performances

|     | RF | NB |
| - | - | - |
| Accuracy  |  0.7925   |   0.7514    | 
| Sensitivity |  0.8168    |  0.8349   | 
| Specificity    |  0.6338    |  0.4883    | 
| False positives | 26    |   66    |
| False negatives|   85   |  67    |

## Limitations and trade-offs

In terms of accuracy, the **Random forest** model performs the best with 79.25% accuracy and this model is also useful as it provides insight into feature importance. 

It can be argued however that with outcomes of HIV/AIDS not missing positive outcomes (i.e. patients who would die) is more important on an individual level, as such predictions could prompt further actions to prevent this. To this end, one may look at the false negatives and the sensitivity, in both of which metrics the **Naive Bayes** classifier performed best with 83.49% sensitivity and only 67 false negatives compared to 85 with the decision forest classifier.

While an accuracy of 80% is a good indicator of risk, it is not a perfect tool for predicting individual outcomes. It is crucial to consider the false negatives and sensitivity metrics, which measure the ability of the models to correctly identify patients who are at risk of mortality.

Further limitations might arise due to the data had been collected a long time ago (early 1990s). Since the dataset was collected, the available treatments for people with HIV evolved significantly. The study reflects on the state-of-the art in HIV treatment at the time. As such, the treatments used in this study might not be often used/considered anymore.