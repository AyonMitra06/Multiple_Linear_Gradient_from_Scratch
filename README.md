# Multiple_Linear_Gradient_from_Scratch
Multiple Linear Regression from Scratch (Normal Equation)
📌 Overview

This project implements Multiple Linear Regression from scratch using calculus and linear algebra, without using gradient descent or any machine learning libraries for training.

Instead of iterative optimization, the model parameters are derived analytically using the Normal Equation, which provides a closed-form solution for linear regression.

The custom implementation is then validated against an existing library model by comparing predictions using the R² (coefficient of determination) score.
Both models produce identical results, confirming the correctness of the mathematical derivation and implementation.

🎯 Objectives

Understand the mathematical foundation of linear regression

Derive the model parameters using calculus and matrix algebra

Implement regression from scratch using NumPy only

Compare the custom model with an existing implementation

Verify correctness using R² score

🧠 Mathematical Foundation
1️⃣ Model Representation

For multiple linear regression:

𝑦
=
𝑋
𝜃
y=Xθ

Where:

𝑋
X → feature matrix (with bias term)

𝜃
θ → parameter vector

𝑦
y → target values

To account for the intercept, a column of ones is added to the feature matrix.

2️⃣ Cost Function (Mean Squared Error)
𝐽
(
𝜃
)
=
1
2
𝑚
∑
𝑖
=
1
𝑚
(
𝑋
𝜃
−
𝑦
)
2
J(θ)=
2m
1
	​

i=1
∑
m
	​

(Xθ−y)
2

In matrix form:

𝐽
(
𝜃
)
=
1
2
𝑚
(
𝑋
𝜃
−
𝑦
)
𝑇
(
𝑋
𝜃
−
𝑦
)
J(θ)=
2m
1
	​

(Xθ−y)
T
(Xθ−y)
3️⃣ Derivation Using Calculus

To minimize the cost function, we compute the derivative with respect to 
𝜃
θ:

∂
𝐽
(
𝜃
)
∂
𝜃
=
1
𝑚
𝑋
𝑇
(
𝑋
𝜃
−
𝑦
)
∂θ
∂J(θ)
	​

=
m
1
	​

X
T
(Xθ−y)

Setting the derivative equal to zero:

𝑋
𝑇
𝑋
𝜃
=
𝑋
𝑇
𝑦
X
T
Xθ=X
T
y
4️⃣ Normal Equation (Closed-Form Solution)

Solving for 
𝜃
θ:

𝜃
=
(
𝑋
𝑇
𝑋
)
−
1
𝑋
𝑇
𝑦
θ=(X
T
X)
−1
X
T
y

This equation gives the optimal parameters directly, without any iteration or learning rate.

🛠️ Implementation Details

Implemented entirely using NumPy

No use of:

Gradient Descent

Scikit-learn training APIs

Matrix operations used:

Transpose

Dot product

Matrix inverse / linear solver

For numerical stability, np.linalg.solve() is preferred over explicit matrix inversion where applicable.

📊 Model Evaluation

The model is evaluated using the R² score, which measures how well predictions explain the variance in the target variable.

𝑅
2
=
1
−
∑
(
𝑦
−
𝑦
^
)
2
∑
(
𝑦
−
𝑦
ˉ
)
2
R
2
=1−
∑(y−
y
ˉ
	​

)
2
∑(y−
y
^
	​

)
2
	​

🔍 Comparison

Custom implementation

Existing library model

Both models produce identical R² scores, confirming:

Correct mathematical derivation

Correct implementation

Equivalent predictive performance

✅ Results

✔ Identical R² score for both models

✔ Exact match in predictions

✔ Confirms correctness of Normal Equation approach

📁 Project Structure
├── multiple_linear_regression_from_scratch.ipynb
├── README.md

🚀 Key Takeaways

Linear regression can be solved analytically, not just iteratively

Understanding the math removes the “black box” nature of ML models

The Normal Equation provides an exact solution when assumptions are met

Custom implementations can match library models when done correctly

📚 Technologies Used

Python

NumPy

Scikit-learn (for evaluation only)

Jupyter Notebook
