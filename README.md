<p align="center">
  <img src="https://drive.google.com/uc?export=view&id=1gco4xivJ4_gVIG9c3X_9hYHNwd772k5b" alt="Womanium Logo" width="300" align="right"/>
</p>

<br/><br/>
<h1 style="color:#004aad;">Quantum Walks and Monte Carlo</h1>

## Team: Quantum Walkers 🐈‍⬛

### Team Members

- Julio Cesar Flores Molina — WISER ID: gst-v6S1tRYrcaFzE4A
- Ana Noguera ... — WISER ID: ...  
- Mirian Ahuatzi Corona — ID: gst-BIBIibpQapXMXhN  

---

## 📄 Project Summary

The **Quantum Galton Board (QGB)** is a quantum circuit model that emulates the statistical behavior of a classical Galton board using quantum mechanical principles. In the classical system, a ball falls through a triangular array of pins, being deflected left or right at each layer with a 50% chance. After many such layers, the accumulated results form a binomial distribution that closely approximates a Gaussian. The quantum version replaces the physical randomness with coherent superposition and interference, enabling a single quantum “ball” to explore all possible trajectories simultaneously.

This project, developed for the **WISER 2025 Quantum Challenge in collaboration with the Naval Nuclear Laboratory (NNL)**, focuses on the efficient construction, simulation, and analysis of multi-level Quantum Galton Boards using the Qiskit SDK. We start by implementing a single quantum peg and then build a four-level circuit based on the circuit presented in [1], corresponding to nine quantum pegs and ten qubits. In each case, the structure uses Hadamard gates, controlled-SWAP operations (Fredkin gates), and CNOT gates to route amplitude across different data qubits while recycling a central control qubit.

The next phase of the project consisted of generalizing QGB to an arbitrary number of levels, that is, automating circuit creation and generating non-Gaussian distributions, specifically **exponential** and **Hadamard quantum walk** profiles. 

The generalized QGB implementation uses a **modular design** where each *quantum peg* consists of:

- **2 CSWAP gates**  
- **1 CNOT gate**  

The **control qubit** is reset and reused at each level to minimize resource usage.  
This approach allows the circuit to scale efficiently — an *n*-level QGB requires only **2n + 2 qubits** — and maintains balanced amplitudes through **corrective inverted CNOTs**.

Simulations are performed using **Qiskit’s AerSimulator** in *matrix product state* (MPS) mode, which optimizes execution speed for circuits with low entanglement.

For the unbiased distribution, a fit to a Gaussian distribution was made, giving a very good approximation; this approximation improved with the number of QGB levels. On the other hand, for the exponential distribution, a good approximation was only obtained with few levels (n = 10); as the levels increased, quantum interference transformed the distribution into a Gaussian one. Finally, for the Hadamard quantum walk, quantum interference was what made it possible to achieve the distribution for an arbitrary number of levels. It also has the advantage of being much more efficient than the construction of the other distributions — for instance, in our tests, a 30-level Hadamard walk with 100,000 shots completed in ~30 seconds on a GPU-accelerated backend, compared to much longer runtimes for the Gaussian QGB.

To produce the exponential distribution, the coin qubit’s Hadamard was replaced with an RY rotation whose angle decays exponentially with the layer index (
𝜃_𝑘 = 𝜃_0 e^{-𝛼𝑘}
), biasing the path probabilities. For the Hadamard quantum walk, CNOT gates after CSWAPs were removed, and the coin qubit was not reset between levels, preserving coherence across the whole circuit and enhancing interference effects.


Through this project, we demonstrate how quantum circuits can serve as compact statistical simulators, highlighting both the power and limitations of current quantum hardware. Our implementation showcases modular design, circuit efficiency, and the potential for adaptation to broader probabilistic modeling tasks in physics and data science.

---

## 🎞 Project Presentation Deck

👉 [Click here to view the deck](./presentation.pdf)  

---
## 🎞 Structured Summary: Implementing the Quantum Galton Board

👉 [Click here to view the deck](./doc.pdf)  

--
## References
[1] Mark Carney & Ben Varcoe (2022). Universal Statistical Simulator. arXiv:2202.01735. https://doi.org/10.48550/arXiv.2202.01735

