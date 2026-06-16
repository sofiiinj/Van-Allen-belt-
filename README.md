# Charged Particle Dynamics in Magnetic Fields
 
Numerical simulation of charged particle motion in magnetic dipole fields,
developed as part of the Classical Mechanics / Electromagnetism coursework
at the Universidad de Costa Rica.
 
## Overview
 
This project covers three related simulations:
 
**1. Magnetic Dipole Motion**
Integrates the equations of motion of a charged particle in a pure magnetic
dipole field using `scipy.odeint`. Results are validated by tracking
conservation of kinetic energy over long time spans (τ_max = 26,000).
 
**2. Non-Uniform Field Motion**
Simulates particle dynamics in a non-uniform magnetic field configuration,
tracking the full 3D trajectory and verifying energy conservation throughout
the integration.
 
**3. Van Allen Belt Simulation**
3D animated visualization of electron and proton trapping in the Earth's
dipole magnetic field, reproducing the helical bounce motion characteristic
of the Van Allen radiation belts. Includes:
- Magnetic field lines plotted using dipole field geometry (L-shell parameter)
- Separate inner belt (protons) and outer belt (electrons) trajectories
- Rotating 3D perspective animation exported as GIF
## Physics Background
 
The equations of motion are derived from the Lorentz force on a charged
particle in a magnetic dipole field. Working in normalized units (distances
in Earth radii, time in normalized units), the acceleration components are:
 
```
d²X/dτ² = [(2Z² - Y² - X²) dY/dτ - 3YZ dZ/dτ] / r⁵
d²Y/dτ² = -[(2Z² - Y² - X²) dX/dτ - 3XZ dZ/dτ] / r⁵
d²Z/dτ² = 3Z [Y dX/dτ - X dY/dτ] / r⁵
```
 
where r² = X² + Y² + Z².
 
Energy conservation (|v|² = const) is used as a numerical accuracy check.
 
## Usage
 
```bash
python tarea_programada_f3.py
```
 
This will:
1. Run the magnetic dipole integration and print energy conservation errors
2. Run the non-uniform field simulation
3. Generate and save the Van Allen belt animation as `SimulacionVanAllen.gif`
## Results
 
| Simulation | Integration time | Energy error |
|---|---|---|
| Dipole — Z motion | τ = 1,400 | < 0.1% |
| Dipole — XY motion | τ = 26,000 | < 0.1% |
| Non-uniform field | τ = 140 | Energy integral monitored throughout |
