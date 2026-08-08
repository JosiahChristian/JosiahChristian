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
