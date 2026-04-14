# 📘 Linear Algebra Basics for Machine Learning

## 🧠 1. Matrix
A **matrix** is a rectangular grid of numbers.

Example:
\[
A =
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}
\]

- Rows = data points  
- Columns = features  

👉 In ML: datasets are matrices.

---

## 📦 2. Vectors
A **vector** is a matrix with one row or column.

Example:
\[
x =
\begin{bmatrix}
5 \\
6
\end{bmatrix}
\]

👉 In ML:
- Represents a data point or weights

---

## ➕ 3. Matrix Addition
Add element-wise (same size only)

Example:
\[
A + B =
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}
+
\begin{bmatrix}
5 & 6 \\
7 & 8
\end{bmatrix}
=
\begin{bmatrix}
6 & 8 \\
10 & 12
\end{bmatrix}
\]

---

## ✖️ 4. Matrix Multiplication
\[
A (m \times n) \cdot B (n \times p) = C (m \times p)
\]

Example:
\[
\begin{bmatrix}
1 & 2
\end{bmatrix}
\cdot
\begin{bmatrix}
3 \\
4
\end{bmatrix}
= 1×3 + 2×4 = 11
\]

👉 In ML:
\[
y = Xw
\]

---

## 🔁 5. Transpose
Flip rows ↔ columns

\[
A =
\begin{bmatrix}
1 & 2
\end{bmatrix}
\quad
A^T =
\begin{bmatrix}
1 \\
2
\end{bmatrix}
\]

---

## 📏 6. Dot Product
Multiply corresponding elements and sum.

Example:
\[
[1,2,3] \cdot [4,5,6] = 1×4 + 2×5 + 3×6 = 32
\]

👉 Measures similarity

---

## 📉 7. Identity Matrix
\[
I =
\begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix}
\]

Property:
\[
AI = A
\]

---

## 🔄 8. Inverse
\[
A^{-1}
\]

Example:
\[
A =
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}
\]

👉 Used in:
\[
w = (X^T X)^{-1} X^T y
\]

---

## 📊 9. Determinant
For:
\[
A =
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
\]

\[
\det(A) = ad - bc
\]

Example:
\[
\det =
(1×4 - 2×3) = -2
\]

👉 If determinant = 0 → no inverse

---

## 🧭 10. Eigenvalues & Eigenvectors
\[
Av = \lambda v
\]

Example idea:
Matrix scales vector without changing direction.

👉 Used in PCA

---

# ➕ 11. Linear Combination
A **linear combination** is combining vectors using scalars.

Example:
\[
v = c_1 v_1 + c_2 v_2
\]

\[
v_1 =
\begin{bmatrix}
1 \\
0
\end{bmatrix}
,\quad
v_2 =
\begin{bmatrix}
0 \\
1
\end{bmatrix}
\]

\[
2v_1 + 3v_2 =
\begin{bmatrix}
2 \\
3
\end{bmatrix}
\]

👉 Core idea in ML: predictions are linear combinations of features.

---

# 🧩 12. Span
The **span** of vectors = all possible linear combinations.

Example:
- Vectors (1,0) and (0,1) span **entire 2D space**
- Vectors (1,1) only span a **line**

👉 In ML:
- Determines what your model can represent

---

# 🧮 13. Rank (Bonus)
Rank = number of independent vectors in a matrix.

Example:
\[
\begin{bmatrix}
1 & 2 \\
2 & 4
\end{bmatrix}
\]

Rank = 1 (rows are dependent)

👉 In ML:
- Low rank = redundant features

---

# 🚀 Big Picture in ML

- Data → Matrix (X)
- Weights → Vector (w)
- Prediction → Xw
- Learning → adjusting w

---

# 🧠 Intuition

Matrices = transformations  
Vectors = points  
ML = transforming data to get predictions
