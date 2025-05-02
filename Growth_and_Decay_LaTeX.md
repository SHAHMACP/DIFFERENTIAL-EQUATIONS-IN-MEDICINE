
# GROWTH AND DECAY

## MALTHUSIAN LAW OF GROWTH

The initial value problem

$$
\frac{dx}{dt} = kx, \quad x(t_0) = x_0
$$

where \( t \) and \( x \) are variables and \( k \) is a non-zero constant, occurs in many physical theories involving either growth or decay. The constant \( k \) can be obtained from the solution of the differential equation by using a subsequent measurement of the population at a time \( t_1 > t_0 \). The constant \( k \) is called the continuous growth rate if it is positive, or the continuous decay rate if it is negative.

There are many quantities in the real world that approximately obey such an equation — population of animals, radioactivity, temperature of cooling body, amount of substance remaining during a reaction, etc.

Solving the equation generally:

$$
\frac{dx}{dt} = kx \Rightarrow \frac{dx}{x} = kdt
$$

Integrating,

$$
\ln x = kt + c \Rightarrow x = Ce^{kt}
$$

Depending on whether \( k \) is positive or negative, the quantity \( x \) grows or decays with respect to \( t \).

![image](https://github.com/user-attachments/assets/47f32bf2-8f42-4394-8f76-b0e7c75894da)


The fundamental differential equation

$$
\frac{dx}{dt} = kx
$$

with solution

$$
x = Ce^{kt}
$$

is called the **Malthusian law of growth**, named after T. R. Malthus (1766–1834).

### Example

Bacteria in a certain culture increase at a rate proportional to the number present. If the number doubles in one hour, how long does it take for the number to triple?

**Solution**:

Let \( y \) denote the number present at time \( t \). Then,

$$
\frac{dy}{dt} = ky, \quad y(0) = y_0, \quad y(1) = 2y_0
$$

Integrating:

$$
\frac{dy}{y} = kdt \Rightarrow \ln y = kt + c \Rightarrow y = Ce^{kt}
$$

Using the initial condition 
$y(0) = y_0 \Rightarrow C = y_0$
, and 
$y(1) = 2y_0 \Rightarrow 2y_0 = y_0 e^k \Rightarrow k = \ln 2$

Thus,

$$
y = y_0 e^{t \ln 2}
$$

Now for tripling:

$$
3y_0 = y_0 e^{t \ln 2} \Rightarrow \ln 3 = t \ln 2 \Rightarrow t = \frac{\ln 3}{\ln 2} \approx 1.5849 \text{ hr}
$$

---

## BIOLOGICAL GROWTH — VERHULST-PEARL MODEL


A fundamental problem in biology is that of growth — whether it is the growth of a cell, an organ, a human, a plant, or a population.

We already have the fundamental differential equation

$$
\frac{dN}{dT} = kN
$$

with the solution

$$
N = N_0 e^{kt}
$$

One obvious drawback of the Malthusian law of growth is that if $k > 0$, then $N \to \infty$ as $t \to \infty$, meaning that growth is unlimited. This conflicts with reality. After a certain period of time, we know that a cell or individual stops growing, having attained a maximum size. So, we modify the equation to better reflect biological constraints.

Suppose $N$ denotes the size of a cell, and assume that the rate of change of size depends on the size in a more complex way than simple proportionality. That is, let

$$
\frac{dN}{dT} = F(N), \quad N(0) = N_0
$$

where $N_0$ represents the size at some specified initial time $t = 0$, and $F$ is an appropriate function. Since the linear function $F(N) = kN$ is not adequate, we consider a quadratic approximation:

$$
F(N) = aN - bN^2
$$

Here, $b > 0$ is chosen to inhibit growth as $N$ becomes large — a condition demanded by biological reality.


To model growth with a limiting size (realistic in biological contexts), we use:

$$
\frac{dN}{dt} = aN - bN^2, \quad N(0) = N_0
$$

This is called the **logistic equation** and the growth governed is **logistic growth**. The model is known as the **Verhulst-Pearl model**.

Separating variables:

$$
\int \frac{1}{aN - bN^2} dN = \int dt
$$

Using partial fractions:

$$
\frac{1}{a} \left[ \ln N - \ln(a - bN) \right] = t + c
$$

![image](https://github.com/user-attachments/assets/34623869-cb21-4115-a8a4-0791692ffd1f)

Solving for N, we get the **Verhulst formula**:

$$
N(t) = \frac{\frac{a}{b}}{1 + \left( \frac{\frac{a}{b}}{N_0} - 1 \right)e^{-at}}
$$

As $t \to \infty$, the population approaches a maximum:

$$
N_{\text{max}} = \frac{a}{b}
$$

If values \( N_0, N_1, N_2 \) at times \( 0, 1, 2 \) respectively are known, then:

![image](https://github.com/user-attachments/assets/3afdfc4c-b52b-4c03-a5ec-343568eb4790)

$$
e^{-a} = \frac{N_0(N_2 - N_1)}{N_2(N_1 - N_0)}
$$

and

$$
\frac{b}{a} = \frac{N_1^2 - N_0 N_2}{N_1(N_0 N_1 - 2N_0 N_2 + N_1 N_2)}
$$

Hence the limiting value of \( N \) is:

$$
N_{\text{max}} = \frac{N_1(N_0 N_1 - 2N_0 N_2 + N_1 N_2)}{N_1^2 - N_0 N_2}
$$

![image](https://github.com/user-attachments/assets/e9f9b973-b045-4f09-a633-efbaa7623f35)


This **logistic curve** is S-shaped and includes a point of inflection at which the growth rate starts to slow down.

### Example

Predict mean size of adult human cell using given data:

| Stage | Size |
|-------|------|
| Birth | 19.4 |
| 1     | 31.3 |
| 2     | 34.5 |
| 3     | 37.2 |
| 4     | 40.3 |
| 5     | 43.9 |
| 6     | 48.1 |
| 7     | 52.5 |
| 8     | 56.8 |

Taking \( N_0 = 19.4, N_1 = 40.3, N_2 = 56.8 \), we find:

$$
N_{\text{max}} = 66.9
$$

This is the predicted adult size of a human cell.
