# Cardiovascular System Response Dynamics to Exercise Stress

One of the current applied problems in medicine is predicting heart rate and blood pressure dynamics under exercise stress. This task is crucial in planning rehabilitation after cardiovascular diseases. This chapter presents a mathematical model of heart rate and pressure influenced by physical activity, focusing on modeling pulse and pressure dynamics and identifying relevant parameters.

## Historical Background

Based on similarities between the human cardiovascular system and electrical systems, O. Frank in the early 20th century proposed modeling the cardiovascular system using an electrical circuit. However, due to the relatively low accuracy and complexity of this approach, representing the cardiovascular system with a system of differential equations proves to be a more powerful tool.

A well-known model developed by Grodins uses differential equations to describe the function of a four-chambered heart. This model incorporates Starling's and Bowditch's effects as well as peripheral self-regulation, allowing for the analysis of brain blood pressure and measurements during orthostatic stress.

## Mathematical Model

Clinical studies have identified two main phases of cardiovascular function under exercise stress: the **response period** and the **recovery period**. During the response phase, pulse and pressure increase in proportion to physical activity. In the recovery phase, they return to baseline values.

![image](https://github.com/user-attachments/assets/dc72fdea-a60b-4661-a7eb-6c66e5fedab9)


In the figure above, \( W \) is the load, \( W' \) is the rate of change of load, and \( H, P \) denote heart rate and blood pressure. \( H_0, P_0 \) are their initial values.

The body's response to exercise can be modeled using the **Michaelis–Menten function**, a smooth analog of the Heaviside step function:

$$
M(t) = \frac{W(t)}{1 + W(t)}
$$

This function approaches 1 under high physical load and approaches 0 during rapid decreases in activity. The corresponding recovery process is described as:

$$
R(t) = 1 - M(t - t_0) = 1 - \frac{W(t - t_0)}{1 + W(t - t_0)}
$$

where \( t_0 \) is the delay between unloading and recovery activation.

Since pressure and heart rate changes are proportional to load change \( W'(t) \), their dynamics are described by the following Cauchy problem:

$$
h'(t) = A_1 W'(t) \frac{W(t)}{1 + W(t - t_0)} - \left(1 - \frac{W(t - t_0)}{1 + W(t - t_0)}\right) A_2 h^{A_3}(t)
$$

$$
p'(t) = B_1 W'(t) \frac{W(t)}{1 + W(t - t_0)} - \left(1 - \frac{W(t - t_0)}{1 + W(t - t_0)}\right) B_2 h^{B_3}(t)
$$

with initial conditions:

$$
h(0) = 0, \quad p(0) = 0
$$

Here, \( h = H - H_m \) and \( p = P - P_m \) represent excess heart rate and blood pressure. The constants \( A_1, B_1 \) reflect exercise dynamics; \( A_2, B_2 \) are adaptation rates; and \( A_3, B_3 \) define nonlinearity in adaptation.

## Model Parameter Identification

Parameter identification is performed using the root-mean-square error minimization:

$$
\vec{a} = \arg \min_{\vec{A}} \sum_{j=1}^{N_t} \left[\tilde{h}(\vec{A}, t_j) - (H_j - H_m)\right]^2
$$

$$
\vec{b} = \arg \min_{\vec{B}} \sum_{j=1}^{N_t} \left[\tilde{p}(\vec{B}, t_j) - (P_j - P_m)\right]^2
$$

where \( N_t \) is the number of observation points and \( \tilde{h}, \tilde{p} \) are model solutions with coefficients \( \vec{A}, \vec{B} \) at time \( t_j \).

To minimize the objective function, the **modified Levenberg–Marquardt gradient method** is used, with initial values:

$$
A_1 = \frac{h_3 - h_1}{W_3 - W_1}, \quad A_2 = \frac{h_K - h_{K+2}}{W_3 - W_1}
$$

$$
B_1 = \frac{P_3 - P_1}{W_3 - W_1}, \quad B_2 = \frac{P_K - P_{K+2}}{2 P_K \Delta t}
$$

The nonlinear coefficients \( A_3 \) and \( B_3 \) are selected using exhaustive search, followed by fitting \( A_1, A_2, B_1, B_2 \) using the optimization algorithm.

Considering \( W(t) \approx 1 \), \( R(t - t_0) \approx 0 \) during exercise onset and \( W(t_K) \approx 0 \), \( R(t - t_0) \approx 1 \) during recovery, the differential equations can be simplified and analyzed using approximated difference-differential expressions.

## Model Verification

Model validation was performed using an *ergometer* to measure exercise capacity. Results indicate a decrease in initial heart rate and blood pressure due to rehabilitation and a faster recovery rate when the exercise load is removed.

## Conclusion

A mathematical model of heart rate and blood pressure under physical activity was constructed using differential equations incorporating the Michaelis–Menten law. The model effectively predicts cardiovascular response to controlled physical stress, proving useful in rehabilitation planning.
