# TWO-SPIN QUANTUM SIMULATION USING QISKIT

## AUTHOR

Fahim Faisal

## OVERVIEW

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

The objective is to understand how quantum computers can simulate physical quantum systems and calculate observable quantities such as energy.

## INTRODUCTION

One of the most important applications of quantum computing is the simulation of quantum systems. Classical computers often struggle to simulate large quantum systems because the amount of information required grows exponentially with the number of particles.

Quantum computers naturally operate according to the laws of quantum mechanics. Because of this, they can represent and simulate quantum systems more efficiently than classical computers.

In this project, a simple quantum system consisting of two interacting spins is modeled using two qubits. By preparing an entangled quantum state and measuring its properties, we can investigate the behavior of a small quantum system using Qiskit.

## PROJECT MOTIVATION

Quantum simulation was one of the earliest applications envisioned for quantum computers.

Many physical systems, including molecules, magnetic materials, and superconductors, are fundamentally quantum mechanical. Simulating these systems on classical computers quickly becomes difficult as the system size increases.

This project serves as a simple introduction to quantum simulation by studying a two-spin system and calculating both measurement outcomes and energy values.

## QUANTUM SPINS

A spin is a fundamental quantum property of particles such as electrons.

For simplicity, a spin can be viewed as a tiny magnet that can point in one of two directions:

Spin Up    -> |0>
Spin Down  -> |1>

Unlike classical objects, quantum spins can also exist in a superposition of both states simultaneously.

For a single qubit:

|ψ> = α|0> + β|1>

where:

|α|² + |β|² = 1

The coefficients α and β determine the probabilities of measuring the qubit in each state.

## QUANTUM ENTANGLEMENT

When two qubits become correlated in a way that cannot be explained classically, they are said to be entangled.

In this project, we prepare the Bell State:

|Ψ-> = (|01> - |10>) / √2

This state has an important property:

* If the first qubit is measured as 0, the second will be 1.
* If the first qubit is measured as 1, the second will be 0.

Although the outcomes are perfectly correlated, neither qubit has a definite value before measurement.

## CREATING THE BELL STATE

Initial State:

|00>

Step 1: Hadamard Gate

Apply a Hadamard gate to qubit 0:

|00>
->
(|00> + |10>) / √2

This creates a superposition.

Step 2: CNOT Gate

Apply a CNOT gate using qubit 0 as the control qubit:

(|00> + |10>) / √2
->
(|00> + |11>) / √2

This creates the Bell State:

|Φ+> = (|00> + |11>) / √2

Step 3: Additional Gates

Apply an X gate to qubit 1 and a Z gate to qubit 0:

|Φ+>
->
|Ψ-> = (|01> - |10>) / √2

This Bell State is used throughout the project.

## MEASURING THE QUANTUM STATE

After preparing the Bell State, measurements are performed on both qubits.

Theoretically expected outcomes:

01 ≈ 50%

10 ≈ 50%

The outcomes:

00

11

should ideally never appear.

Small deviations may occur on real quantum hardware due to noise and hardware imperfections.

## THE TWO-SPIN HAMILTONIAN

To study the energy of the system, we define a Hamiltonian.

A Hamiltonian is a mathematical operator that describes the total energy of a quantum system.

For this project:

H = J(ZZ) + hx(XI + IX)

where:

J  = Spin-spin interaction strength

hx = Transverse magnetic field strength

## MEANING OF EACH TERM

Interaction Term:

J(ZZ)

This term describes the interaction between the two spins.

Depending on the value of J, the spins may prefer to align or anti-align.

Magnetic Field Term:

hx(XI + IX)

This term represents the effect of an external magnetic field acting on both spins.

The magnetic field can flip spins and create quantum superpositions.

## QISKIT WORKFLOW

This project follows the standard Qiskit workflow:

1. MAP

Represent the physical system using qubits and quantum operators.

2. OPTIMIZE

Transpile the circuit for the selected backend.

3. EXECUTE

Run the circuit on:

* IBM Quantum Hardware
* Aer Simulator

4. POST-PROCESS

Analyze:

* Measurement probabilities
* Energy expectation values

## SAMPLER PRIMITIVE

The Sampler primitive answers the question:

"What measurement outcomes occur and how often?"

Example output:

01 : 50

10 : 49

11 : 1

The result is a probability distribution of measurement outcomes.

## ESTIMATOR PRIMITIVE

The Estimator primitive answers a different question:

"What is the expectation value of an observable?"

Instead of producing measurement counts, it calculates a physical quantity such as energy.

For this project, Estimator evaluates:

<Ψ-|H|Ψ->

which represents the energy of the Bell State under the chosen Hamiltonian.

## CIRCUIT OPTIMIZATION (TRANSPILATION)

Before execution, a quantum circuit must be translated into instructions supported by the target quantum processor.

This process is known as transpilation.

During transpilation:

* Logical qubits are mapped to physical qubits.
* Unsupported gates are replaced by hardware-native gates.
* Circuit depth may be reduced.
* Execution efficiency may be improved.

Qiskit performs these operations automatically using a preset pass manager.

## REAL HARDWARE VS SIMULATOR

IBM QUANTUM HARDWARE

Advantages:

* Uses a real quantum processor.
* Demonstrates practical quantum computation.

Disadvantages:

* Queue waiting times.
* Noise and hardware errors.

AER SIMULATOR

Advantages:

* Fast execution.
* No waiting time.
* Ideal theoretical results.

Disadvantages:

* Does not represent real hardware imperfections unless a noise model is included.

## EXPERIMENTS

Experiment 1:
Bell State Measurement using IBM Quantum Hardware

Experiment 2:
Bell State Measurement using Aer Simulator

Experiment 3:
Energy Estimation using EstimatorV2 on IBM Quantum Hardware

Experiment 4:
Energy Estimation using BackendEstimatorV2 on Aer Simulator

## RESULTS

The Bell State measurements should show strong anti-correlation between the two qubits:

01 ≈ 50%

10 ≈ 50%

The energy calculated using Estimator should be close to:

-1

for the chosen Hamiltonian parameters.

Small deviations may occur on real quantum hardware because of noise and gate imperfections.

## TECHNOLOGIES USED

* Python 3.10+
* Qiskit
* Qiskit Aer
* Qiskit IBM Runtime
* IBM Quantum Platform
* Jupyter Notebook

## CONCLUSION

This project demonstrates several fundamental concepts in quantum computing:

* Qubits
* Superposition
* Quantum Gates
* Entanglement
* Bell States
* Quantum Measurement
* Hamiltonians
* Quantum Simulation
* Sampler Primitive
* Estimator Primitive
* IBM Quantum Hardware
* Aer Simulation

Although the system contains only two qubits, the same principles can be extended to much larger quantum systems.

Quantum simulation is expected to be one of the most impactful applications of quantum computing because it enables the study of physical systems that are difficult or impossible to model efficiently using classical computers.
