# DETECTION OF DIABETES

The human body needs to maintain a level of glucose concentration that is not too high in order for it to function properly. In order for glucose to be produced and utilized, insulin production and utilization must occur. If insulin is not produced, or not enough of it is produced, then proper glucose levels cannot be maintained, which leads to the disease of diabetes. Diabetes mellitus is a condition in which there is too much glucose in our blood.

In diabetes, the body is unable to burn off all its sugar, starches, and carbohydrates due to an insufficient supply of insulin. 
Diabetes is usually diagnosed by fasting and postprandial blood tests or by the Glucose Tolerance Test (GTT). In GTT, the patient after fasting overnight is given a large dose of glucose, and during the next three to five hours, several measurements are made of the concentration of glucose in the patient's blood.

In the mid-sixties, Dr. Rosevear, Dr. Molnar, Dr. Ackerman, and Dr. Gatewood discovered a criterion for interpreting the results of GTT. Their model is based on the following simple and well-known facts of elementary biology:

* Glucose is a source of energy for all tissues and organs. For each individual, there is an optimal blood glucose concentration. Any excessive deviations from this optimal concentration lead to severe pathological conditions and potential death.
* Blood glucose levels are influenced and controlled by various hormones and metabolism such as:

  1. **Insulin**: A hormone secreted by \$\beta\$ cells of the pancreas. After absorbing carbohydrates, the pancreas secretes more insulin. In addition, the glucose in the blood directly stimulates the \$\beta\$ cells to secrete insulin. Insulin facilitates the tissue uptake of glucose. Without sufficient insulin, the body cannot have all the energy it needs.

  2. **Glucagon**: A hormone secreted by the \$\alpha\$ cells of the pancreas. Excess glucose is stored in the liver as glycogen and when needed this glycogen is converted back into glucose. Glucagon increases the rate of breakdown of glycogen into glucose. Hypoglycemia (low blood sugar) and fasting promote glucagon secretion, while high blood glucose levels suppress it.

  3. **Epinephrine (adrenaline)**: Secreted by the adrenal medulla, it quickly increases blood glucose levels during extreme hypoglycemia. It increases the breakdown of glycogen into glucose and inhibits glucose uptake by muscle tissues. It also inhibits insulin secretion and helps convert lactate to glucose in the liver.

  4. **Glucocorticoids**: Hormones like cortisol, secreted by the adrenal cortex, which play a key role in carbohydrate metabolism.

  5. **Thyroxine**: Secreted by the thyroid gland. It helps the liver form glucose from non-carbohydrate sources like glycerol, lactate, and amino acids.

  6. **Growth hormone (somatotropin)**: Secreted by the anterior pituitary gland. It decreases muscle and adipose tissue sensitivity to insulin, reducing insulin's effectiveness.

---

## Mathematical Model

The model postulated is a simple one, requiring only a limited number of blood samples during a GTT. It centers on two concentrations:

* \$G\$: Glucose in the blood
* \$H\$: Net hormonal concentration

The latter represents the cumulative effect of important hormones. Insulin is considered to increase \$H\$ while cortisone decreases it.

The basic model:

$$
\frac{dG}{dt} = F_1(G, H) + J(t)
$$

$$
\frac{dH}{dt} = F_2(G, H)
$$

where \$J(t)\$ is the external rate at which blood glucose concentration is being increased.

Assume that by the time a fasting patient arrives at the hospital, \$G\$ and \$H\$ have reached equilibrium values \$G\_0\$ and \$H\_0\$:

$$
F_1(G_0, H_0) = 0 = F_2(G_0, H_0)
$$

We now define deviations:

* \$G = G\_0 + g\$
* \$H = H\_0 + h\$

where \$g\$ and \$h\$ are small.

Then,

$$
\frac{dg}{dt} = f_1(g, h) + J(t)
$$

$$
\frac{dh}{dt} = f_2(g, h)
$$

Assume \$f\_1\$ and \$f\_2\$ are linear:

$$
\frac{dg}{dt} = -ag - bh + J(t)
$$

$$
\frac{dh}{dt} = -ch + eg
$$

Constants:

* \$a > 0\$: glucose is consumed by tissues
* \$b > 0\$: hormones help reduce glucose
* \$c > 0\$: hormone concentration drops over time
* \$e > 0\$: increased glucose causes hormone secretion

From the above, solve for \$h\$:

$$
h = \frac{1}{b} \left[ -ag + J - \frac{dg}{dt} \right]
$$

Substitute into \$dh/dt\$:

$$
\frac{d^2g}{dt^2} + (a + c) \frac{dg}{dt} + (ac + be)g = \frac{dJ}{dt} + cJ
$$

Since \$J(t)\$ is nonzero only for a short interval, for \$t > 0\$:

$$
\frac{d^2g}{dt^2} + (a + c) \frac{dg}{dt} + (ac + be)g = 0
$$

Let \$A = \frac{a + c}{2}\$ and \$B = \sqrt{ac + be}\$.

If \$A^2 - B^2 < 0\$ (underdamped case), then the solution is:

$$
g(t) = e^{-At} \left[ C \cos(B_0 t) + D \sin(B_0 t) \right]
$$

where \$B\_0 = \sqrt{B^2 - A^2}\$.

Then the complete solution becomes:

$$
G(t) = G_0 + e^{-At} \left[ C \cos(B_0 t) + D \sin(B_0 t) \right]
$$

To find the constants:

* \$G\_0\$ is the fasting glucose level.
* Take four measurements: \$G\_1, G\_2, G\_3, G\_4\$ at times \$t\_1, t\_2, t\_3, t\_4\$

Then:

$$
G_i = G_0 + e^{-At_i} \left[ C \cos(B_0 t_i) + D \sin(B_0 t_i) \right], \quad i = 1, 2, 3, 4
$$

Alternatively, take \$n\$ measurements and apply **least squares fitting** to find the best-fit parameters using a computer.

Observation:

* Small errors in \$G\$ can cause large errors in \$A\$.
* \$B\_0\$ is relatively stable and can describe the GTT response.

Define:

$$
t_0 = \frac{2\pi}{B_0}
$$

* If \$t\_0 < 4\$ hours → Normal response
* If \$t\_0 > 4\$ hours → Indicates mild diabetes

---

