# 🚀 HyperTune SearchLab

## 🔍 GridSearchCV vs RandomizedSearchCV

A practical machine learning project comparing **GridSearchCV** and **RandomizedSearchCV** for hyperparameter optimization using the **Telco Customer Churn** dataset.

---

## 🎯 Project Objective

The goal of this project is to systematically optimize a Random Forest classifier and compare:

- Untuned baseline model
- GridSearchCV
- RandomizedSearchCV
- Cross-validation performance
- Search time
- Number of model fits
- Held-out test performance

---

## 📊 Dataset

**Dataset:** Telco Customer Churn

- Records: 7,043
- Target: `Churn`
- `Yes` → 1
- `No` → 0
- `customerID` removed
- `TotalCharges` converted to numeric
- Categorical features encoded using One-Hot Encoding

An untouched **20% test set** was kept separate from the hyperparameter search.

---

## 🌲 Model

The project uses:

**Random Forest Classifier**

Hyperparameters optimized:

- `n_estimators`
- `max_depth`
- `min_samples_split`
- `min_samples_leaf`

Evaluation metric:

**F1-Score**

---

## 🔎 GridSearchCV

GridSearchCV evaluated all predefined combinations.

- Parameter combinations: **54**
- Cross-validation folds: **5**
- Total model fits: **270**
- Best CV F1-Score: **0.5877**
- Search time: **58.66 seconds**

Best parameters:

```text
max_depth = 10
min_samples_leaf = 2
min_samples_split = 10
n_estimators = 300


| Model              | Accuracy | Precision | Recall | F1-Score |
| ------------------ | -------: | --------: | -----: | -------: |
| Baseline           |   0.7925 |    0.6376 | 0.5080 |   0.5655 |
| GridSearchCV       |   0.7953 |    0.6414 | 0.5214 |   0.5752 |
| RandomizedSearchCV |   0.7910 |    0.6351 | 0.5027 |   0.5612 |


📊 Improvement Over Baseline

| Model              | F1 Improvement |
| ------------------ | -------------: |
| Baseline           |         0.0000 |
| GridSearchCV       |        +0.0097 |
| RandomizedSearchCV |        -0.0043 |



⚖️ GridSearchCV vs RandomizedSearchCV

In this experiment, both methods used the same number of model fits.

GridSearchCV achieved a slightly higher cross-validation F1-score and also required slightly less search time.

However, this result is specific to this experiment and does not mean GridSearchCV is always better.

When to use GridSearchCV

GridSearchCV is useful when:

The hyperparameter space is relatively small.
All important combinations can be evaluated.
Computational resources are sufficient.
A systematic search is preferred.
When to use RandomizedSearchCV

RandomizedSearchCV is useful when:


The hyperparameter space is large.
Parameters have continuous or wide ranges.
Full grid evaluation is computationally expensive.
A fixed computational budget is available.

Randomized search can explore a wider search space without evaluating every possible combination.


🧠 Key Learnings
Hyperparameter tuning can improve model performance over an untuned baseline.
Cross-validation provides a more reliable estimate during model selection.
GridSearchCV evaluates every combination in the predefined grid.
RandomizedSearchCV samples a fixed number of configurations.
The held-out test set should remain untouched during hyperparameter optimization.
Search strategy should consider both model performance and computational cost.


🛠️ Technologies Used
Python
Pandas
NumPy
Scikit-learn
SciPy
Matplotlib
Jupyter Notebook


📁 Project Structure

HyperTune-SearchLab/
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
├── hyperparameter_optimization.ipynb
├── README.md
├── requirements.txt
└── .gitignore



👩‍💻 Author

Madhumita Khatua

Machine Learning / Data Science Intern
