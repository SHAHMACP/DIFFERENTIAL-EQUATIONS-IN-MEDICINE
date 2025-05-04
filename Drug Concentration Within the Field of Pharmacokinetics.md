# **Drug Concentration Within the Field of Pharmacokinetics**

## **Drug Concentration in Single Compartment System**

Mathematical models in pharmacokinetics often describe the evolution of pharmacological processes in terms of systems of linear or non-linear ordinary differential equations. These models help in determining the appropriate dosing regimen to maintain a constant drug level in the patient's body. They reveal limiting values for the minimum and maximum concentration of the drug at any given time.

We need to determine the time interval between drug doses such that the drug concentration doesn't become dangerously high or ineffectively low. The goal is to interpret these ODEs and draw qualitative conclusions about the pharmacological process being modeled. Such models assist in optimizing patient dosing and streamlining pharmaceutical research.

---

### **History**

A known case involves **Tylenol**, a commonly used pain reliever since the 1950s. According to the CDC, between 2001 and 2010, Tylenol poisoning resulted in around 1,600 deaths in the U.S., becoming the most common cause of acute hepatic failure. The FDA provides dosage and frequency guidelines.

This situation is a classic problem in pharmacokinetics modeled using first-order differential equations.

---

### **Drug Dose Provided Periodically**

Let \$y = y(t)\$ be the quantity of drug in the patient’s body at time \$t\$. Suppose initially at \$t = 0\$, a dose \$y\_0\$ is administered. The drug decays exponentially:

$$
\frac{dy}{dt} = -ky
$$

Solving gives:

$$
y = y_0 e^{-kt}
$$

After a time interval \$T\$, another dose \$y\_0\$ is added. At \$t = T\$,

$$
y(T) = y_0 + y_0 e^{-kT}
$$

At \$t = 2T\$,

$$
y(2T) = y_0 + (y_0 + y_0 e^{-kT}) e^{-kT} = y_0 (1 + e^{-kT} + e^{-2kT})
$$

Generalizing, at \$t = nT\$:

$$
y(nT) = y_0 (1 + e^{-kT} + e^{-2kT} + \ldots + e^{-nkT})
$$

This is a geometric progression:

$$
y(nT) = y_0 \left( \frac{1 - e^{-(n+1)kT}}{1 - e^{-kT}} \right)
$$

As \$n \to \infty\$:

$$
y \to \frac{y_0}{1 - e^{-kT}}
$$

If the required concentration is \$y\_c\$, then:

$$
y_c = \frac{y_0}{1 - e^{-kT}} \Rightarrow y_0 = y_c (1 - e^{-kT})
$$

Thus, periodic dosing maintains concentration within a safe range.

At the end of the first interval \$T\$, the concentration is:

$$
y_c e^{-kT}
$$

To restore it to \$y\_c\$, we add dose \$y\_1\$ such that:

$$
y_1 + y_c e^{-kT} = y_c \Rightarrow y_1 = y_c (1 - e^{-kT}) = y_0
$$

This method quickly brings the concentration to the required level but may introduce side effects due to large initial dosing.

> *Graphical Representation of Drug Concentration* ![image](https://github.com/user-attachments/assets/69b97ce4-07f8-413c-8a84-48ca2e342c6b)


---

### **Drug Dose at Regular Intervals**

Suppose a patient receives dose \$y\_0\$ at intervals \$T\$, and the concentration follows:

$$
\frac{dy}{dt} = -k e^y
$$

Solving gives:

$$
y = -\log(kT + c)
$$

Before second dose:

$$
y_1 = -\log(kT + e^{-y_0})
$$

Before third dose:

$$
y_2 = -\log(kT + e^{-(y_0 + y_1)}) = -\log(kT(1 + e^{-y_0}) + e^{-2y_0})
$$

Before fourth dose:

$$
y_3 = -\log(kT + e^{-(y_0 + y_2)}) = -\log(kT(1 + e^{-y_0} + e^{-2y_0}) + e^{-3y_0})
$$

In general:

$$
y_n = -\log\left(kT \left( \frac{1 - e^{-ny_0}}{1 - e^{-y_0}} \right) + e^{-ny_0} \right)
$$

As \$n \to \infty\$, let \$y\_n \to y\_c\$:

$$
y_c = -\log \left( \frac{kT}{1 - e^{-y_c}} \right)
$$

Hence,

$$
T = \frac{e^{-y_c}}{k} (1 - e^{-y_c})
$$

This is the time required to reach target concentration \$y\_c\$ after the first dose.

---

## **Concentration of a Drug in a Two-Compartment System**

Compartmental models estimate how drugs are distributed and eliminated in the body. A two-compartment model considers two regions (e.g., blood and tissues) with different elimination rates.

> *Diagram of Two-Compartment System * ![image](https://github.com/user-attachments/assets/7c3ef55b-ee12-442d-b755-222255e4f765)


Let \$V\_1\$, \$V\_2\$ be the volumes, \$g(t)\$ and \$b(t)\$ be the drug masses in compartments 1 (GI tract) and 2 (bloodstream). Area of the membrane is \$A\$.

* Flow from blood to GI: \$a\_{2\_1} \cdot \frac{A b(t)}{V\_2}\$
* Flow from GI to blood: \$a\_{1\_2} \cdot \frac{A g(t)}{V\_1}\$

The governing equations:

$$
\frac{dg(t)}{dt} = a_{2_1} \frac{A b(t)}{V_2} - a_{1_2} \frac{A g(t)}{V_1}
$$

$$
\frac{db(t)}{dt} = a_{1_2} \frac{A g(t)}{V_1} - a_{2_1} \frac{A b(t)}{V_2} - a \cdot \frac{b(t)}{V_2}
$$

Define:

* \$\beta = a\_{2\_1} \cdot \frac{A}{V\_2}\$
* \$\alpha = a\_{1\_2} \cdot \frac{A}{V\_1}\$
* \$f(t) = \frac{a}{V\_2}\$

Then:

$$
\frac{dg(t)}{dt} = f(t) - \beta g(t)
$$

$$
\frac{db(t)}{dt} = \beta g(t) - \alpha b(t)
$$

To solve, convert to a second-order equation:

Apply operator \$D = \frac{d}{dt}\$:

$$
[D + \beta]g(t) = 0
$$

$$
[D + \alpha]b(t) - \beta g(t) = 0
$$

Multiply first equation by \$\beta\$ and second by \$(D + \beta)\$:

$$
\beta [D + \beta]g(t) = 0
$$

$$
[D + \alpha][D + \beta]b(t) - \beta [D + \beta]g(t) = 0
$$

Add:

$$
[D + \alpha][D + \beta]b(t) = 0 \Rightarrow D^2 + (\alpha + \beta)D + \alpha\beta = 0
$$

Solutions:

$$
D = -\alpha, -\beta
$$

Homogeneous solution:

$$
b_h(t) = A e^{-\alpha t} + B e^{-\beta t}
$$

Particular solution (if \$f(t) = 1\$):

$$
b_p(t) = \frac{1}{\alpha}
$$

Complete solution:

$$
b(t) = A e^{-\alpha t} + B e^{-\beta t} + \frac{1}{\alpha}
$$

This gives the drug amount in blood over time.

---

### **Example: Lidocaine Metabolism**

Lidocaine is used to treat irregular heartbeat. Assume 2 mg is injected into the bloodstream.

Let:

* \$\frac{dg}{dt} = -g(t) + 2\$, with \$g(0) = 0\$
* \$\frac{db}{dt} = -g(t) - b(t)\$, with \$b(0) = 0\$

Solving:

$$
g(t) = 2e^{-t}, \quad b(t) = 2e^{-t}
$$

> *Lidocaine Kinetics Model Diagram* ![image](https://github.com/user-attachments/assets/8bacf035-f3a2-4120-9e20-4c5e2f387530)


---
