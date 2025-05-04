# A Problem in Epidemiology

An important problem in biology and medicine involves the occurrence, spread, and control of a contagious disease, i.e., one that can be transmitted from one individual to another. The science that deals with this study is called **epidemiology**. If a large portion of the population contracts the disease, we say that there is an **epidemic**.

The goals of epidemiologists are to:

- Understand the causes of a disease  
- Predict its progression  
- Develop methods for its control, including comparisons of various possible strategies  

---

## History

The study of infectious disease data began with the work of **John Graunt** in his 1662 book, *Natural and Political Observations Made upon the Bills of Mortality*. He analyzed various causes of death and developed a method to estimate the comparative risks of dying from different diseases.

What is typically regarded as the first mathematical model in epidemiology was developed by **Daniel Bernoulli** in his work on smallpox inoculation. In the 18th century, smallpox was endemic, and Bernoulli introduced a mathematical model to support the benefits of vaccination. Later, in the 19th century, **William Farr** and **John Snow** made notable contributions, particularly during the cholera epidemics in London.

---

## Mathematical Modeling of Infectious Diseases

To understand how a disease spreads and to design interventions, mathematical models are used. One of the simplest and most well-known models is the **SIR model**, which divides the total population into three compartments:

- $S(t)$: the number of **Susceptible** individuals at time $t$
- $I(t)$: the number of **Infected** individuals at time $t$
- $R(t)$: the number of **Recovered (or Removed)** individuals at time $t$

The total population is assumed to be constant:

$$
N = S(t) + I(t) + R(t)
$$

This assumes no births, deaths (unrelated to disease), or migrations.

---

## The SIR Model Equations

The dynamics of the model are governed by the following system of ordinary differential equations:

$$
\frac{dS}{dt} = -\beta S I
$$

$$
\frac{dI}{dt} = \beta S I - \gamma I
$$

$$
\frac{dR}{dt} = \gamma I
$$

Where:

- $\beta$ is the **transmission rate** (rate at which susceptible individuals become infected upon contact with infected individuals)
- $\gamma$ is the **recovery rate** (rate at which infected individuals recover and move into the recovered compartment)

---

## Interpretation of the Equations

### Susceptible ($S$):
The equation
$$\frac{dS}{dt} = -\beta S I $$
indicates that the susceptible population decreases as individuals become infected. The rate of new infections is proportional to both the susceptible and infected populations.

### Infected ($I$):
The equation
$$\frac{dI}{dt} = \beta S I - \gamma I$$
describes the rate of change of infected individuals. It increases due to new infections and decreases as infected individuals recover.

### Recovered ($R$):
The equation
$$\frac{dR}{dt} = \gamma I$$
indicates that the number of recovered individuals increases as infected individuals recover at rate $\gamma$.

---

## Basic Reproduction Number ($R_0$)

The **basic reproduction number** $R_0$ is defined as:

$$R_0 = \frac{\beta}{\gamma}$$

It represents the average number of secondary infections produced by a single infected individual in a fully susceptible population.

- If $R_0 > 1$: the infection can spread in the population.
- If $R_0 < 1$: the infection will die out over time.

---

## Applications of the SIR Model

- **Predicting the peak** of infection and timing
- **Estimating the impact** of interventions like quarantine, vaccination, and social distancing
- **Modeling real epidemics** such as measles, influenza, and COVID-19
- **Public health policy**: using mathematical analysis to determine the proportion of the population that must be vaccinated to prevent an outbreak

---

## Limitations

While the SIR model provides insights, it has limitations:

- Assumes **homogeneous mixing** of the population
- Ignores **incubation periods** (can be resolved using SEIR models)
- Assumes **permanent immunity**
- Assumes **no births or deaths** during the outbreak

---

## Conclusion

Mathematical models like the SIR model help understand the dynamics of disease transmission and design effective control strategies. While simple, they form the basis for more complex models used in modern epidemiology.

---

## References

- Hethcote, H. W. (2000). The Mathematics of Infectious Diseases. SIAM Review, 42(4), 599–653.
- Kermack, W. O., & McKendrick, A. G. (1927). A Contribution to the Mathematical Theory of Epidemics. Proceedings of the Royal Society A.

Thanks for sharing the complete section! Now everything is clear — both the **example** and the **table** are present and well-formatted. Here's a quick summary of the added elements you asked about:

---

### **Example Section Summary**:

* **Context**: A flu virus spreads in a hostel of 1000 students.
* **Differential Equation Used**:

  $$\frac{dN_i}{dt} = k N_i (N - N_i)$$
* **Initial and known conditions**: $N(0) = 1$, $N(4) = 50$
* **Solution**: Logistic function:

  $$N(t) = \frac{1000}{1 + 999e^{-0.9906t}}$$
* **Final result**: After 6 days, 276 students are infected.

---

### **Table** of Calculated Values:

| t (Days) | N (Infected Students) |
| -------- | --------------------- |
| 4        | 50 (observed)         |
| 5        | 124                   |
| 6        | 276                   |
| 7        | 507                   |
| 8        | 735                   |
| 9        | 882                   |
| 10       | 953                   |

---

### **Logistic Curve**:

![image](https://github.com/user-attachments/assets/1dc7f11c-4f7f-43d8-91ec-740f90722c6e)

