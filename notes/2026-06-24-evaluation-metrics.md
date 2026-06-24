# Evaluation Metrics: Accuracy, Precision, Recall, F1 Score, ROC-AUC

**Date: 23 June 2026**

---

# What is Accuracy?

Accuracy measures the proportion of correctly classified samples out of all samples.

### Formula

```text
Accuracy = (TP + TN)/(TP + TN + FP + FN)
```

where:

- TP = True Positives
- TN = True Negatives
- FP = False Positives
- FN = False Negatives

### Example

Suppose:

```text
TP = 80
TN = 10
FP = 5
FN = 5
```

Then:

```text
Accuracy = (80 + 10)/(80 + 10 + 5 + 5)
         = 90/100
         = 90%
```

### When to Use

- Balanced datasets.
- Equal importance of false positives and false negatives.

### Limitation

Accuracy can be misleading for imbalanced datasets.

Example:

```text
99 healthy patients
1 sick patient
```

Predicting everyone as healthy gives:

```text
Accuracy = 99%
```

but the model completely fails to detect disease.

---

# What is Precision?

Precision measures how many predicted positive samples are actually positive.

### Formula

```text
Precision = TP/(TP + FP)
```

### Example

Suppose:

```text
TP = 90
FP = 10
```

Then:

```text
Precision = 90/(90 + 10)
          = 90%
```

### Interpretation

Out of all positive predictions, 90% are correct.

### When to Use

When false positives are costly.

Examples:

- Spam detection
- Fraud detection
- Email filtering

---

# What is Recall?

Recall measures how many actual positive samples are correctly identified.

### Formula

```text
Recall = TP/(TP + FN)
```

### Example

Suppose:

```text
TP = 90
FN = 30
```

Then:

```text
Recall = 90/(90 + 30)
       = 75%
```

### Interpretation

The model detected 75% of all actual positives.

### When to Use

When false negatives are costly.

Examples:

- Cancer diagnosis
- Disease detection
- Intrusion detection
- Manufacturing defect detection

---

# Precision vs Recall

Precision answers:

> Out of all predicted positives, how many are actually positive?

Recall answers:

> Out of all actual positives, how many did we find?

### Tradeoff

Increasing recall often decreases precision and vice versa.

Example:

Lowering the classification threshold:

```text
More samples predicted positive
↓
Recall increases
↓
Precision decreases
```

---

# What is F1 Score?

F1 Score is the harmonic mean of precision and recall.

### Formula

```text
F1 = 2 × Precision × Recall/(Precision + Recall)
```

Alternative form:

```text
F1 = 2TP/(2TP + FP + FN)
```

### Example

Suppose:

```text
Precision = 0.8

Recall = 0.6
```

Then:

```text
F1 = 2×0.8×0.6/(0.8+0.6)
   = 0.686
```

### Why Harmonic Mean?

The harmonic mean penalizes imbalance.

Example:

```text
Precision = 1.0
Recall = 0.1
```

F1 remains low because one metric is poor.

### When to Use

- Imbalanced datasets.
- Need to balance precision and recall.

---

# What is ROC-AUC?

ROC stands for:

```text
Receiver Operating Characteristic
```

A ROC curve plots:

```text
True Positive Rate (Recall)
vs
False Positive Rate
```

where:

```text
TPR = TP/(TP + FN)

FPR = FP/(FP + TN)
```

### AUC

AUC stands for:

```text
Area Under the Curve
```

ROC-AUC measures how well the model separates positive and negative classes across all thresholds.

### Interpretation

| ROC-AUC | Performance |
|----------|-------------|
| 1.0 | Perfect classifier |
| 0.9–1.0 | Excellent |
| 0.8–0.9 | Good |
| 0.7–0.8 | Fair |
| 0.5 | Random guessing |
| < 0.5 | Worse than random |

### When to Use

- Comparing classifiers.
- Threshold-independent evaluation.
- Imbalanced datasets.

---

# Confusion Matrix

```text
                  Actual

               Positive   Negative
Pred Positive      TP         FP

Pred Negative      FN         TN
```

All classification metrics are derived from the confusion matrix.

---

# Accuracy vs Precision vs Recall vs F1 vs ROC-AUC

| Metric | Formula | Best Used When |
|----------|---------|----------------|
| Accuracy | (TP+TN)/(Total) | Balanced data |
| Precision | TP/(TP+FP) | False positives are costly |
| Recall | TP/(TP+FN) | False negatives are costly |
| F1 Score | Harmonic mean of Precision and Recall | Imbalanced data |
| ROC-AUC | Area under ROC curve | Comparing classifiers |

---

# Interview Answer (1 Minute)

> Accuracy measures the overall percentage of correct predictions, but it can be misleading for imbalanced datasets. Precision tells us how many predicted positives are actually positive, whereas recall measures how many actual positives are successfully detected. F1 score is the harmonic mean of precision and recall and is useful when both metrics are important. ROC-AUC evaluates how well a classifier separates classes across different thresholds and provides a threshold-independent measure of performance. All these metrics are derived from the confusion matrix, and the choice of metric depends on the problem and the relative costs of false positives and false negatives.