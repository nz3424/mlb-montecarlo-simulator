# Optimizing MLB Postseason Pitching Rotations

This repository contains the code for a simulation-based and optimization-driven analysis of MLB pitching rotation construction under postseason conditions. The project studies how teams should allocate payroll across starting pitchers and offense when the objective is to maximize championship probability in short playoff series rather than regular-season performance.

## Project Overview

MLB postseason series are short, volatile, and highly sensitive to elite starting pitching. Because of this, roster construction strategies that work well over a 162-game regular season may not be optimal in October. This project combines statistical modeling, Monte Carlo simulation, and optimization methods to evaluate which types of pitching rotations perform best in the postseason under different payroll constraints.

The main goals of the project are:

- model game outcomes as a function of starting pitcher quality, opponent offensive strength, rest, and home-field advantage
- simulate playoff series and full postseason runs many times to estimate championship probability
- compare different roster construction strategies under fixed payroll budgets
- identify whether top-heavy or balanced rotations are more effective in postseason settings
- explore optimization approaches for selecting cost-effective rotations

## Methodology

The project consists of three main components:

### 1. Statistical Game Model
A negative binomial regression model is used to estimate runs allowed in a game. Key predictors include:

- starting pitcher WAR
- opposing team offensive quality
- days of rest
- home-field indicator

This model generates the expected runs allowed for each team in a simulated game.

### 2. Monte Carlo Postseason Simulation
Using the fitted run model, the code simulates:

- individual games
- best-of-series playoff matchups
- full postseason brackets

Repeating these simulations many times produces an estimate of each roster’s championship probability.

### 3. Rotation Optimization
The repository includes code for evaluating and selecting five-man pitching rotations under payroll constraints. Two general approaches are used:

- **Monte Carlo search / heuristic optimization** to identify high-performing rotations
- **surrogate-based integer programming** to approximate the simulation objective and solve a tractable roster selection problem

