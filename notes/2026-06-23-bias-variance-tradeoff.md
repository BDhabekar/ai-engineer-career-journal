# Bias-Variance Trade-off

**Date: 23 June 2026**

---

## What’s the Bias-Variance Trade-off?

The bias-variance trade-off describes the balance between:

### Bias
Error caused by overly simplistic assumptions.

- High bias → model cannot capture patterns well.
- Example: Linear regression fitting nonlinear data.

### Variance
Error caused by sensitivity to training data.

- High variance → model learns noise and small fluctuations.
- Example: Deep decision tree memorizing the training set.

The goal is to find a model complex enough to capture the true pattern but simple enough to generalize to unseen data.

|                 | High Bias | High Variance |
|-----------------|-----------|---------------|
| Complexity      | Low       | High          |
| Training Error  | High      | Very Low      |
| Test Error      | High      | High          |
| Generalization  | Poor      | Poor          |
| Problem         | Underfitting | Overfitting |

---

## How is this Trade-off Related to Overfitting and Underfitting?

### Underfitting (High Bias, Low Variance)

- Model is too simple.
- Performs poorly on both training and test sets.
- Cannot capture underlying relationships.

Example:

```text
Training Accuracy = 70%
Validation Accuracy = 68%
```

Both are poor → **Underfitting**.

---

### Overfitting (Low Bias, High Variance)

- Model is too complex.
- Fits training data extremely well.
- Fails to generalize to new data.

Example:

```text
Training Accuracy = 99%
Validation Accuracy = 82%
```

Large gap → **Overfitting**.

---

## How Do You Know Your Model is High Variance, Low Bias? What Would You Do?

### Symptoms

- Very low training error.
- Much higher validation/test error.
- Large train-test performance gap.

Example:

```text
Training Accuracy = 99%
Validation Accuracy = 84%
```

This indicates:

- **Low bias** (training error is low).
- **High variance** (generalization error is large).

### Remedies

#### 1. Collect More Training Data

More data reduces variance.

#### 2. Regularization

Increase:

- L1 (Lasso)
- L2 (Ridge)
- Weight decay

#### 3. Reduce Model Complexity

- Shallower tree
- Fewer neurons/layers
- Lower polynomial degree

#### 4. Early Stopping

Stop training before memorization begins.

#### 5. Dropout (Neural Networks)

Randomly deactivate neurons during training.

#### 6. Ensemble Methods

- Bagging
- Random Forest
- Averaging predictions

---

## How Do You Know Your Model is Low Variance, High Bias? What Would You Do?

### Symptoms

- High training error.
- Validation error close to training error.
- Small train-validation gap.

Example:

```text
Training Accuracy = 75%
Validation Accuracy = 73%
```

This indicates:

- **High bias** (can't fit training data well).
- **Low variance** (similar performance on unseen data).

### Remedies

#### 1. Increase Model Complexity

- Add features.
- Increase polynomial degree.
- Use deeper networks.

#### 2. Reduce Regularization

Strong regularization may make the model too simple.

#### 3. Train Longer

More epochs may help.

#### 4. Use a More Expressive Algorithm

Examples:

- Linear Regression → Random Forest
- Logistic Regression → XGBoost
- Simple Neural Network → Deep Neural Network

#### 5. Feature Engineering

Create informative features and transformations.

---

# Interview Answer (1 Minute)

> The bias-variance trade-off is the balance between underfitting and overfitting. High bias means the model is too simple and cannot learn the underlying pattern, leading to underfitting. High variance means the model is too complex and becomes sensitive to training data, causing overfitting. I diagnose bias and variance by comparing training and validation performance. If training error is low and validation error is much higher, the model has high variance, and I reduce complexity or add regularization. If both training and validation errors are high and similar, the model has high bias, and I increase model complexity or improve features. The objective is to minimize total generalization error by balancing bias and variance. 