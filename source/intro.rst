Introduction
============

OpenQASM is an imperative programming language for describing quantum circuits. It is capable to
describe universal quantum computing using the circuit model, measurement-based model, and near-term
quantum computing experiments. It achieves this using a parameterized set of physical logic gates
and concurrent real-time classical computations. Its main goal is to serve as an intermediate
representation for higher-level compilers to communicate with quantum hardware; however, allowances
have been made to make it pleasant to write for people as well. In particular, the language admits
different representations of the same program as it is lowered from a high-level description down to
a low-level pulse representation.

This document is draft version 3.0 of the OpenQASM specification. The Qiskit development team is
soliciting feedback on this draft for consideration prior to finalizing version 3.0.


Design Goals
------------

Version 3.0 of the OpenQASM specification aims to extend OpenQASM to include:

* **A broader family of computation with classical logic**. We introduce classical control flow,
  instructions, and data types to define circuits that include real-time computations on
  classical data. A *kernel* mechanism allows for opaque references to generic classical
  computations acting upon run-time data.

* **Explicit timing**. We introduce a flexible mechanism to describe *design intent* of
  instruction scheduling while remaining independent of specific durations determined by gate
  calibrations. This enables, for example, dynamical decoupling while retaining a gate-level
  description of a circuit.

* **Embedded pulse-level definitions**. An extensible mechanism to attach low-level definitions to
  gates. This is particularly relevant to calibration tasks which optimize pulse parameters using
  error amplification sequences most easily described at the gate level.


Scope
-----

This document aims to define the OpenQASM language itself, but it does not attempt to fully explain
the motivation for various design choices. A forthcoming paper will provide this background. This
document also does not seek to define the execution environment that accepts OpenQASM as an input.
For the previous versions of OpenQASM please read arXiv:1707.03429_.

.. _arXiv:1707.03429: https://arxiv.org/abs/1707.03429
