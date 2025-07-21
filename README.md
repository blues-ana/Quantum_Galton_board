<p align="center">
  <img src="https://drive.google.com/uc?export=view&id=1gco4xivJ4_gVIG9c3X_9hYHNwd772k5b" alt="Womanium Logo" width="300" align="right"/>
</p>

<br/><br/>
<h1 style="color:#004aad;">Quantum Walks and Monte Carlo</h1>

## Team: ------

### Team Members

- Julio César ... — WISER ID: ...
- Ana Noguera ... — WISER ID: ...  
- Mirian Ahuatzi ... — ID: gst-BIBIibpQapXMXhN  

---

## 📄 Project Summary

The **Quantum Galton Board (QGB)** is a quantum circuit model that emulates the statistical behavior of a classical Galton board using quantum mechanical principles. In the classical system, a ball falls through a triangular array of pins, being deflected left or right at each layer with a 50% chance. After many such layers, the accumulated results form a binomial distribution that closely approximates a Gaussian. The quantum version replaces the physical randomness with coherent superposition and interference, enabling a single quantum “ball” to explore all possible trajectories simultaneously.

This project, developed for the **WISER 2025 Quantum Challenge in collaboration with the Naval Nuclear Laboratory (NNL)**, focuses on the efficient construction, simulation, and analysis of multi-level Quantum Galton Boards using the Qiskit SDK. We begin by implementing a single quantum peg and gradually build circuits with up to four levels, corresponding to nine quantum pegs and ten qubits. In each case, the structure uses Hadamard gates, controlled-SWAP operations (Fredkin gates), and CNOT gates to route amplitude across different data qubits while recycling a central control qubit.

Each configuration is simulated using noiseless quantum backends to obtain the resulting output distributions. Repeated measurement across many shots yields histograms that reproduce the expected Gaussian profile, thus validating the quantum encoding of classical stochastic processes.

The next phase of the project involves generalizing the QGB to arbitrary depth, constructing **biased circuits** by introducing parameterized \( R_x(\theta) \) gates in place of Hadamards, and generating non-Gaussian distributions such as **exponential** and **quantum walk-inspired** profiles. We also aim to simulate the circuits under realistic **quantum noise models**, optimizing gate depth to improve fidelity. The final step will involve calculating statistical distances (e.g., KL divergence, total variation distance) between the measured output and the target distribution, allowing a quantitative evaluation of the simulation’s accuracy.

Through this project, we demonstrate how quantum circuits can serve as compact statistical simulators, highlighting both the power and limitations of current quantum hardware. Our implementation showcases modular design, circuit efficiency, and the potential for adaptation to broader probabilistic modeling tasks in physics and data science.

---

## 🎞 Project Presentation Deck

👉 [Click here to view the deck](./presentation.pdf)  

---
## 🎞 Structured Summary: Implementing the Quantum Galton Board

👉 [Click here to view the deck](./doc.pdf)  
