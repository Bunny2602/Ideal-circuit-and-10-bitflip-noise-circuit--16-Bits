BB84 Protocol Simulation with Ideal and Noisy Circuits

This repository contains Python implementations of the BB84 quantum key distribution protocol, executed using AWS Braket. The implementations simulate both an ideal quantum circuit and a noisy circuit with 10% bit-flip noise. The circuits are designed to explore quantum communication in perfect and error-prone environments.

Contents
ideal_16_bits.py: Simulates the BB84 protocol with an ideal 16-bit quantum circuit.
16_noise.py: Simulates the BB84 protocol with 10% bit-flip noise applied to the quantum circuit.


1. Ideal 16-Bit BB84 Protocol

Overview
The ideal implementation of the BB84 protocol models a noise-free environment, enabling the generation and distribution of a secret key using quantum states.

Key Steps
Sender (Alice):
Generates a random 16-bit bitstring and a corresponding random set of measurement bases (rectilinear and diagonal).
Prepares quantum states based on the bitstring and bases.

Receiver (Bob):
Chooses random measurement bases.
Measures the received qubits in his chosen bases.

Key Agreement:
Alice and Bob compare their bases to identify matching ones.
A secret key is generated based on the matching bases.

Output:
Alice's bitstring and bases.
Bob's bases and measurements.
The secret key generated from the matching bases.
Quantum circuit visualization.
Communication time.


2. BB84 Protocol with 10% Bit-Flip Noise

Overview
This implementation introduces 10% bit-flip noise to the ideal circuit, simulating real-world error scenarios.

Key Steps


Sender (Alice):
Same as in the ideal protocol.

Noise Application:
Applies bit-flip noise to 10% of the qubits after preparation.
Tracks noisy operations for analysis.

Receiver (Bob):
Same as in the ideal protocol.

Key Agreement:
Compares bases to generate keys for both ideal and noisy scenarios.

Output:
Alice's bitstring and bases.
Bob's bases and measurements (ideal and noisy).
The secret keys (ideal and noisy).
Quantum circuit visualizations (before and after noise).
Positions where noise was applied.
Communication time.

Dependencies
Python 3.x
AWS Braket SDK
Installation

Install the AWS Braket SDK:
pip install amazon-braket-sdk

Clone this repository:
git clone https://github.com/your-repo/bb84-simulation.git
cd bb84-simulation

Running the Simulations

Ideal Circuit:
Run the ideal BB84 protocol simulation:
python ideal_16_bits.py

Noisy Circuit:
Run the BB84 protocol simulation with 10% bit-flip noise:
python 16_noise.py

Results:
The results of each simulation include:
Alice's bitstring and bases.
Bob's bases and measurements.
The secret key (ideal and noisy).
Communication time.
Quantum circuit representations.

Notes: 
Replace the LocalSimulator device with AwsDevice for execution on AWS Braket.
Adjust the num_bits parameter to simulate more or fewer bits.

