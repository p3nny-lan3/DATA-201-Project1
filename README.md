# Project 1:  Kidney Disease Data and Classification  
## By Rin Hwang  
## DATA 205 Statistical Methods in Data Science  

### Kidney Disease Classification (BD-KDD Replication)

This project replicates the baseline classification experiment from the [BD-KDD dataset paper](https://pmc.ncbi.nlm.nih.gov/articles/PMC13092092/), which uses routine lab and vitals data from 988 patients to predict healthy vs. kidney disease.

#### What I did
- Explored and prepped the data (no missing values, all features already numeric)
- Split 80/20 (stratified), then used 5-fold CV on the training set
- Built four classifiers: Logistic Regression, LDA, QDA, and KNN (K chosen with CV)
- Compared them on the test set with confusion matrices, accuracy, precision, recall, specificity, F1, and ROC-AUC

#### Results

| Model | Accuracy | Recall | Specificity | ROC-AUC |
|---|---|---|---|---|
| Logistic Regression | 0.571 | 0.608 | 0.531 | 0.576 |
| LDA | 0.566 | 0.608 | 0.521 | 0.576 |
| QDA | 0.525 | 0.500 | 0.552 | 0.520 |
| KNN | 0.556 | 0.627 | 0.479 | 0.558 |

#### Main finding
All four models did only a little better than a coin flip. The paper reports about 61% accuracy, and my results land in the same weak range. The features (even creatinine and urea) look almost identical between healthy and sick patients, so the models had very little to learn from. My accuracy also swung from 46% to 57% depending on the random split, thus the paper's 61% is skeptical.

Since missing a sick patient is the worst mistake here, recall matters most, and even the best model missed about 40 of 102 sick patients in the test set. I would pick logistic regression for its simplicity and probability outputs, however I would ultimately not use it to diagnose anyone.
