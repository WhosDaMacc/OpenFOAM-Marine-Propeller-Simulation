# Propeller Performance Analysis using OpenFOAM

This repository contains files and scripts for a CFD simulation of a propeller in water using OpenFOAM. The simulation aims to evaluate the propeller’s thrust, torque, and efficiency at specific operating conditions. This case is based on the OpenFOAM propeller tutorial.

## Project Overview

This analysis evaluates a propeller with the following specifications:
- **Propeller Diameter**: 0.2 m
- **Inflow Velocity**: 5 m/s
- **Rotational Speed**: 158 rad/s
- **Fluid**: Water (Density: 1000 kg/m³)

Key performance parameters like **thrust coefficient** (C_T), **torque coefficient** (C_Q), and **efficiency** (eta) are calculated and compared with theoretical expectations.

## Simulation Setup

1. **Geometry and Mesh**: The tutorial propeller geometry is used. The mesh is generated with appropriate resolution around the propeller blades and wake regions to capture flow characteristics accurately using snappyHexMesh.

2. **Boundary Conditions**:
   - **Inlet**: Uniform inflow velocity of 5 m/s.
   - **Outlet**: Zero-gradient pressure boundary condition.
   - **Propeller Surface**: Rotating wall condition.

3. **Solver**: The `pimpleFoam` solver is used, suitable for transient simulations involving incompressible flows.


## Running the Simulation

1. **Prepare the case**:

  Run Allrun.pre

2. **Run the Simulation**:

  Run Allrun

3. **Post-Processing**: Use the forces function in the `controlDict` to calculate thrust and torque on the propeller. The results are stored in the `postProcessing/forces` directory. The same applies to the moments.

## Analysis

- **Thrust and Torque**: The calculated values of thrust and torque are used to derive dimensionless coefficients C_T and C_Q, along with efficiency (eta).


## Results

The computed performance parameters are:

- **Thrust Coefficient** (C_T): 0.361
- **Torque Coefficient** (C_Q): 0.106
- **Advance Ratio** (J): 0.994
- **Efficiency** (eta): 53.7%

These values are calculated in report.pdf
