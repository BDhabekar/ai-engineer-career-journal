# Linear Regression and Logistic Regression

**Date: 24 June 2026**

---

# What is Linear Regression?

Linear Regression is a **supervised machine learning algorithm used for regression problems**, where the objective is to predict a continuous numerical value by modeling the relationship between one or more input features and a target variable.

It assumes that the target variable can be expressed as a linear combination of the input features and learns the parameters that best fit the training data.

### Mathematical Model

For one feature:

```text
ŷ = wx + b
```

For multiple features:

```text
ŷ = w₀ + w₁x₁ + w₂x₂ + ... + wₙxₙ
```

where:

- ŷ = predicted value
- x = input feature(s)
- w = weights (coefficients)
- b = bias (intercept)

### Applications

- House price prediction
- Sales forecasting
- Temperature prediction
- Demand forecasting

### Example

```text
Area = 2000 sq.ft

Predicted Price = ₹75 Lakhs
```

Linear Regression predicts **continuous numerical values**.

---

# What is Logistic Regression?

Logistic Regression is a **supervised machine learning algorithm used for classification problems**, primarily binary classification. It estimates the probability that an input belongs to a particular class by applying the sigmoid function to a linear combination of the input features.

Instead of predicting continuous values, it predicts probabilities between 0 and 1, which are converted into class labels.

### Mathematical Model

Linear part:

```text
z = wx + b
```

Sigmoid function:

```text
ŷ = σ(z) = 1/(1 + e⁻ᶻ)
```

where:

- ŷ = probability of class 1
- x = input feature(s)
- w = weights
- b = bias

### Applications

- Spam Detection
- Fraud Detection
- Disease Diagnosis
- Customer Churn Prediction

### Example

```text
P(Spam | Email Features) = 0.92
```

Since:

```text
0.92 > 0.5
```

Prediction:

```text
Spam
```

Logistic Regression predicts **probabilities and class labels**, not continuous values.

---

# Cost Function of Linear Regression

Linear Regression uses **Mean Squared Error (MSE)**:

```text
J(w,b) = (1/2m) Σ(ŷ-y)²
```

where:

- m = number of samples
- y = actual value
- ŷ = predicted value

Objective:

```text
Minimize J(w,b)
```

---

# Cost Function of Logistic Regression

Logistic Regression uses **Binary Cross-Entropy Loss**:

```text
J(w,b)=-(1/m)Σ[ylog(ŷ)+(1-y)log(1-ŷ)]
```

Objective:

```text
Minimize J(w,b)
```

Cross-entropy is preferred because MSE produces a non-convex optimization problem for logistic regression.

---

# Gradient Descent

Gradient Descent is an optimization algorithm that iteratively updates parameters to minimize the cost function.

General update rule:

```text
w = w − α ∂J/∂w

b = b − α ∂J/∂b
```

where:

- α = learning rate

---

# Gradient Descent for Linear Regression

Predictions:

```text
ŷ = wx+b
```

Gradients:

```text
∂J/∂w = (1/m)Σ(ŷ-y)x

∂J/∂b = (1/m)Σ(ŷ-y)
```

Update equations:

```text
w = w − α(1/m)Σ(ŷ-y)x

b = b − α(1/m)Σ(ŷ-y)
```

---

# Gradient Descent for Logistic Regression

Predictions:

```text
ŷ = σ(wx+b)
```

Gradients:

```text
∂J/∂w = (1/m)Σ(ŷ-y)x

∂J/∂b = (1/m)Σ(ŷ-y)
```

Update equations:

```text
w = w − α(1/m)Σ(ŷ-y)x

b = b − α(1/m)Σ(ŷ-y)
```

Although the update equations look similar, the predictions and cost functions are different.

---

# Linear Regression vs Logistic Regression

| Feature | Linear Regression | Logistic Regression |
|-----------|----------------|----------------|
| Problem Type | Regression | Classification |
| Output | Continuous Value | Probability/Class |
| Range | (-∞,+∞) | (0,1) |
| Activation Function | None | Sigmoid |
| Cost Function | MSE | Cross-Entropy |
| Example | House Price Prediction | Spam Detection |
| Decision Boundary | No | Yes |

---

# Interview Answer (1 Minute)

> Linear regression is a supervised learning algorithm used for regression problems where the goal is to predict continuous numerical values. It models the relationship between features and target variables using a linear equation and minimizes Mean Squared Error using gradient descent. Logistic regression is a supervised learning algorithm used mainly for classification problems. It computes the probability of a class by applying the sigmoid function to a linear combination of features and uses cross-entropy loss for optimization. Both algorithms use gradient descent to learn the optimal parameters, but linear regression predicts continuous values whereas logistic regression predicts class probabilities.