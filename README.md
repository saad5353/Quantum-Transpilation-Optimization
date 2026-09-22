# Quantum Transpilation Pipeline ⚛️

This repository contains educational materials and Qiskit code examples demonstrating **Quantum Transpilation**—the process of converting high-level, abstract quantum algorithms into executable, noise-resistant instructions for specific physical quantum hardware.

## 📌 Overview

While classical *compilation* translates high-level code to machine binary, quantum *transpilation* is a source-to-source transformation. It adapts ideal mathematical circuits to the physical constraints of Noisy Intermediate-Scale Quantum (NISQ) devices.

This module covers the three main hardware barriers transpilation solves:
1. **Basis Gate Constraints:** Converting textbook gates (e.g., Hadamard, Toffoli) into the chip's native microwave/laser pulses.
2. **Coupling Maps (Topology):** Navigating the physical wiring of the chip (e.g., heavy-hex grids) where not all qubits are directly connected.
3. **Heterogeneous Qubit Quality:** Routing around high-error physical qubits.

## ⚙️ The 4-Step Transpilation Pipeline

1. **Unrolling (Synthesis):** Decomposing abstract gates into the target hardware's native basis gates (e.g., `RZ`, `SX`, `X`, `CNOT`).
2. **Initial Layout:** Mapping virtual algorithmic qubits to the highest-quality physical qubits on the chip.
3. **Routing (SWAP Insertion):** Inserting `SWAP` gates to satisfy hardware connectivity limits when 2-qubit gates are required between non-adjacent qubits.
4. **Post-Routing Optimization:** Using commutation rules and rotation merging to cancel out redundant gates created during unrolling and routing.

## 🛠 Prerequisites & Installation

```bash
pip install qiskit qiskit-ibm-runtime numpy
