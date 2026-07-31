# [Linear Regression]

**Type: Supervised | Task: Regression | Family: Model

---

## Introduction to [Linear Regression]

Linear Regression is a **model-based supervised learning algorithm** used for **regression** tasks (predicting continuous numerical values).  
  
It predicts an output by multiplying each feature by its learned **weight (slope)**, summing them together, and adding a **bias (intercept)**.  
  
The model learns the best weights and bias by **minimizing the Mean Squared Error (MSE)** between the predicted values and the actual values.  
  
> **Intuition**: Imagine each feature casts a vote on the final prediction. The weight determines how strong that vote is, and the bias gives the prediction a starting value.

---

## [Parameter Tuning] 

For linear regression there is no parameter tuning.


> **Note: It will come in later stages of Ridge and Lasso regression


---

## Math (light)

**[Formula name]:**Mean Squared Error(MSE)

## Mean Squared Error (MSE)

### Formula

$$
\boxed{
\text{MSE}=\frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2
}
$$

### Where

| Symbol | Meaning |
|--------|---------|
| $n$ | Number of data points |
| $y_i$ | Actual (true) value |
| $\hat{y}_i$ | Predicted value |
| $(y_i-\hat{y}_i)^2$ | Squared error for a single data point |

---

### How MSE is Calculated

1. Predict the output for every training example.
2. Calculate the error:

   $$
   \text{Error} = \text{Actual} - \text{Predicted}
   $$

3. Square each error.
4. Add all the squared errors.
5. Divide by the total number of data points.

---

### Why MSE Matters

During **training**, the model repeatedly:

```text
Predict
    ↓
Calculate MSE
    ↓
Adjust weights & bias
    ↓
Predict again
```

The goal is to make the **MSE as small as possible** or **there is no significant decrease in the MSE** by finding the best weights and bias.

> **Important:** MSE is used to **guide learning** during training. During testing, it may be calculated only to **evaluate** the model—it is **not** used to update the weights.

---

### Intuition

Think of **MSE as the model's "mistake score."**

- **High MSE** → Predictions are far from the actual values.
- **Low MSE** → Predictions are close to the actual values.
- **MSE = 0** → Perfect predictions.

> **Why it matters:** During training, the model calculates the MSE to measure how wrong its predictions are. If the MSE is large, it adjusts the **weights** and **bias** to reduce the MSE. This process repeats until the model finds the best weights and bias.
---

## Strength, Weakness and Parameters

### Parameters

**No hyperparameters to tune** in basic Linear Regression.

---

### Strength

- Simple and easy to understand.
- Fast to train and make predictions.
- Works well when the relationship between features and target is approximately linear.
- Model is highly interpretable (weights show the effect of each feature).

---

### Weakness

- Assumes a linear relationship between features and the target.
- Sensitive to outliers.
- Can overfit when number of features increase by a lot.
- Can underfit complex, non-linear datasets.
- Performance may decrease if features are highly correlated (multicollinearity).

---

## When to Use

✅ Predicting continuous values (house prices, salaries, sales), when the relationship is approximately linear, and when model interpretability is important.

❌ Complex non-linear relationships, datasets with many outliers, or problems where a more flexible model (e.g., Decision Trees or Random Forests) performs better.

---

## Personal Notes

Concept of Multicollinearity : 
https://dilipkumar.medium.com/multicollinearity-and-regularization-in-regression-models-25c24b9107a7



[[Ridge Regression]]