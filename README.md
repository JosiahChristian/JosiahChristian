# Josiah Christian

### Software Engineering • AI/ML • Cyber-Physical Systems • Computational Modeling

I build software for **intelligent, data-driven, and physically modeled systems**, with interests spanning backend engineering, artificial intelligence, scientific computing, cyber-physical systems, digital twins, autonomy, and computational simulation.

My work combines software engineering with mathematical and physical modeling: from Java backend infrastructure and interactive web telemetry to autonomous planning, aerospace simulation, biomedical computation, and adaptive digital-twin research.

I am developing this portfolio alongside my Computer and Data Science degree programs with a long-term research direction in **Modeling and Simulation Engineering**, particularly the prediction, adaptation, and control of complex evolving systems.

---

## Engineering & Research Focus

My portfolio is organized around three connected areas:

### Software & Systems Engineering

Building reliable software infrastructure for computational and data-intensive systems.

- Backend and REST API development
- Concurrent and asynchronous processing
- Object-oriented software architecture
- Web interfaces and real-time visualization
- Persistence and data pipelines
- Automated testing and CI/CD
- Reproducible build systems

### Intelligent & Cyber-Physical Systems

Developing software that connects computation, sensing, decision-making, and physical-system behavior.

- Cyber-physical systems
- Autonomous planning
- Telemetry and state monitoring
- Digital twins
- Feedback and control
- Aerospace systems
- Adaptive and intelligent systems

### Computational Modeling & Research

Using mathematical models, numerical computation, and machine learning to investigate complex systems.

- Dynamical systems
- State-space modeling
- Scientific computing
- Physics-informed machine learning
- Numerical simulation
- Optimization and intelligent control
- Uncertainty-aware modeling
- Biomedical and aerospace applications

---

# Selected Engineering Projects

## TelemetryPipelineJava

**Java 21 • Spring Boot • Maven • REST • Spring Data JPA • H2 • JUnit • GitHub Actions**

A layered telemetry backend for asynchronous data ingestion, validation, processing, persistence, and retrieval.

The project combines REST API engineering with a thread-safe producer/consumer architecture using `BlockingQueue<TelemetryPacket>`. Incoming telemetry is validated through the API, passed through a service layer, processed asynchronously, and persisted using Spring Data JPA.

Engineering features include:

- Spring Boot REST endpoints
- Bean Validation
- Structured exception handling
- Service and repository layers
- Concurrent producer/consumer processing
- H2 relational persistence
- Maven dependency and build management
- Automated Spring Boot, MockMvc, and repository tests
- GitHub Actions CI using Java 21

[Explore TelemetryPipelineJava](https://github.com/JosiahChristian/TelemetryPipelineJava)

---

## AeroCPSSimulation

**C++ • CMake • Control Systems • Flight Dynamics • GitHub Actions**

A modular cyber-physical flight simulation exploring closed-loop quadcopter dynamics and proportional feedback control.

The project models six-degree-of-freedom flight behavior and incorporates configurable gravitational environments while emphasizing modular C++ architecture and reproducible builds.

Engineering features include:

- Object-oriented simulation architecture
- 6-DOF flight dynamics
- Proportional feedback control
- Configurable planetary gravity models
- CMake build management
- GCC/Clang CI validation

[Explore AeroCPSSimulation](https://github.com/JosiahChristian/AeroCPSSimulation)

---

## AeroCPSTelemetry

**JavaScript • HTML5 • CSS3 • Canvas • Web Visualization**

A browser-based telemetry visualization environment for observing simulated aerospace cyber-physical system behavior.

The interface demonstrates real-time flight-state visualization through browser-native rendering, including altitude tracking, feedback behavior, and environmental disturbances.

Current visualization areas include:

- Aircraft altitude and trajectory behavior
- Target-altitude conformance
- Dynamic atmospheric disturbances
- Crosswind-induced displacement
- Browser-native telemetry rendering

[Explore AeroCPSTelemetry](https://github.com/JosiahChristian/AeroCPSTelemetry)

[Launch Live Aerospace Telemetry](https://josiahchristian.github.io/AeroCPSTelemetry/)

---

## AeroDigitalTwin

**Python • NumPy • Machine Learning • Physics-Informed Modeling**

An experimental digital-twin and predictive-modeling project investigating physics-informed approaches to structural degradation and predictive maintenance.

The project explores combining optimization with physical constraints so learned models can be evaluated against governing system behavior rather than data fitting alone.

Research themes include:

- Physics-informed machine learning
- Predictive maintenance
- Structural degradation modeling
- Optimization
- Loss-function design
- Model convergence analysis

[Explore AeroDigitalTwin](https://github.com/JosiahChristian/AeroDigitalTwin)

---

## BiomedicalSystemsSolver

**Python • NumPy • Matplotlib • Numerical Methods • Biophysics**

A computational modeling project exploring two biological-system domains: electrophysiology and cardiovascular fluid behavior.

The repository uses numerical integration and finite-difference methods to investigate how software and mathematical models can represent evolving biological processes.

Current modeling areas include:

- Action-potential propagation
- Neural electrophysiology
- Transient numerical integration
- Arterial velocity profiles
- Finite-difference computation
- Scientific visualization

[Explore BiomedicalSystemsSolver](https://github.com/JosiahChristian/BiomedicalSystemsSolver)

### BiomedicalTelemetryVisualizer

**JavaScript • HTML5 • CSS3 • Canvas • Scientific Visualization**

A dedicated browser-based scientific telemetry environment for computational biophysics and biomedical system models.

The visualizer provides an independent observation layer for physiological simulations, separating biomedical telemetry from the aerospace visualization stack.

Current visualization areas include:

- Cardiovascular flow dynamics
- Vessel velocity telemetry
- Systolic and diastolic pressure behavior
- Neural action-potential propagation
- Membrane-potential recovery
- Real-time physiological signal rendering

[Explore BiomedicalTelemetryVisualizer](https://github.com/JosiahChristian/BiomedicalTelemetryVisualizer)

[Launch Live Biomedical Telemetry](https://josiahchristian.github.io/BiomedicalTelemetryVisualizer/)

---

## AutonomousPathPlanner

**C++ • Algorithms • Spatial Reasoning • Autonomous Systems**

An autonomous planning project exploring perception-to-planning software architecture and dynamic obstacle avoidance.

The system processes environmental constraints and performs geometric collision evaluation to modify planned trajectories when obstacle regions intersect the current path.

Engineering themes include:

- Autonomous decision logic
- Spatial reasoning
- Obstacle detection
- Collision evaluation
- Dynamic waypoint adjustment
- Modular C++ development

[Explore AutonomousPathPlanner](https://github.com/JosiahChristian/AutonomousPathPlanner)
[Launch Live Autonomy Visualizer](https://josiahchristian.github.io/AutonomousPathPlanner/)

---

# Current Research Development

## Adaptive Digital Twin Framework

I am developing a broader research framework around **adaptive digital twins for complex evolving systems**.

The project is being constructed from the mathematical foundation upward, connecting concepts from dynamical systems, state estimation, machine learning, uncertainty quantification, optimization, intelligent control, and computational architecture.

Current theoretical areas include:

```text
Dynamical Systems
        ↓
State-Space Representation
        ↓
Observation & State Estimation
        ↓
Machine Learning / Adaptive Dynamics
        ↓
Uncertainty Quantification
        ↓
Optimization & Intelligent Control
        ↓
Adaptive Digital Twin
```

The long-term objective is to investigate computational systems that continuously reconcile models with observations, quantify uncertainty, adapt internal representations, and support prediction or control as the underlying system evolves.

[Explore Adaptive-Digital-Twin-Framework](https://github.com/JosiahChristian/Adaptive-Digital-Twin-Framework)

---

# Technical Toolkit

### Languages

`Java 21` • `C++17` • `Python` • `JavaScript` • `SQL`

### Backend & Software Engineering

`Spring Boot` • `REST APIs` • `Spring Data JPA` • `Maven` • `Object-Oriented Design` • `Concurrency`

### Scientific Computing & AI/ML

`NumPy` • `SciPy` • `Matplotlib` • `Numerical Methods` • `Physics-Informed Modeling` • `Optimization`

### Web Engineering

`HTML5` • `CSS3` • `JavaScript Canvas` • `Responsive Interfaces` • `Data Visualization`

### Engineering Infrastructure

`Git` • `GitHub Actions` • `CI/CD` • `CMake` • `Maven` • `Linux CI Environments`

---

# Research Direction

My broader technical interests center on the intersection of:

**software engineering + artificial intelligence + mathematical modeling + physical systems**

I am particularly interested in systems that must:

1. observe an evolving physical or computational process,
2. estimate its current state,
3. predict future behavior,
4. quantify uncertainty,
5. adapt models as new information arrives, and
6. support intelligent decisions or control.

This creates a common research thread across digital twins, autonomous systems, aerospace simulation, biomedical modeling, telemetry infrastructure, and AI-assisted computational engineering.

---

# Portfolio Philosophy

These repositories are not intended to represent a single technology stack or application domain.

Together, they document my development across **software engineering, computational science, intelligent systems, and research-oriented modeling** while leaving room for independent coursework, experiments, and future engineering projects.

The connecting question behind much of my work is:

> **How can software, mathematical models, and machine intelligence work together to understand, predict, and influence complex evolving systems?**

---

## Current Direction

Continuing development in:

- Java and backend software engineering
- AI and machine learning
- computational modeling and simulation
- cyber-physical and autonomous systems
- adaptive digital twins
- scientific computing
- research software engineering

with a long-term academic interest in advanced research in **Modeling and Simulation Engineering**.
