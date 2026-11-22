# Robust Text Classification Using Domain Generalization: A Multi-Dataset Study

## Overview

This repository provides the replication package for the research paper **"Robust Text Classification Using Domain Generalization: A Multi-Dataset Study."**

The study investigates cross-dataset generalization for spam and ham text classification using character-level text representations and classical machine learning classifiers. A Leave-One-Dataset-Out (LODO) evaluation framework is used to assess model performance on completely unseen target datasets.

The experiments use three publicly available datasets, two character-level feature extraction methods, and three machine learning classifiers.

## Datasets

The study uses the following datasets:

1. **Spam-Ham Dataset**
2. **SMS Spam Collection**
3. **SpamAssassin Dataset**

Each dataset serves once as the unseen target domain. Dataset download sources and preparation instructions are provided in the `data/README.md` file.

*Note: The original datasets are not included in this repository. Users should download them from their respective sources and follow the preparation instructions.*

## Methodology

### Text Representation

Two character-level feature extraction methods are investigated:

- Character-level Count Vectorization
- Character-level TF-IDF Vectorization

### Machine Learning Classifiers

The following classifiers are evaluated:

- Logistic Regression
- Linear Support Vector Classifier (LinearSVC)
- Stochastic Gradient Descent (SGD) Classifier

Class imbalance is handled at the classifier level using `class_weight='balanced'`.

### Experimental Design: LODO

Three Leave-One-Dataset-Out experiments are conducted:

| Experiment | Training datasets | Unseen target dataset |
|---|---|---|
| LODO-1 | Spam-Ham + SMS Spam Collection | SpamAssassin |
| LODO-2 | SpamAssassin + SMS Spam Collection | Spam-Ham |
| LODO-3 | Spam-Ham + SpamAssassin | SMS Spam Collection |

The target dataset is excluded from model training and hyperparameter optimization in each experiment.

## Evaluation Metrics

Model performance is evaluated using:

- Accuracy
- Macro F1-score
- Confusion matrix parameters: TP, TN, FP, and FN


```
## Repository Contents

This repository contains three Jupyter notebooks corresponding to the three Leave-One-Dataset-Out (LODO) experiments:

- `LODO_1.ipynb` – SpamAssassin as the unseen target dataset.
- `LODO_2.ipynb` – Spam-Ham Dataset as the unseen target dataset.
- `LODO_3.ipynb` – SMS Spam Collection as the unseen target dataset.

Each notebook includes the relevant preprocessing, feature extraction, model training, and evaluation procedures.

*The structure above represents the recommended organization of the replication package.*

## Requirements

- Python [specify version]
- NumPy
- Pandas
- Scikit-learn
- SciPy
- Optuna
- Matplotlib

The complete dependency list and package versions are provided in `requirements.txt`.


## Running the Experiments

1. Download the three datasets from their original sources.
2. Follow the instructions in `data/README.md` to prepare the datasets.
3. Install the required Python dependencies.
4. Open the corresponding notebook in the `notebooks/` directory.
5. Execute the notebook cells in sequence to run the respective LODO experiment.
6. Review the generated evaluation metrics and confusion matrices.

## Results

The repository provides the evaluation results for all three LODO settings, including Accuracy, Macro F1-score, and confusion matrix parameters.

The reported results can be compared with Tables III and IV in the research paper.

## Reproducibility

The source code, preprocessing procedures, feature extraction settings, classifier configurations, and evaluation scripts are provided to support independent verification and reproduction of the experiments.

All three LODO settings maintain the unseen target dataset separately from model training and hyperparameter optimization.

## Research Context

This repository provides the experimental implementation and replication materials for a study on cross-dataset spam and ham text classification using character-level features and a Leave-One-Dataset-Out (LODO) evaluation framework.

## License

No license has been specified for this repository.
