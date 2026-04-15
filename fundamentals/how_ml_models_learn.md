# 🤖 How Machine Learning Models Use Linear Algebra

---

## 🧠 1. Do All ML Models Work the Same Way?

### ✔️ Many models follow this pattern:

* Start with **weights (parameters)**
* Make predictions
* Compare with actual values
* Update weights to reduce error

**Examples:**

* Linear Regression
* Logistic Regression
* Neural Networks

---

### ❗ Some models work differently:

* Decision Trees → rule-based splits
* k-NN → compares distances (no training phase)
* Random Forest → combination of trees

---

## 📦 2. Data Representation

Each feature is a **scalar (number)**:

```text
age = 25
salary = 50000
experience = 3
```

One data row becomes a **vector**:

```text
x = [25, 50000, 3]
```

Multiple rows form a **matrix**:

```text
X = [
 [25, 50000, 3],
 [30, 60000, 5],
 [22, 45000, 2]
]
```

---

## ⚖️ 3. Weights (Parameters)

Weights are also scalars:

```text
w = [0.2, 0.0001, 1.5]
```

* Same weights are applied to all rows
* Learned during training

---

## ✖️ 4. Prediction = Linear Combination

For one row:

```text
y = x · w
```

Expanded:

```text
y = (0.2 × 25) + (0.0001 × 50000) + (1.5 × 3)
```

👉 This is a **linear combination of features**

---

## 🔁 5. Multiple Predictions (Matrix Form)

```text
y = Xw
```

* Each row produces one output
* Output is a vector:

```text
y_pred = [y1, y2, y3]
```

---

## 🎯 6. Comparing with Actual Values

```text
y_true = [t1, t2, t3]
```

Each prediction is compared with its target.

---

## 📉 7. Loss Function (Error Across All Rows)

We don’t evaluate rows individually — we compute **total error**:

```text
Loss = ( (y1 - t1)^2 + (y2 - t2)^2 + (y3 - t3)^2 ) / 3
```

👉 This is **Mean Squared Error (MSE)**

---

## 🔄 8. How Weights Are Updated

Weights start randomly:

```text
w = [0.1, -0.3, 0.5]
```

Then updated using:

```text
w = w - learning_rate × gradient
```

👉 Gradient is computed using **all rows together**

---

## ⚠️ 9. Important Insight

* The model does **not** try to be perfect for each row
* It tries to minimize **overall error**

👉 Because:

* Data may be noisy
* Different rows may conflict

---

## 🧠 10. Intuition

* Each row = one data example
* Model = one formula
* Same formula applied to all rows

Think of it like:

```text
price = (area × w1) + (rooms × w2)
```

* Formula stays same
* Inputs change

---

## ⚖️ 11. Training vs Prediction

### During Training:

* Data = fixed
* Weights = updated

### During Prediction:

* Weights = fixed
* Data = new inputs

---

## 🔥 12. Key Takeaways

* Features → scalars
* Row → vector
* Dataset → matrix
* Prediction → linear combination
* Training → adjusting weights

---

## ✅ Final Summary

```text
Weights start randomly and are updated using the combined error from all rows, allowing the model to learn the best parameters that minimize overall loss.
```
