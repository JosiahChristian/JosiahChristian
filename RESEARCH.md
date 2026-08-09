# Computational Modeling & Intelligent Systems Research Workspace

This document serves as a developing research notebook connecting mathematical models, computational experiments, software implementations, and future research questions across my engineering portfolio.

The central research theme is the study of **complex evolving systems**: systems whose internal state changes over time, is only partially observable, is influenced by uncertainty or disturbance, and may require prediction, adaptation, or control.

Current application domains include:

- cyber-physical and autonomous systems,
- aerospace dynamics,
- computational biophysics,
- digital twins,
- physics-informed machine learning,
- reinforcement-learning robustness, and
- adaptive computational modeling.

The purpose of this workspace is not to present completed research conclusions. It documents mathematical foundations, implementation mappings, hypotheses, and research directions that can be tested and refined as the associated software develops.

---

# 1. Unifying Mathematical Perspective

Many of the systems represented across this portfolio can be expressed through a dynamical-system formulation:

$$
\dot{\mathbf{x}}(t)
=
f\left(
\mathbf{x}(t),
\mathbf{u}(t),
\mathbf{w}(t),
\boldsymbol{\theta},
t
\right)
$$

where:

- $\mathbf{x}(t)$ represents the internal system state,
- $\mathbf{u}(t)$ represents control inputs,
- $\mathbf{w}(t)$ represents disturbances or uncertain external influences,
- $\boldsymbol{\theta}$ represents model parameters, and
- $f(\cdot)$ defines the governing dynamics.

Measurements may provide only an incomplete representation of that state:

$$
\mathbf{y}(t)
=
h\left(
\mathbf{x}(t)
\right)
+
\mathbf{v}(t)
$$

where $\mathbf{v}(t)$ represents measurement noise or observational uncertainty.

This provides a common conceptual framework for several projects:

```text
Physical / Simulated System
            ↓
       Observations
            ↓
      State Estimation
            ↓
    Predictive Model
            ↓
 Uncertainty Assessment
            ↓
 Optimization / Control
            ↓
       New System State
            ↺
```

This feedback structure is central to my developing interest in adaptive digital twins and intelligent computational systems.

---

# 2. Research Development: Adaptive Digital Twins

The `Adaptive-Digital-Twin-Framework` repository is being developed as a theoretical and computational framework for studying systems that continuously reconcile mathematical models with incoming observations.

Current foundations include:

1. dynamical systems,
2. state-space representation,
3. observation and state estimation,
4. machine learning as adaptive dynamics,
5. uncertainty quantification,
6. optimization and intelligent control, and
7. computational architecture.

A general adaptive model can be represented conceptually as:

$$
\hat{\mathbf{x}}_{t+1}
=
f_{\boldsymbol{\theta}_t}
\left(
\hat{\mathbf{x}}_t,
\mathbf{u}_t
\right)
$$

with parameter adaptation:

$$
\boldsymbol{\theta}_{t+1}
=
\boldsymbol{\theta}_t
-
\eta
\nabla_{\boldsymbol{\theta}}
\mathcal{L}
\left(
\mathbf{y}_t,
\hat{\mathbf{y}}_t
\right)
$$

where $\eta$ is an adaptation or learning rate and $\mathcal{L}$ measures disagreement between observations and model predictions.

This formulation motivates a central research question:

> **How can a computational model update its internal state and parameters from observations while remaining physically meaningful, uncertainty-aware, and useful for prediction or control?**

Repository:
`Adaptive-Digital-Twin-Framework`

---

# 3. Physics-Informed Machine Learning

## 3.1 Physics-Constrained Optimization

A conventional supervised model may optimize a data-fitting objective:

$$
\mathcal{L}_{data}
=
\frac{1}{N}
\sum_{i=1}^{N}
\left|
\hat{u}_i-u_i
\right|^2
$$

For systems governed by known physical relationships, an additional residual term can penalize violations of the governing equations:

$$
\mathcal{L}_{total}
=
\mathcal{L}_{data}
+
\lambda
\mathcal{L}_{physics}
$$

where:

$$
\mathcal{L}_{physics}
=
\frac{1}{N_f}
\sum_{i=1}^{N_f}
\left|
\frac{\partial \hat{u}}{\partial t}
+
\mathcal{N}_x[\hat{u}]
\right|^2
$$

and $\mathcal{N}_x$ represents the relevant spatial or physical differential operator.

The physics term does **not** guarantee that a learned solution is correct or globally stable. Rather, it introduces an inductive constraint that penalizes disagreement with specified governing equations at evaluated points.

This can be useful when observational data are sparse, noisy, or expensive to obtain.

### Portfolio Mapping

`AeroDigitalTwin`

Current research themes:

- physics-informed loss functions,
- structural degradation,
- predictive maintenance,
- optimization behavior,
- model convergence, and
- physical consistency of learned predictions.

---

# 4. Fluid Dynamics and Physics-Informed Models

## 4.1 Incompressible Navier-Stokes Constraints

For an incompressible velocity field $\mathbf{u}$:

$$
\frac{\partial \mathbf{u}}{\partial t}
+
(\mathbf{u}\cdot\nabla)\mathbf{u}
=
-\nabla p
+
\nu\nabla^2\mathbf{u}
$$

subject to the incompressibility constraint:

$$
\nabla\cdot\mathbf{u}=0
$$

where:

- $\mathbf{u}$ is the fluid velocity field,
- $p$ is pressure, and
- $\nu$ is kinematic viscosity.

A physics-informed model can construct residuals such as:

$$
\mathbf{r}_{momentum}
=
\frac{\partial \hat{\mathbf{u}}}{\partial t}
+
(\hat{\mathbf{u}}\cdot\nabla)\hat{\mathbf{u}}
+
\nabla\hat{p}
-
\nu\nabla^2\hat{\mathbf{u}}
$$

and:

$$
r_{continuity}
=
\nabla\cdot\hat{\mathbf{u}}
$$

with a physics loss:

$$
\mathcal{L}_{physics}
=
\frac{1}{N_f}
\sum_{i=1}^{N_f}
\left\|
\mathbf{r}_{momentum}^{(i)}
\right\|^2
+
\frac{1}{N_f}
\sum_{i=1}^{N_f}
\left|
r_{continuity}^{(i)}
\right|^2
$$

Automatic differentiation can be used to evaluate the derivatives appearing in these residuals when the approximation is represented by a differentiable neural network.

The residual encourages the learned approximation to satisfy the specified conservation equations at the selected collocation points. Its effectiveness depends on factors including optimization, model capacity, sampling, boundary conditions, and the suitability of the governing model.

---

# 5. Computational Hemodynamics

The `BiomedicalSystemsSolver` explores simplified numerical representations of cardiovascular flow.

A developing one-dimensional velocity formulation is:

$$
\frac{\partial v}{\partial t}
+
v\frac{\partial v}{\partial x}
=
-\frac{1}{\rho}\frac{\partial P}{\partial x}
+
\frac{\mu}{\rho}
\left(
\frac{\partial^2v}{\partial x^2}
+
\frac{1}{R}
\frac{\partial R}{\partial x}
\frac{\partial v}{\partial x}
\right)
$$

where:

- $v(x,t)$ represents axial velocity,
- $P(x,t)$ represents pressure,
- $\rho$ represents fluid density,
- $\mu$ represents dynamic viscosity, and
- $R(x,t)$ represents a spatially or temporally varying vessel radius.

The convective term:

$$
v\frac{\partial v}{\partial x}
$$

captures nonlinear transport of momentum.

The radius-dependent term provides a simplified mechanism for exploring how changes in vessel geometry may influence the modeled velocity field.

This formulation should be understood as a computational approximation rather than a complete clinical model of cardiovascular fluid-structure interaction.

### Computational Mapping

| Simulation quantity | Mathematical quantity | Interpretation |
|---|---|---|
| Velocity | $v(x,t)$ | Axial fluid velocity |
| Pressure | $P(x,t)$ | Modeled pressure field |
| Vessel radius | $R(x,t)$ | Geometric boundary parameter |
| Time step | $\Delta t$ | Numerical integration increment |
| Spatial node | $x_i$ | Discretized vessel position |

Repository:
`BiomedicalSystemsSolver`

---

# 6. Electrophysiological Modeling

## 6.1 Spatial Cable Model

Electrical propagation through excitable tissue can be represented using a cable-type equation:

$$
C_m
\frac{\partial V}{\partial t}
=
\frac{a}{2R_a}
\frac{\partial^2V}{\partial x^2}
-
\sum I_{ion}
$$

where:

- $V(x,t)$ is transmembrane potential,
- $C_m$ is membrane capacitance,
- $a$ is a geometric radius parameter,
- $R_a$ is axial resistance, and
- $I_{ion}$ represents ionic currents.

The spatial derivative:

$$
\frac{\partial^2V}{\partial x^2}
$$

represents spatial variation in membrane voltage and contributes to the propagation of electrical activity along the modeled domain.

---

## 6.2 Hodgkin-Huxley-Type Ionic Dynamics

A more detailed representation introduces voltage-dependent sodium, potassium, and leakage currents:

$$
\frac{a}{2R_a}
\frac{\partial^2V}{\partial x^2}
=
C_m\frac{\partial V}{\partial t}
+
\bar{g}_{Na}m^3h(V-V_{Na})
+
\bar{g}_{K}n^4(V-V_K)
+
g_L(V-V_L)
$$

The gating variables evolve according to first-order kinetic equations:

$$
\frac{dm}{dt}
=
\alpha_m(V)(1-m)
-
\beta_m(V)m
$$

$$
\frac{dh}{dt}
=
\alpha_h(V)(1-h)
-
\beta_h(V)h
$$

$$
\frac{dn}{dt}
=
\alpha_n(V)(1-n)
-
\beta_n(V)n
$$

An example voltage-dependent rate formulation is:

$$
\alpha_n(V)
=
\frac{0.01(V+55)}
{1-\exp(-(V+55)/10)}
$$

and:

$$
\beta_n(V)
=
0.125
\exp
\left(
-\frac{V+65}{80}
\right)
$$

These variables represent idealized channel activation and inactivation dynamics and provide a computational mechanism for generating action-potential-like behavior.

### Portfolio Mapping

`BiomedicalSystemsSolver`

```text
Membrane Parameters
        ↓
Gating-State Evolution
        ↓
Ionic Current Calculation
        ↓
Transmembrane Voltage
        ↓
Numerical Integration
        ↓
Signal Visualization
```

The corresponding browser visualization work in `AeroCPSTelemetry` provides a separate interface layer for displaying electrophysiological signal behavior.

---

# 7. Cyber-Physical Systems and Control

A linearized state-space representation provides a useful foundation for analyzing controlled systems under disturbance:

$$
\dot{\mathbf{x}}(t)
=
\mathbf{A}\mathbf{x}(t)
+
\mathbf{B}\mathbf{u}(t)
+
\mathbf{D}\mathbf{w}(t)
$$

where:

- $\mathbf{x}(t)$ represents system state,
- $\mathbf{u}(t)$ represents control input,
- $\mathbf{w}(t)$ represents disturbance,
- $\mathbf{A}$ describes nominal state evolution,
- $\mathbf{B}$ maps control inputs into the state dynamics, and
- $\mathbf{D}$ maps disturbances into the system.

This representation is useful for reasoning about how environmental disturbances interact with control actions and system dynamics.

### Portfolio Mapping

`AeroCPSSimulation`

| Logged quantity | Mathematical interpretation |
|---|---|
| Flight step | Numerical time increment $\Delta t$ |
| Altitude | Component of system state $\mathbf{x}(t)$ |
| Velocity | State derivative / kinematic quantity |
| Control input | Component of $\mathbf{u}(t)$ |
| Wind disturbance | Component of $\mathbf{w}(t)$ |

This mapping provides a bridge between simulation telemetry and formal state-space reasoning.

---

# 8. Autonomous Planning

`AutonomousPathPlanner` explores a different layer of intelligent cyber-physical behavior: translating environmental information into trajectory decisions.

A simplified planning pipeline can be represented as:

```text
Environment
     ↓
Perception / Obstacle Representation
     ↓
Geometric Collision Evaluation
     ↓
Trajectory Feasibility
     ↓
Waypoint Adjustment
     ↓
Updated Planned Path
```

This project currently emphasizes deterministic geometric reasoning rather than learned planning.

Future research could investigate how deterministic planning, probabilistic state estimation, reinforcement learning, and model-predictive control compare under uncertainty.

---

# 9. Reinforcement Learning Robustness and Adversarial Perturbation

A developing research direction examines the behavior of reinforcement-learning systems when observations are corrupted or intentionally manipulated.

## 9.1 Bounded Observation Perturbation

Let the true state observation at time $t$ be $s_t$.

A perturbed observation can be represented as:

$$
\tilde{s}_t
=
s_t
+
\delta_t
$$

subject to:

$$
\|\delta_t\|_p
\leq
\epsilon
$$

where $\epsilon$ bounds the perturbation magnitude under a selected norm.

A bounded perturbation does not necessarily evade detection or degrade a policy. Instead, it defines an experimentally controlled adversarial region within which robustness can be evaluated.

---

## 9.2 Policy Behavior Under Perturbed Observations

For a policy:

$$
\pi_\theta(a_t\mid\tilde{s}_t)
$$

the policy-gradient objective can be studied under altered observations:

$$
\nabla_\theta J(\theta)
=
\mathbb{E}_{\tau\sim\pi_\theta}
\left[
\sum_{t=0}^{T}
\nabla_\theta
\log
\pi_\theta
(a_t\mid\tilde{s}_t)
Q^{\pi_\theta}(s_t,a_t)
\right]
$$

Potential experimental questions include:

- How does perturbation magnitude affect trajectory performance?
- Which state variables produce the greatest policy sensitivity?
- Can behavioral deviations reveal attacks that remain difficult to detect from raw observations alone?
- How should false-positive and false-negative detection rates be evaluated?
- Can physics-based simulation provide useful reference behavior for anomaly detection?

This direction connects AI engineering, simulation, autonomous systems, and cybersecurity without assuming that a particular detection strategy has already been validated.

### Developing Research Topic

**Detecting Adversarial Data Poisoning Attacks in Reinforcement Learning Models Using High-Fidelity Behavioral Simulation**

Repository:
`Adversarial-RL-Data-Poisoning-Thesis`

---

# 10. Telemetry and Computational Infrastructure

Mathematical models require software infrastructure capable of transporting, validating, processing, storing, and retrieving observations.

`TelemetryPipelineJava` provides a backend engineering layer for this problem.

Current architecture:

```text
Telemetry Source
       ↓
Spring Boot REST API
       ↓
Validation
       ↓
Service Layer
       ↓
BlockingQueue<TelemetryPacket>
       ↓
Asynchronous Processing
       ↓
Spring Data JPA
       ↓
Relational Persistence
```

This project is not itself a mathematical simulation. Instead, it represents infrastructure that could support future computational experiments involving streamed observations or model updates.

That distinction is important: **simulation software represents system behavior; telemetry infrastructure transports and manages information about that behavior.**

Repository:
`TelemetryPipelineJava`

---

# 11. Simulation and Experimental Data Ledger

The following table records current computational scenarios represented across the portfolio.

| Repository | Scenario | Example parameters | Output / log |
|---|---|---|---|
| `AeroCPSSimulation` | Earth flight baseline | $g=-9.81\text{ m/s}^2$ | `test_logs/flight_telemetry_run_history.txt` |
| `AeroCPSSimulation` | Mars gravity experiment | $g=-3.711\text{ m/s}^2$ | `test_logs/flight_telemetry_run_history.txt` |
| `AeroDigitalTwin` | Optimization baseline | Epochs $=50$, learning rate $=10^{-4}$ | `test_logs/learning_test_run_baseline.txt` |
| `AeroDigitalTwin` | Extended convergence run | Epochs $=500$, learning rate $=10^{-3}$ | `test_logs/learning_test_run_converged.txt` |
| `BiomedicalSystemsSolver` | Hemodynamic simulation | Length $=10\text{ cm}$, nodes $=20$ | `output/hemodynamic_velocity_vector.txt` |
| `BiomedicalSystemsSolver` | Electrophysiology simulation | Length $=1\text{ cm}$, nodes $=100$ | `output/transmembrane_potential_volt.txt` |

These logs should be treated as computational artifacts associated with specific model configurations, not as experimental validation by themselves.

---

# 12. Code-to-Model Traceability

A recurring goal across these repositories is to make relationships between software variables and mathematical quantities explicit.

Examples include:

| Software / telemetry quantity | Mathematical quantity | Domain |
|---|---|---|
| `altitude` | state component $x_i(t)$ | Aerospace |
| `velocity` | $\dot{x}(t)$ or $v(t)$ | Aerospace / fluid dynamics |
| `windDisturbance` | $\mathbf{w}(t)$ | CPS control |
| `learningRate` | $\eta$ or $\alpha$ | Optimization |
| `loss` | $\mathcal{L}$ | Machine learning |
| `actionPotential` | $V(x,t)$ | Electrophysiology |
| `cardioVelocity` | $v(x,t)$ | Hemodynamics |

Maintaining this traceability helps distinguish:

- mathematical assumptions,
- numerical approximations,
- implementation variables,
- telemetry outputs, and
- experimental observations.

This separation becomes increasingly important as model complexity increases.

---

# 13. Research Validation Principles

As these projects develop, stronger research claims should be supported through explicit validation rather than inferred from successful execution alone.

Important validation categories include:

### Numerical Verification

Does the implementation correctly solve the mathematical model being specified?

Possible methods:

- convergence studies,
- time-step sensitivity,
- spatial-grid sensitivity,
- comparison with analytical solutions when available,
- conservation checks, and
- regression tests.

### Model Validation

Does the mathematical model adequately represent the phenomenon being studied for its intended purpose?

Possible methods:

- comparison with published reference data,
- parameter sensitivity analysis,
- comparison with established benchmark problems, and
- uncertainty analysis.

### Machine-Learning Evaluation

Does the learned model generalize beyond its training conditions?

Possible methods:

- train/validation/test separation,
- baseline comparisons,
- ablation studies,
- out-of-distribution evaluation,
- uncertainty calibration, and
- repeated experiments.

### Cyber-Physical / Control Evaluation

Does the system remain effective under disturbance, uncertainty, or altered operating conditions?

Possible methods:

- disturbance sweeps,
- robustness testing,
- trajectory error analysis,
- control-effort measurement,
- failure-envelope characterization, and
- Monte Carlo simulation.

---

# 14. Literature Review Tracks

Current literature-review areas include:

### Physics-Informed Machine Learning

Questions:

- When do physics-informed constraints improve generalization?
- How should competing data and physics losses be weighted?
- What failure modes occur when the assumed governing equations are incomplete?
- How should PINNs be compared with conventional numerical solvers?

### Adaptive Digital Twins

Questions:

- What distinguishes a digital model from an adaptive digital twin?
- How should model-state synchronization be quantified?
- Which state-estimation methods are appropriate under partial observability?
- How should uncertainty propagate through predictions and control decisions?

### Cyber-Physical Systems

Questions:

- How should disturbances and uncertainty be represented?
- Which safety properties can be tested computationally?
- How can telemetry support runtime monitoring?
- What is the relationship between simulation verification and physical-system validation?

### Computational Biophysics

Questions:

- Which simplifications are appropriate for educational or exploratory models?
- How sensitive are electrophysiological simulations to gating parameters?
- How do discretization choices affect modeled wave propagation?
- Which hemodynamic assumptions dominate predicted flow behavior?

### Adversarial Reinforcement Learning

Questions:

- Which observation channels are most sensitive to bounded perturbations?
- How should attack success be quantified?
- Can simulated physical behavior provide an independent anomaly signal?
- How robust are detection methods under environmental uncertainty?

---

# 15. Academic Development Mapping

Future coursework can contribute to this research program without assuming in advance that every assignment will become part of a dissertation.

Potential connections include:

- **Simulation fundamentals:** experimental design, discrete-event simulation, verification, and validation.
- **Computer graphics and visualization:** scientific visualization and interactive telemetry interfaces.
- **Machine learning:** adaptive models, uncertainty, representation learning, and robustness.
- **High-performance computing:** parallel simulation, parameter sweeps, ensemble methods, and scalable model execution.
- **Algorithms:** autonomous planning, optimization, and computational complexity.
- **Probability and statistics:** uncertainty quantification, estimation, inference, and experimental analysis.
- **Software engineering:** maintainable research software, testing, architecture, and reproducibility.

The objective is to allow coursework, independent projects, and later graduate research to reinforce one another where the connection is technically meaningful.

---

# 16. Long-Term Research Direction

The broader research trajectory is moving toward computational systems that combine:

$$
\boxed{
\text{Physical Models}
+
\text{Observations}
+
\text{Machine Learning}
+
\text{Uncertainty}
+
\text{Optimization}
+
\text{Control}
}
$$

A mature implementation of this idea could support a continuous loop:

```text
Observe
   ↓
Estimate
   ↓
Predict
   ↓
Quantify Uncertainty
   ↓
Adapt
   ↓
Optimize / Control
   ↓
Observe Again
```

This architecture motivates research across adaptive digital twins, autonomous systems, cyber-physical systems, computational science, and intelligent simulation.

The long-term question guiding this work is:

> **How can computational models remain useful as the systems they represent evolve, observations remain incomplete, and decisions must be made under uncertainty?**

That question provides a research bridge between my current software-engineering projects and future graduate study in Modeling and Simulation Engineering.