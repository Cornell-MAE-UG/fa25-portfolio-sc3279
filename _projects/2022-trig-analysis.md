---
layout: project
title: MAE 3070 Project
description: Class project with torque wrench
technologies: [CAD & ANSYS]
image: /assets/images/Torque_Wrench_sketch.png
---

### 1. CAD Model
Dimensions: image of CAD on the left
- L = 16 inches,
- h = 0.5 inches,
- b = 0.8, inches,
- c = 1.0, inches,
- r = .05 inches

<div style="clear: both;"></div>
### 2. Materials Used & Properties
The torque wrench beam was designed using M42 tool steel due to its high strength, good fatigue resistance, and compatibility with bonded strain gauges. Relevant material properties used in analysis include:

- Young’s modulus: 32 Msi
- Poisson’s ratio: 0.29
- Ultimate tensile strength: 370 ksi
- Fatigue strength (10⁶ cycles): 115 ksi
- Fracture toughness: 15 ksi√in

These properties were used to evaluate yielding, fatigue performance, and crack-growth safety margins.

### 3. Loads & Boundary conditions applied to FEM
The torque wrench was modeled as a cantilever beam, fixed at the drive end. A point load was applied at the load arm to generate the equivalent design torque. Boundary conditions included:

- Fully fixed constraints at the square drive interface
- Point load producing 600 in-lbf torque
- Strain gauge locations modeled on the tension side of the beam

A simplified diagram of the applied loads and constraints is shown below.
<p align="center">
  <img src="{{ '/assets/images/Load.png' | relative_url }}" width="800">
</p>

### 4. Normal Strain Contours (Gauge Direction)
<p align="center">
  <img src="{{ '/assets/images/Normal_Strain.png' | relative_url }}" width="800">
</p>

### 5. Maximum Principal Stress Contour
<p align="center">
  <img src="{{ '/assets/images/Max_Stress.png' | relative_url }}" width="800">
</p>

### 6. Summary of FEM Results
Key numerical results from the simulation:

- Maximum normal stress: 574.64 ksi
- Load-point deflection: 0.23952 in
- Strain at gauge location: 527.57 microstrain

### 7. Torque Wrench Sensitivity (mV/V)
Using the strain from FEA and the properties of a full-bridge strain gauge setup, the calculated sensitivity is:

- Sensitivity: 1.06 mV/V at full-scale torque
- Configuration: Full-bridge, axial-tension gauges

This output determines the voltage-to-torque calibration used during testing.

### 8. Strain Gauge Selection
A full-bridge configuration was selected to maximize sensitivity and temperature compensation. Gauge type and dimensions:

- Gauge length: 3mm
- Grid width: 2mm
- Resistance: 350 Ω
- Waterproof backing for durability

The beam provides sufficient flat surface area at the gauge location to ensure proper bonding and clean strain transfer.
