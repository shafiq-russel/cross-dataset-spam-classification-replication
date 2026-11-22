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

