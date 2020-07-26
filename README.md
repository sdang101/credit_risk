# credit_risk

# Oversampling
## Naive Random Oversampling
|               |   pre    |    rec   |     spe   |      f1   |     geo   |     iba   |     sup  |
| :-------------|:---------|:---------|:----------|:----------|:----------|:----------|:--------:|
|  high_risk    |   0.01   |   0.61   |    0.68   |    0.02   |    0.64   |    0.41   |      87  |
|   low_risk    |   1.00   |   0.68   |    0.61   |    0.81   |    0.64   |    0.42   |   17118  |
|avg / total    |   0.99   |   0.68   |    0.61   |    0.81   |    0.64   |    0.42   |   17205  |

The accuracy score is moderately low at 64.6%. Recall for both high and low risk are moderately low (61%, 68%), but precision for high risk (1%) is really low. f1 score is really low for high risk, but high for low risk.

Random Oversampling is not a good model at classifying high and low risk creditors.

## SMOTE
|               |   pre    |  rec     |   spe     |    f1     |   geo     |iba        |  sup    |
| :-------------|:---------|:---------|:----------|:----------|:----------|:----------|:--------|
|  high_risk    |   0.01   |   0.70   |   0.57    |   0.02    |   0.63    |   0.41    |     87  |
|   low_risk    |   1.00   |   0.57   |   0.70    |   0.73    |   0.63    |   0.40    |  17118  |
|avg / total    |   0.99   |   0.57   |   0.70    |   0.73    |   0.63    |   0.40    |  17205  |

The accuracy score is similar to random oversampling (63.8%). Recall for high risk is better than in random oversampling (70%) but recall for low risk is lower than in random oversampling. The f1 score decreased compared to random oversampling.

SMOTE and random oversampling seem equally poor at classifying high and low risk creditors.

# Undersampling
## Cluster Centroid
|               |    pre   |    rec   |    spe    |    f1     |   geo     |    iba    |   sup   |
| :-------------|:---------|:---------|:----------|:----------|:----------|:----------|:--------|
|  high_risk    |   0.01   |   0.64   |   0.67    |  0.02     |   0.65    |  0.43     |     87  |
|   low_risk    |   1.00   |   0.67   |   0.64    |  0.80     |   0.65    |  0.43     |  17118  |
| avg / total   |   0.99   |   0.67   |   0.64    |  0.79     |   0.65    | 0.43      |  17205  |

The accuracy score is moderately low at 63.8%. Precision remains about the same as oversampling models. Recall for both high and low risk is moderately low (64%, 67%). f1 score is really low for high risk (1%) and is moderately high for low_risk (80%).

Cluster centroid is not a good model for classifying high and low risk risk creditors.

## Combination
|               |   pre    |   rec    |   spe     |   f1      |   geo     |  iba      | sup     |
| :-------------|:---------|:---------|:----------|:----------|:----------|:----------|:--------|
|  high_risk    |   0.01   |   0.70   |   0.57    |  0.02     |   0.63    |  0.41     |      87 | 
|   low_risk    |   1.00   |   0.57   |   0.70    |  0.73     |   0.63    |  0.40     |   17118 |
|avg / total    |   0.99   |   0.57   |   0.70    |  0.73     |   0.63    |  0.40     |   17205 |

The accuracy score is lower than in oversampling and undersampling (52.1%).Precision remains the same as the other models. Recall and f1 score also remains about the same, thus the combination model also is not a good model for classifying high and low risk creditors.

# Ensemble
## Balanced Random Forest Classifier
|               |    pre   |    rec   |    spe    |    f1     |   geo     |  iba      |    sup  |
| :-------------|:---------|:---------|:----------|:----------|:----------|:----------|:--------|
|  high_risk    |   0.03   |   0.71   |   0.86    |  0.05     |     0.78  |    0.61   |     87  |
|   low_risk    |   1.00   |   0.86   |   0.71    |  0.93     |     0.78  |    0.62   |  17118  | 
|avg / total    |   0.99   |   0.86   |   0.71    |  0.92     |     0.78  |    0.62   |  17205  |

The accuracy score is 78.8% which is somewhat high. Recall for high risk is 71% which is somewhat high, but precision is really low (3%). Recall for low risk is high 86%, and precision is high (100%). f1 score for low risk is high (93%), but remains low for high risk.

Balanced random forest classifier is a good model for classifying low risk creditors, but not for high risk creditors.

## AdaBoost Classifier
|               |    pre   |    rec   |    spe    |    f1     |  geo      |   iba     |  sup    |
| :-------------|:---------|:---------|:----------|:----------|:----------|:----------|:--------|
|  high_risk    |   0.08   |   0.91   |   0.94    |  0.14     |   0.93    |   0.85    |     87  |
|   low_risk    |   1.00   |   0.94   |   0.91    |  0.97     |   0.93    |   0.86    |  17118  |
|avg / total    |   0.99   |   0.94   |   0.91    |  0.97     |   0.93    |   0.86    |  17205  |

The accuracy score is 92.6% which is really high. Precision, recall, and f1 score for low risk and recall for high risk is high (100%, 94%, 97%, 91%), but the precision and f1 score is low for high risk (8%, 14%).

AdaBoost Classifier is a good model for classifying low risk creditors but not high risk creditors.