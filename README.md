# Titanic Survival Prediction

## Problem Statement
Predict which Titanic passengers survived from details such as class, sex, age and fare. Kaggle competition "Titanic - Machine Learning from Disaster", framed as binary classification.

Kaggle notebook: [paste your Kaggle notebook link]

## Dataset
- `data/train.csv`: 891 labelled passengers; `data/test.csv`: 418 passengers
- Features: Pclass, Sex, Age, SibSp, Parch, Fare, Embarked

## Approach
- Dropped Cabin (~77% missing), Ticket, PassengerId and Name
- Imputed Age and Fare with the mean, Embarked with the most frequent value; one-hot encoded Sex and Embarked
- Compared a Decision Tree (depth tuned 2 to 12), a Random Forest (301 trees, max_depth=6) and a PyTorch ANN (3 hidden layers of 16 units, ReLU, Adam, BCEWithLogitsLoss, best checkpoint by validation loss)

## Results
| Model | Accuracy |
|---|---|
| Decision Tree | 80.45% (hold-out) |
| Random Forest | 80.45% (hold-out) |
| ANN, 3 hidden layers | 82.12% (hold-out), 85.98% (validation) |

**Kaggle public leaderboard score (ANN submission): 0.78708**

The leaderboard score is lower than my hold-out accuracy because it is measured on Kaggle's hidden test set.

## Final Submission
I submitted the ANN because [your actual reason]. Its hold-out lead over the tree models was small (about 3 of 179 samples), so I treat the models as close in performance.

## Notes
The notebook was built on Kaggle, so data paths point to `/kaggle/input/...`; change them to `data/train.csv` and `data/test.csv` to run locally. The ANN is unseeded, so exact numbers vary between runs.
