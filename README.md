# FitzHugh–Nagumo Phase Plane Visualization

This project implements and visualizes the FitzHugh–Nagumo (FHN) model, a two-dimensional reduction of the Hodgkin–Huxley system that captures essential excitability and spiking behavior in neurons.

The current code focuses on generating:

* The phase plane defined by membrane potential (v) and recovery variable (w)
* Streamplots showing the vector field ((dv/dt, dw/dt))
* The nullclines where (dv/dt = 0) and (dw/dt = 0)

The goal is to build a foundation for later extensions such as stability analysis, fixed points, limit cycles, and bifurcation studies.

## Model Equations

The FitzHugh–Nagumo model in this implementation is:

$$
\frac{dv}{dt} = v - \frac{v^3}{3} - w + I_{\text{ext}}
$$

$$
\frac{dw}{dt} = \tau (v + a - bw)
$$

Parameters (a, b, $$\tau$$, $$I_{\text{ext}}$$) control the system’s excitability and timescale separation.

## Code Overview

* `eqn_v(v, w)`: computes (dv/dt)
* `eqn_w(v, w)`: computes (dw/dt)
* A grid is generated using `numpy.meshgrid` to evaluate the vector field
* `matplotlib.pyplot.streamplot` visualizes the flow in the phase plane
* Nullclines are plotted for reference:

  * v-nullcline: (w = v - v^3/3 + $$I_{\text{ext}}$$)
  * w-nullcline: (w = (v + a)/b)

## What the Plot Shows

The phase portrait captures:

* Regions where the membrane potential changes rapidly (fast subsystem)
* Slow evolution of the recovery variable
* The geometry that gives rise to excitability and spike-like trajectories
* Intersections of nullclines indicating potential fixed points

This visual structure is essential for later steps in dynamical systems analysis.

## Planned Extensions

* Identify and classify equilibrium points
* Compute Jacobians and assess stability
* Explore parameter-dependent transitions
* Perform bifurcation analysis (e.g., Hopf, saddle-node)

The current implementation provides a foundation for these analyses by establishing the phase plane and nullcline geometry.

