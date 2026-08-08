# ODU Doctoral Research Matrix: Literature Review Workspace

This tracking database logs the historical data, mathematical equations, and active literature reviews matching my trajectory into the ODU Ph.D. in Modeling and Simulation Engineering.

---

## 📑 Core Literature Review Log Matrix

### 🧠 1. Neuro-Electrophysiology & Bio-Transport Space
*   **Target Publication Domain:** Multi-scale mathematical modeling of excitable biological tissues.
*   **Mathematical Foundation (Spatial Cable Equation):**
    $$C_m \frac{\partial V}{\partial t} = \frac{a}{2R_a} \frac{\partial^2 V}{\partial x^2} - \sum I_{ion}$$
*   **Core Literature Insights:** Analysis of how micro-scale changes in axon diameter ($a$) or membrane capacitance ($C_m$) directly impact macro-scale signal propagation velocities. This maps directly to my optimization adjustments within `BiomedicalSystemsSolver`.
*   **Active Lab Mapping:** Directly supports virtual anatomical validation tracks under ODU Medical Simulation pipelines.

### 📊 2. Physics-Informed Neural Networks (PINN) Space
*   **Target Publication Domain:** Integrating partial differential equations (PDEs) directly into machine learning deep networks.
*   **Mathematical Foundation (PINN Loss Metric Optimization):**
    $$\mathcal{L}_{\text{total}} = \mathcal{L}_{\text{data}} + \mathcal{L}_{\text{physics}}$$
    $$\mathcal{L}_{\text{physics}} = \frac{1}{N} \sum_{i=1}^N \left| \frac{\partial \hat{u}}{\partial t} + \mathcal{N}_x[\hat{u}] \right|^2$$
*   **Core Literature Insights:** Standard data-driven AI models fail when telemetry logs are scarce or noisy. By embedding physical conservation matrices (like fluid momentum or mechanical stress limits) straight into the backpropagation loss calculation, the system is physically forced to maintain stability.
*   **Active Lab Mapping:** Serves as the foundation for structural health degradation forecasting tracks within my `AeroDigitalTwin`.

### 🛸 3. Cyber-Physical Runtime Verification Space
*   **Target Publication Domain:** Formal methods, control safety boundaries, and trajectory validation under high-uncertainty dynamics.
*   **Mathematical Foundation (State-Space Control Matrix):**
    $$\dot{\mathbf{x}}(t) = \mathbf{A}\mathbf{x}(t) + \mathbf{B}\mathbf{u}(t) + \mathbf{D}\mathbf{w}(t)$$
*   **Core Literature Insights:** Modeling structural error bounds where external environmental disturbance forces ($\mathbf{w}(t)$), such as heavy atmospheric crosswind shear vectors, interface with proportional feedback hardware loops ($\mathbf{u}(t)$). 
*   **Active Lab Mapping:** Connects directly into my `AeroCPSSimulation` and `AutonomousPathPlanner` verification timelines.

---

## 🗺️ Academic Course-to-Thesis Mapping Ledger
This ledger functions as an active mapping log to guarantee every upcoming graduate assignment contributes structurally to a specific segment of my eventual doctoral dissertation framework:

1.  **MSIM 602 (Simulation Fundamentals):** Applied to design high-performance queue management systems tracking sensory packet ingestion latency constraints.
2.  **MSIM 541 (Computer Graphics & Visualization):** Applied to extend browser-native low-overhead interactive monitoring canvases.
3.  **Advanced Machine Learning Graduate Seminars:** Applied to optimize stress tracking weight algorithms inside the structural digital twin engine.
4.  **High-Performance Computing (HPC) Core:** Applied to translate local script configurations into scalable, distributed parallel arrays running on ODU clusters.

---

## 📊 Comprehensive Computational Simulation Data Ledger

This ledger acts as a permanent auditing framework tracking the discrete mathematical variations, operational environments, and resulting physical file logs compiled across my technical architecture.

| 📂 Target Repository Slot | 🏷️ Research Scenario Profile | 🌍 Physical Parameters Tested | 📄 Log Asset Generated (Hard Drive / Cloud) |
| :--- | :--- | :--- | :--- |
| `AeroCPSSimulation` | Baseline Planetary Flight | Gravity: $-9.81 \text{ m/s}^2$ (Earth Core) | `test_logs/flight_telemetry_run_history.txt` |
| `AeroCPSSimulation` | Deep Space Drone Auto-Pilot | Gravity: $-3.711 \text{ m/s}^2$ (Mars Grid) | `test_logs/flight_telemetry_run_history.txt` |
| `AeroDigitalTwin` | Optimization Phase Baseline | Epochs: $50$ \| Learning Rate: $1\text{e-}4$ | `test_logs/learning_test_run_baseline.txt` |
| `AeroDigitalTwin` | Deep Model Convergence Suite | Epochs: $500$ \| Learning Rate: $1\text{e-}3$| `test_logs/learning_test_run_converged.txt` |
| `BiomedicalSystemsSolver` | Transient Carotid Hemodynamics| Track Scale: $10 \text{ cm}$ \| Nodes: $20$ | `output/hemodynamic_velocity_vector.txt` |
| `BiomedicalSystemsSolver` | Neuro-Electrophysiology Cable | Track Scale: $1 \text{ cm}$ \| Nodes: $100$ | `output/transmembrane_potential_volt.txt` |

### 🛠️ Execution Tracking Protocol
* Local text logs generated in standard comma-separated text frameworks (`.txt` / `.csv`) are housed inside structured root-level `test_logs/` sub-directories.
* Changes are automatically ingested and integrated during pushing routines to serve as immutable benchmark artifacts matching my doctoral thesis progress timeline tracking constraints.

---

## 🔬 Advanced Mathematical Derivations & Publication Deep-Dive

This section documents the foundational calculus limits, partial differential equations, and state-space tracking mechanics guiding my doctoral research thesis compilation.

### ⚡ 1. Multi-Scale Hodgkin-Huxley Cable Matrix Verification
Electrical signal propagation velocity down unmyelinated neural pathways is evaluated by tracking parallel membrane capacitance and ion channel conductance parameters:

$$\frac{a}{2R_a}\frac{\partial^2 V}{\partial x^2} = C_m\frac{\partial V}{\partial t} + \bar{g}_{Na}m^3h(V - V_{Na}) + \bar{g}_K n^4(V - V_K) + g_L(V - V_L)$$

*   **Axoplasmic Diffusion Metric:** The second-order derivative ($\frac{\partial^2 V}{\partial x^2}$) governs passive longitudinal voltage decay down the fiber core axis based on axial core radius ($a$) constraints.
*   **Voltage-Gated Gating Transitions:** Dynamic open/close probability matrices ($m, h, n$) simulate the precise sodium depolarization and potassium repolarization currents generating transient clinical potential voltage spike waveforms.

### 📐 2. Non-Linear Hemodynamic Convective Mass-Transport Fluid Core
The fluid dynamics solver moves beyond basic linear boundary assumptions to enforce a 1D incompressible convective Navier-Stokes profile tracking velocity vectors through an elastic carotid tract segment:

$$\frac{\partial v}{\partial t} + v \frac{\partial v}{\partial x} = -\frac{1}{\rho}\frac{\partial P}{\partial x} + \frac{\mu}{\rho}\left(\frac{\partial^2 v}{\partial x^2} + \frac{1}{R}\frac{\partial R}{\partial x}\frac{\partial v}{\partial x}\right)$$

*   **Convective Acceleration Mapping:** The spatial gradient ($v \frac{\partial v}{\partial x}$) resolves non-linear fluid momentum velocity alterations caused by geometric arterial lumen alterations.
*   **Fluid-Structure Interaction Coupling:** The boundary tracking component ($\frac{1}{R}\frac{\partial R}{\partial x}$) models radial cross-sectional boundary expansion ($R$), capturing wall shear stress modifications during heart wall systolic ejections.

### 🛸 3. Environmental Disturbance Control State-Space Array
The validation of autonomous aerospace vehicle trajectory tracking loops operating under extreme atmospheric constraints uses a continuous safety-critical control framework:

$$\mathbf{\dot{x}}(t) = \mathbf{A}\mathbf{x}(t) + \mathbf{B}\mathbf{u}(t) + \mathbf{D}\mathbf{w}(t)$$

*   **Systemic Tracking Integration:** Cross-maps independent feedback control laws ($\mathbf{u}(t)$) against external wind shear boundary disruptions ($\mathbf{w}(t)$) to model flight safety stability thresholds.

---

## ⛓️ Code-to-Equation Telemetry Mapping Index

This index bridges the discrete structural string tracking metrics archived in local and cloud `test_logs/` sub-directories directly to the continuous differential parameters of the core mathematical frameworks.

### 🛸 1. Aerospace CPS Tracking Integration Matrix
*   **Target Log Location:** `AeroCPSSimulation/test_logs/flight_telemetry_run_history.txt`
*   **Code Parameter Mapping Structure:**

| 📄 Local Log String Value | 🧮 Continuous Calculus Term | 📐 Physical System Meaning |
| :--- | :--- | :--- |
| `Flight Step` | Independent Variable Step Delta ($t$) | Continuous iteration integration time steps ($\Delta t = 0.05\text{s}$) |
| `Current Altitude` | State Trajectory Space Array element ($x(t)$) | The physical vertical tracking displacement component coordinate vector |
| `Velocity` | First-Order Time Derivative Operator ($\dot{x}(t)$) | Kinematic velocity vector output generated by active total acceleration parameters |
| `Atmospheric Wind Shear` | Disturbance Force Matrix component ($\mathbf{D}\mathbf{w}(t)$)| Crosswind vector disruptions acting dynamically on the quadcopter chassis bounds |

---

### 🧠 2. Deep Learning Twin Optimization Matrix
*   **Target Log Location:** `AeroDigitalTwin/test_logs/learning_test_run_*.txt`
*   **Code Parameter Mapping Structure:**

| 📄 Local Log String Value | 🧮 Continuous Calculus Term | 📐 Physical System Meaning |
| :--- | :--- | :--- |
| `Epochs` | Optimization Loop Index Boundary ($N$) | Total configuration tracking execution epochs run across the system loops |
| `Learning Rate` | Gradient Descent Multiplier Step ($\alpha$) | System learning rate step size coefficient adjustments used to shift local model weights |
| `Final Tracking Loss Index` | Aggregated Performance Metric Value ($\mathcal{L}_{\text{total}}$)| Mean Squared Error performance tracking indices validating optimization convergence |

---

### 🫀 3. Multi-Domain Biophysics Stream Mapping Core
*   **Target UI Components:** `AeroCPSTelemetry/index.html` $\rightarrow$ Canvas Rendering Contexts
*   **Code Parameter Mapping Structure:**

| 📄 Interface Variable String | 🧮 Continuous Calculus Term | 📐 Physical System Meaning |
| :--- | :--- | :--- |
| `cardioVelocity` | Transient Blood Mass-Transport Velocity ($v(x,t)$) | Scrolling 2D pixel coordinates plotting mid-artery Carotid pressure pump fluid waves |
| `actionPotential` | Axon Transmembrane Potential ($V(x,t)$) | Scrolling red vector lines plotting voltage-gated synaptic depolarization spikes |
| `systolicBP / diastolicBP`| Intravascular Blood Hydrostatic Pressure ($P$) | Automated text data canvas bindings calculating mean arterial blood pressure indices |
