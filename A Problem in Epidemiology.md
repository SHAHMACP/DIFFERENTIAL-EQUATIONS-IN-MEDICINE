# A Problem in Epidemiology

An important problem in biology and medicine involves the occurrence, spread, and control of a contagious disease, i.e., one that can be transmitted from one individual to another. The science that deals with this study is called **epidemiology**. If a large portion of the population contracts the disease, we say that there is an **epidemic**. 

The goals of epidemiologists are to:

- Understand the causes of a disease  
- Predict its progression  
- Develop methods for its control, including comparisons of various possible strategies

## History

The study of infectious disease data began with the work of **John Graunt** in his 1662 book, _Natural and Political Observations Made upon the Bills of Mortality_. He analyzed the various causes of death and developed a method to estimate the comparative risks of dying from different diseases.

What is typically regarded as the first mathematical model in epidemiology was developed by **Daniel Bernoulli** in his work on smallpox inoculation. In the eighteenth century, smallpox was endemic. Other valuable contributions later emerged concerning **cholera**.

## Mathematical Modeling

To study the spread of a disease, we divide the total population into three groups:

- $S(t)$: the number of susceptible individuals  
- $I(t)$: the number of infected individuals  
- $R(t)$: the number of recovered (or removed) individuals

This model is called the **SIR model**, and it is based on the following assumptions:

1. The total population $N$ is constant, so:  
   $$ N = S(t) + I(t) + R(t) $$
2. The disease spreads through contact between susceptible and infected individuals.
3. Infected individuals recover at a constant rate.

The model is described by the following system of differential equations:

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

- $\beta$ is the **transmission rate**
- $\gamma$ is the **recovery rate**

These equations show how individuals move between the compartments over time due to infection and recovery.

## Interpretation

- The first equation means that susceptible individuals become infected at a rate proportional to both $S$ and $I$.
- The second equation captures both the new infections and the recovery of individuals.
- The third equation reflects the increase in recovered individuals due to the recovery of infected ones.

## Use of the Model

Such models can help us answer:

- Will the disease die out or become an epidemic?
- What proportion of the population will eventually be infected?
- How effective is a vaccination program?

This kind of mathematical modeling is essential in public health decision-making, especially during outbreaks such as influenza, Ebola, or COVID-19.

---
