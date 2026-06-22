# Two-Spin Quantum Simulation with Qiskit

## Overview

This project demonstrates the fundamentals of quantum computing through the simulation of a simple two-spin quantum system using Qiskit.

The project explores:

  * Quantum Superposition
  * Quantum Entanglement
  * Bell State Preparation
  * Quantum Measurement using SamplerV2
  * Energy Estimation using EstimatorV2
  * IBM Quantum Hardware Execution
  * Aer Simulator Execution
  * Hamiltonian-Based Quantum Simulation

The goal is to understand how quantum computers can be used to simulate physical quantum systems and calculate observable quantities such as energy.

---

## Project Motivation

One of the most promising applications of quantum computing is quantum simulation.

Classical computers face exponential scaling challenges when simulating quantum systems. Quantum computers naturally follow the laws of quantum mechanics and can therefore model these systems more efficiently.

This project simulates a simple two-spin system and demonstrates how quantum circuits can be used to study quantum states and measure physical properties.

---

## Quantum State Used

The project prepares the Bell State:

<img width="136" height="52" alt="image" src="https://github.com/user-attachments/assets/a61fa496-8e31-400b-89ad-0aba3989becc" />

This state is maximally entangled and exhibits perfect anti-correlation between the two qubits.

---

## Hamiltonian

The energy of the system is described by:

H = J(ZZ) + h_x(XI + IX)

where:

J : Spin-spin interaction strength
hx : Transverse magnetic field strength

This Hamiltonian models:

  * Interaction between two spins
  * Influence of an external magnetic field
  * Quantum spin flipping effects

---

## Qiskit Workflow

This project follows the standard Qiskit Patterns workflow:

### 1. Map

Represent the physical system using qubits and quantum operators.

### 2. Optimize

Transpile the circuit for the selected quantum backend.

### 3. Execute

Run the circuit using:

* IBM Quantum Hardware
* Aer Simulator

### 4. Post-Process

Analyze:

* Measurement probabilities
* Energy expectation values

---

## Experiments

### Experiment 1: Bell State Measurement on IBM Quantum Hardware

Using SamplerV2:

Bell State → Transpile → IBM Quantum Backend → Counts

Expected Results:

01 ≈ 50%
10 ≈ 50%

---

### Experiment 2: Bell State Measurement on Aer Simulator

Using BackendSamplerV2:

Bell State → Aer Simulator → Counts

Purpose:

* Fast execution
* Hardware comparison
* Noise-free validation

---

### Experiment 3: Energy Estimation on IBM Quantum Hardware

Using EstimatorV2:

Bell State + Hamiltonian → Estimator → Energy

Energy calculated:

<img width="95" height="47" alt="image" src="https://github.com/user-attachments/assets/25253a81-8593-4b46-b4b2-9e49c4565de0" />

---

### Experiment 4: Energy Estimation on Aer Simulator

Using BackendEstimatorV2:

Bell State + Hamiltonian → Simulator → Energy

Used to compare theoretical and experimental results.

---

## Technologies Used

* Python 3.10+
* Qiskit
* Qiskit Aer
* Qiskit IBM Runtime
* IBM Quantum Platform
* Jupyter Notebook

---

## Key Concepts Demonstrated

    * Qubits
    * Superposition
    * Entanglement
    * Bell States
    * Quantum Gates
    * Hamiltonians
    * Quantum Simulation
    * Sampler Primitive
    * Estimator Primitive
    * Circuit Transpilation
    * IBM Quantum Hardware

---

## Sample Results

### Measurement Counts

<img width="467" height="347" alt="image" src="https://github.com/user-attachments/assets/08139d44-f71a-47df-a6cc-5ed4db35e069" />


### Energy Estimation
Real Hardware Energy : -0.9934

Simulator Energy    : -1.0000

---

## Author

**Fahim Faisal**

B.Sc. in Electrical and Electronic Engineering (CUET)

Research Interests:

* Quantum Computing
* Electromagnetics & Antennas
* Power Systems & Automation

---

