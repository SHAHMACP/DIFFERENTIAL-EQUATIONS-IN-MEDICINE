# Chapter: Health and Environment

## Dynamics of Tumor Growth

Tumor growth is a complex process ultimately dependent on tumor cells proliferating and spreading in host tissues. The current view of tumor growth kinetics is based on the general assumption that tumor cells grow exponentially (Shackney, 1993). Lower than expected activity of tumor cells and greater than expected aneuploidy have also been consistently found. These issues are of great importance since both radiotherapy and chemotherapy are entirely based on cytokinetics.

Mathematical modeling of tumor growth expresses the dependence of tumor size on time. Given the population of the tumor, let `x` be the number of individual cells at time `t`. It has been observed experimentally that free-living dividing cells, such as bacterial cells, grow at a rate proportional to the volume of dividing cells at that moment:

$\frac{dx}{dt} = \lambda x$

The population `x` is positive and increasing due to various biological factors and mutation, hence:

$\frac{dx}{dt} > 0 \quad \text{and} \quad \lambda > 0 \quad \text{with} \quad x(t_0) = x_0$

Solving using separation of variables, we get:

$x = x_0 e^{\lambda(t - t_0)}$

This model represents the Malthusian Law of population growth, suitable for early-stage tumor development. The parameter $\lambda$ is related to the tumor’s doubling time, given by:

$\ln(2)/\lambda$

### Gompertzian Relation

Solid tumors do not grow exponentially indefinitely. As the tumor becomes larger, the doubling time increases. The Gompertzian model better fits empirical data for such tumors:

$x(t) = x_0 e^{\frac{\lambda}{a} (1 - e^{-at})}$

Where $\lambda$ and `a` are positive constants. This model describes slower growth over time and an upper limit:

$\lim_{t \to \infty} x(t) = x_0 e^{\lambda / a}$

Differentiating:

$\frac{dx}{dt} = \lambda e^{-at} x$

Two interpretations arise:

1. **First Theory**: Retardation is due to increased generation time of reproducing cells (cells age and divide slower).
2. **Second Theory**: Constant generation time, but fewer reproductive cells due to necrosis in the tumor core, as oxygen and nutrients diminish at the center.

### Kuznetsov et al. Model

The tumor cell population is better modeled using a logistic growth equation:

$\frac{dx}{dt} = \alpha x - \beta x^2$

Where:

* $\alpha > 0$ promotes growth
* $\beta > 0$ inhibits growth (e.g., due to treatment)

For small `x`, exponential growth dominates. For large `x`, growth slows due to inhibitory effects.

Solving:

$\frac{dx}{\alpha x - \beta x^2} = dt$

Using partial fractions and initial condition $x(t_0) = x_0$, we get:

$x(t) = \frac{\alpha y_0 e^{\alpha(t - t_0)}}{1 + \beta y_0 e^{\alpha(t - t_0)}}$

Where:

$y_0 = \frac{x_0}{\alpha - \beta x_0}$

As $t \to \infty$, the population stabilizes at:

$x \to \frac{\alpha}{\beta}$

This model is called the **logistic law of cancer tumor growth**.

Kuznetsov et al. further model tumor-immune interactions using ODEs representing effector and tumor cell populations. They demonstrate that:

* A critical threshold exists above which tumor growth is uncontrollable
* Below the threshold, the immune response can maintain the tumor with periodic exacerbations

Stimulating the immune system is shown to improve survival in this model.

![image](https://github.com/user-attachments/assets/7e98b790-5f94-46a1-ad91-c01d5986c23e)

Here's the visual comparison of tumor growth using the Gompertzian model and the Logistic growth model. The Gompertz model reflects the slowing growth as tumors enlarge, while the logistic model shows a saturation effect due to resource limitations.

---

> This mathematical framework provides a strong foundation for understanding tumor growth and potential interventions in medical applications.
