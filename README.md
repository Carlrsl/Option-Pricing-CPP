# C++ Option Pricing Project

This project implements a comprehensive financial option pricing engine in C++, developed as part of the **"C++ for Finance"** course at **ESILV**.

The engine follows a strict Object-Oriented architecture and uses modern C++ STL features.

## 👥 The Team
Project realized by:
* **Carl ROUSSEL**
* **Alec REYNEN**
* **Thibault PELOU**
* **Louis ROZE**
* **Hugo PICARD**

## 🚀 Key Features

The project is divided into three major parts covering different mathematical models:

### 1. Black-Scholes Model (Closed-Form)
Implementation of the `BlackScholesPricer` class for fast pricing:
* **Products:** European Vanilla Options (Call/Put) and Digital Options.
* **Greeks:** Analytical calculation of Delta.
* **Math:** Utilization of the complementary error function (`std::erfc`) for the cumulative normal distribution.

### 2. Cox-Ross-Rubinstein Model (CRR - Binomial Tree)
Implementation of a generic tree data structure (`BinaryTree<T>`) for numerical methods:
* **Logic:** Backward induction to determine the price at `t=0`.
* **American Options:** Handling of early exercise (comparison between *intrinsic value* and *continuation value*).
* **Exercise Policy:** Storage of the optimal exercise strategy in a boolean tree.
* **Arbitrage Checks:** Automatic verification of no-arbitrage conditions (`D < R < U`).
* **Convergence:** Capability to initialize CRR parameters to approximate Black-Scholes as N approaches infinity.

### 3. Monte Carlo & Exotic Products
Stochastic simulation engine `BlackScholesMCPricer`:
* **Path-Dependent Options:** Pricing of Asian Options (Arithmetic average payoff).
* **Random Generation:** Use of a Singleton class `MT` encapsulating `std::mt19937` (Mersenne Twister) for robust simulations.
* **Statistics:** Computation of 95% Confidence Intervals.