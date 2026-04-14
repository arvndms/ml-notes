# 📘 Linear Algebra Basics for Machine Learning

---

## 🧠 1. Matrix

A matrix is a rectangular grid of numbers.

**Example:**

```
A = [[1, 2],
     [3, 4]]
```

👉 In ML:

* Rows → data points
* Columns → features

---

## 📦 2. Vectors

A vector is a single row or column.

**Example:**

```
x = [5, 6]^T
```

👉 Used for:

* Data points
* Model weights

---

## ➕ 3. Matrix Addition

```
A = [[1, 2],
     [3, 4]]

B = [[5, 6],
     [7, 8]]

A + B = [[6, 8],
         [10, 12]]
```

---

## ✖️ 4. Matrix Multiplication

```
[1, 2] × [3, 4]^T = 1×3 + 2×4 = 11
```

👉 In ML:

```
y = Xw
```

---

## 🔁 5. Transpose

```
A  = [1, 2]
Aᵀ = [1,
      2]
```

---

## 📏 6. Dot Product

```
[1, 2, 3] · [4, 5, 6] = 32
```

👉 Measures similarity

---

## 📉 7. Identity Matrix

```
I = [[1, 0],
     [0, 1]]
```

```
A · I = A
```

---

## 🔄 8. Inverse (Idea)

Used to "undo" a matrix.

👉 In ML:

```
w = (XᵀX)⁻¹ Xᵀy
```

---

## 📊 9. Determinant

For:

```
A = [[a, b],
     [c, d]]
```

```
det(A) = ad - bc
```

**Example:**

```
(1×4 - 2×3) = -2
```

👉 If det = 0 → no inverse

---

## ➕ 10. Linear Combination

Combining vectors using scalars.

```
v1 = [1, 0]
v2 = [0, 1]

2v1 + 3v2 = [2, 3]
```

👉 ML idea: predictions = weighted sum of features

---

## 🧩 11. Span

Span = all possible linear combinations.

* v1 = [1,0], v2 = [0,1] → span = entire 2D space
* v1 = [1,1] → span = a line

---

## 🧮 12. Rank

Number of independent rows/columns.

```
[[1, 2],
 [2, 4]]
```

Rank = 1 (dependent)

👉 In ML:

* Low rank = redundant features

---

## 🧭 13. Eigenvalues & Eigenvectors (Idea)

```
Av = λv
```

👉 Matrix scales vector without changing direction

Used in:

* PCA (dimensionality reduction)

---

# 🚀 Big Picture

* Data → matrix (X)
* Weights → vector (w)
* Prediction → Xw
* Learning → adjusting w

---

# 🧠 Intuition

* Vectors = points
* Matrices = transformations
* ML = transforming data into predictions
