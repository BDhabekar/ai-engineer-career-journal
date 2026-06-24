# Train / Validation / Test Split and Data Leakage

**Date: 23 June 2026**

---

## What is Train/Validation/Test Split?

When building a machine learning model, the dataset is typically divided into three subsets:

### 1. Training Set

Used to train the model and learn patterns from the data.

- Usually 60–80% of the data.
- Model parameters are learned from this set.

Example:

```text
70,000 samples total

Training = 49,000 (70%)
Validation = 10,500 (15%)
Test = 10,500 (15%)
```

---

### 2. Validation Set

Used during model development for:

- Hyperparameter tuning.
- Model selection.
- Early stopping.
- Comparing different algorithms.

The model never learns from the validation set directly.

---

### 3. Test Set

Used only once after the final model is chosen.

Purpose:

- Estimate real-world performance.
- Measure generalization ability.

The test set should remain completely unseen during training and tuning.

---

## Typical Splits

| Training | Validation | Test |
|------------|------------|------|
| 60% | 20% | 20% |
| 70% | 15% | 15% |
| 80% | 10% | 10% |

For very large datasets:

```text
98% Training
1% Validation
1% Test
```

---

## Workflow

```text
Dataset
   │
   ├── Training Set
   │       ↓
   │    Train Model
   │
   ├── Validation Set
   │       ↓
   │ Hyperparameter Tuning
   │
   └── Test Set
           ↓
    Final Performance Evaluation
```

---

# Why Do We Need Three Sets?

If we use only training data:

- The model may memorize the data.
- Training accuracy becomes misleading.

If we tune using the test set:

- We indirectly learn from the test data.
- Test performance becomes overly optimistic.

Therefore:

- Training set → Learn parameters.
- Validation set → Choose hyperparameters.
- Test set → Estimate real-world performance.

---

# What is Data Leakage?

Data leakage occurs when information from outside the training data unintentionally influences model training.

As a result:

- Validation/test accuracy appears very high.
- Real-world performance becomes poor.

It gives the model access to information it would never have during deployment.

---

# Types of Data Leakage

## 1. Train-Test Leakage

Same information appears in both training and test sets.

Example:

```text
Training:
Customer ID 101

Test:
Customer ID 101
```

The model memorizes instead of generalizing.

---

## 2. Preprocessing Before Splitting

Wrong:

```python
scaler.fit(full_dataset)
X_scaled = scaler.transform(full_dataset)

train_test_split(X_scaled)
```

The scaler learns statistics from the test data.

Correct:

```python
X_train, X_test = train_test_split(X)

scaler.fit(X_train)

X_train_scaled = scaler.transform(X_train)
X_test_scaled = scaler.transform(X_test)
```

Only training data should determine preprocessing parameters.

---

## 3. Target Leakage

Using information unavailable at prediction time.

Example:

Predicting:

```text
Will a patient survive?
```

Features include:

```text
Days in ICU
Date of discharge
```

These values are known only after treatment.

The model cheats by seeing the future.

---

## 4. Time-Series Leakage

Randomly shuffling time-series data.

Wrong:

```text
2024 data → train
2023 data → test
```

Future information leaks into the past.

Correct:

```text
Train:
2020-2023

Test:
2024
```

Always preserve chronology.

---

# How to Prevent Data Leakage

### Split First, Preprocess Later

Correct order:

```text
Split Data
      ↓
Fit scaler/imputer on training set
      ↓
Transform validation and test sets
      ↓
Train model
```

---

### Use Pipelines

Scikit-learn pipelines ensure preprocessing uses only training data.

```python
Pipeline([
    ('scaler', StandardScaler()),
    ('model', LogisticRegression())
])
```

---

### Keep Test Set Hidden

Never use the test set for:

- Feature selection.
- Hyperparameter tuning.
- Model comparison.

Use it only once after finalizing the model.

---

### For Time-Series, Respect Time

Train on past data and evaluate on future data.

---

# Interview Answer (1 Minute)

> A dataset is typically split into training, validation, and test sets. The training set is used to learn model parameters, the validation set is used for hyperparameter tuning and model selection, and the test set is used only for final evaluation. Data leakage occurs when information from the validation or test set unintentionally influences training. This causes artificially high performance and poor real-world generalization. Common sources include preprocessing before splitting, target leakage, duplicate samples, and improper handling of time-series data. To avoid leakage, we split first, fit preprocessing only on the training set, use pipelines, and keep the test set completely unseen until final evaluation. 