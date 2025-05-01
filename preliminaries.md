
# 📘 PRELIMINARIES

An equation involving independent and dependent variables and the derivatives or differentials with one or more dependent variables with respect to one or more independent variables is called a **differential equation**.

---

## 🔢 Different Types and Classification

### 📌 Ordinary Differential Equation (ODE)
A differential equation which involves derivatives with respect to a single independent variable is known as an **ODE**.

### 📌 Partial Differential Equation
A differential equation which contains two or more independent variables and partial derivatives with respect to them is called a **partial differential equation**.

---

## 🧮 Order and Degree

### ✅ Order of a Differential Equation  
The order of the highest derivative involved in a differential equation is called the **order** of the equation.

### ✅ Degree of a Differential Equation  
The degree is the exponent of the highest order derivative after the equation has been simplified to remove radicals and fractions involving derivatives.

---

## 🧷 Linear and Non-linear Differential Equations

A **linear differential equation** is one in which the dependent variable and all its derivatives appear to the first power, and are not multiplied together.  
A differential equation that is not linear is called a **non-linear differential equation**.

A **solution** of a differential equation is a relation between dependent and independent variables (without derivatives) that satisfies the equation.

---

## 🔁 General, Particular, and Singular Solutions

- **General Solution**: Contains as many arbitrary constants as the order of the equation.
- **Particular Solution**: A solution free from arbitrary constants.
- **Singular Solution**: A solution that cannot be derived from the general solution, but still satisfies the equation.

---

## 🔧 Methods of Solving First Order, First Degree Differential Equations

### ➤ Variable Separable  
If the DE can be written as:  
$$f_1(x)dx + f_2(y)dy = 0$$  
then variables are separable, and the solution is:  
$$\int f_1(x)dx + \int f_2(y)dy = c$$

### ➤ Homogeneous Differential Equation  
If:  
$$rac{dy}{dx} = f(x, y) \quad 	ext{where } f(x, y) 	ext{ is homogeneous of degree zero}$$

### ➤ First Order Linear DE  
Equation of the form:  
$$rac{dy}{dx} + Py = Q$$  
Where \( P \) and \( Q \) are constants or functions of \( x \).

---

## 🔁 Second Order Linear Equation

Standard form:  
$$Ay'' + By' + Cy = 0$$

For a homogeneous equation, the characteristic equation:  
$$r^2 + r + 1 = 0$$  
Solving gives general solution \( y_h \).  
Non-homogeneous solution is:  
$$y = y_h + y_p$$

---

## 🧲 Damping in Second Order Systems

Given:  
$$m\ddot{x} + b\dot{x} + kx = 0$$

Characteristic roots:  
$$rac{-b \pm \sqrt{b^2 - 4mk}}{2m}$$

### ➤ Under Damping: \( b^2 < 4mk \)  
$$x(t) = e^{rac{-bt}{2m}}(C_1 \cos(\omega_d t) + C_2 \sin(\omega_d t))$$

### ➤ Over Damping: \( b^2 > 4mk \)  
$$x(t) = C_1 e^{r_1 t} + C_2 e^{r_2 t}$$

### ➤ Critical Damping: \( b^2 = 4mk \)  
$$x(t) = e^{rac{-bt}{2m}}(C_1 + C_2 t)$$

---

## 🧮 Bernoulli Differential Equation

A non-linear DE of the form:  
$$y' + P(x)y = Q(x)y^n, \quad n 
eq 0, 1$$

---

## 🧬 Michaelis–Menten Equation

Used in enzyme kinetics:  
$$
u = rac{V_{max}[S]}{K_m + [S]}$$

Where:  
- \( 
u \): Reaction rate  
- \( V_{max} \): Maximum rate  
- \( K_m \): Substrate concentration at half of \( V_{max} \)

---

## 📉 Root-Mean-Square Deviation (RMSD)

A measure of differences between predicted and observed values:  
$$	ext{RMSD} = \sqrt{ rac{1}{n} \sum (y_i - \hat{y}_i)^2 }$$

---

## 🧠 Levenberg–Marquardt Algorithm (LMA)

Minimizes the sum of squared deviations:  
$$\hat{eta} \in rg \min_{eta} \sum [y_i - f(x_i, eta)]^2$$

---

## 🔗 Difference-Differential Equation

Combines:  
- An ordinary differential equation (ODE)  
- A recurrence (difference) relation

---

## 🌐 Cauchy Problem

A PDE solution problem with specified initial/boundary conditions.

---

## 🪜 Heaviside Step Function

Discontinuous function defined as:  
$$
H(x) =
\begin{cases}
0 & x < 0 \\
1 & x \geq 0
\end{cases}
$$
