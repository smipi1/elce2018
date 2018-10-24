# Tutorial: Introduction to Quantum Computing Using Qiskit - Ali Javadi-Abhari, IBM

## History of Quantum Computing

1935: ERP Paradox

...

1990: Shor's algorithm

1026: IBM Q Experience Service
- 100K users
- 6M experiments run
- 130 scientific papers

## From Q Experience to Q Programs

Q Developers --> API --> Real devices / simulators / laboratory

## Qiskit Elements

Terra
- Foundation
- Core programming tools and API to HW

Aer
- Classical simulation of Q circuits

Aqua
- High-level Q applications
- Chemistry, Optimization, AI, Finance

Ignis
- State characterization, error mitigatoin, optimal control

_Designed to be modular for easy experimental_

## Qiskit Community

A place for Qiskitters

## Plan for talk

Difference between Q and classical information
Solving a concrete problem with Q advantage
Live demo

## One Qubit

States:
`|0>`: Up on sphere
`|1>`: Down on sphere
`|0>` + `|1>`: Unity on X-axis

When we try to _see_ the state, we can only see 0 or 1:
- 50% of all observations will be 0
- 50% of all observations will be 1

## Multiple Qubits

Stat of n qubits is described by 2^n coefficients
Adding one qubit _doubles_ the dimension

## Q information processing

2^n dimensional vector
Mathematically equivalent to matrix multiplication
Quantum circuit Model

## The Hadamard Gate: Superposition

`|0>`: H-gate creates superposition

Has an effect on phase
- Can encode information in phase (no classical equivalent)

## The controlled NOT gate: Q if

CNOT flips the target bit if the control bit is 1

## Problem: Bernstein-Vazirani Algorithm

Person is guarding a secret
You can interact with an oracle
- Feed bit-stream
- Will respond with dot-product
On a classical computer
- Send walking ones
- Need N tries

## Classical vs Q Oracles

Classical dot-product oracle: x.s

Q dot-product oracle: Must be reversible

## Trick: Phase kickback

Hadamard gate causes phase kickback causing measured output to represent secret in one iteration

## Why does this work?

Q oracles can be queried _in superposition_
We could exploit problem structure by encoding information in phases

## Example


